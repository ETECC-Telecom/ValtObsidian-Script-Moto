---
Criado: "2026-05-30"
Hora: "16:53"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

```json
{
	config_os:{ //Itens relacionados a configuração da OS e nao a baixa do Script
		tipo_os: String, //Completa, Retenção e etc.
		finalizada: Bool,
		info_encaminhadas: Bool, //informação copiada/enviada ao cliente
		id: String, //id do banco
		coordenadas: {
			latitude: String,
			longitude: String,
			precisao: Integer,
		}
	},
	
	info_cliente:{
		nome_cliente: String, //Nome de quem acompanhou a visita;
		parentesco: String, //Titular, Esposa'o, Filho'a, Funcionário, Avó'ô, Tio'a, outro
		parentesco_info: String, //Em caso de outros
		relato_cliente: String //O problema relatado pelo Cleinte;
	},
	
	endereco_info_os:{
		loc: string, //coordenadas puxadas por API;
		anexo_fachada: Bool, //Foto da frente da casa anexada ao mk?
		info_necessaria: Bool, // ordem de serviço gerada com as informações necessárias
	},
	conferencia_tecnica:{
		cabos_utp:[
			{
				cabo: String, // Cabo de rede da WAN, ou outros cabos;
				checagens: [Bool, Bool, Bool], // Checagem se o Cabo é Giga/Teste Powermitter e Ping diretamente no cabo.
				anexo_cabos: Bool, // Foto do cabo de Rede devidamente conectado;
				observacao: String, // Observação adicional quando necessário.
			}
		],
		fontes:{
			mau_contato: Bool, //Checagem de mau contato nas fontes;
			amperagem: Bool, //Checagem se a amperagem da fonte está correta;
			uso: Bool, // Se está sendo usado corretamente, por exemplo, uso de filtro de linha.
			observacao: String //Observações adicionais relacionadas as fontes do local.
		},
		firware_router: Bool, //Se está devidamente atualizado.
		local_equipamento: {
			adequado: Bool, //Se o local está adequado,
			observacao: String //Motivo de ser um local adeguado/não adeguado.
		},
		fibra: {
			sinal: float/String, //Pode ser um valor float, ou uma string "LOS"
			anexo_sinal: Bool, //anexo do sinal de fibra;
			limpeza: Bool, //Se foi realizado a limpeza da fibra;
			observacao: String, // informações relacionadas a fibra.
		},
		conferencia_router:[
			{
				router: String, //Informar se é primeiro ponto, segundo ou ativo do cliente.
				dns: String, //Etecc, Google, outros,
				largura_banda: String, //20MHz, 40MHz, 20/40MHz
				upnp: Bool, //Se está ativado ou não
				ipv6: Bool, //ativado e com protocolo SLAAC,
				acesso_remoto: Bool, //Se está ativo e configurado
				ativos_anormal: {
					verdadeiro: Bool, // Se tem ou não ativos acima do normal.
					observacao: String // Caso ativos esteja acima do normal, quantos são?
				},
				atividade: { //Tempo de funcionamento do ativo acima do esperado
					verdadeiro: Bool,
					observacao: String // Caso ativos estejaligado a mais de 1 semana!
				},
			}
		],
		teste_navegacao: {
			ativos_empresa: Bool,
			ativos_cliente: Bool,
			observacao: String, //observação geral do que foi testado!
		},
		mapa_calor: {
			realizado: Bool,
			pontos_sobra:Bool,
			observacao: String
		},
		ping_adicional:[ //testes além do .bat
			{
				titulo: String, //exe.: Ativos da empresa/cliente
				tipo: String, //ipv4/ipv6
				pacotes: [0,0,0], //enviados, recebidos, perdidos
				latencia: [0,0,0] //min, média, máx
			}	
		],
		observacao_ping: String, // observações relacionadas aos testes gerais, como observações ou motivo de omissão do teste.
		tracert_adicional: [ //testes além do .bat
			{
				ativo: String, //exe.: Notebook da empresa;
				url: String, // ip/url utilizada;
			}
		],
		observacao_tracert: String, // observações relacionadas aos testes gerais, como observações ou motivo de omissão do teste.
		velocidade_adicional:[ //testes além do .bat
			{
				titulo: String, // exe.: Notebook da empresa
				tipo: String, // Wifi/Cabeado
				down: int,
				up: int,
				ping: int
			}
		],
		observacao_velocidade: String, // observações relacionadas aos testes gerais, como observações ou motivo de omissão do teste.
		encaminhar_externa: {
			necessidade: Bool, // Sim/Não
			observacao: String, //motivo da necessidade de encaminhar externa.
		},
		troca_equipamento:{
			ativos:[
				{
					ativo: String, // ONT, ONU, Router, Outros...
					mac: String
				}
			],
			trocas:{
				ativos_retirados:[
					{
						ativo: String, // ONT, ONU, Router, Outros...
						mac: String
					}
				],
				ativos_inseridos:[
					{
						ativo: String, // ONT, ONU, Router, Outros...
						mac: String
					}
				],
				outros_ativos:[ // Em caso de ativos já inseridos no local
					{
						ativo: String, // ONT, ONU, Router, Outros...
						mac: String
					}
				],
			}
		},
	},
	ajuda_interna:{
		verdadeiro: Bool,
		setor: String, // Torre, TI, Supervisão
		nome: String, //Quem auxiliou
	},
	indicacao: {
		solicitado: Bool,
		indicado: Bool, //Cliente passou indicação?
		observacao: String //Numero de contato do indicado!
	},
	educacao_cliente:[
		{
			id_item: int, //Id da lista de item de educação do cliente
			titulo: String, //Informação passada ao cliente
		}
	],
	atendimento_cliente:[
		{
			id_item: int, //Id da lista de item de atendimento ao cliente
			titulo: String, //Informação passada ao cliente
		}
	],
	complemento_atendimento: [ //Informações Extras passadas ao cliente
		{
			titulo: String, 
			descricao: String
		}	
	],
	relato_adicional: String, //Informaçoes adicionais relacionadas a Visita
	relatorio_estabilidade: Strign, //campo para adição do .bat
}
```




