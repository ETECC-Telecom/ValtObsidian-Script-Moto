---
Criado: "2026-05-30"
Hora: "16:54"
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
	motivo_cancelamento: {
		inviabilidade:{
			verdadeiro: Bool,
			observacao: String,
		},
		condicao_financeira:{
			verdadeiro: Bool,
		},
		mudanca_residencia:{
			verdadeiro: Bool,
		},
		perda_equipamento:{
			verdadeiro: Bool,
		},
		troca_provedor:{
			verdadeiro: Bool,
			observacao: String
		},
		obito_titular:{
			verdadeiro: Bool,
			observacao: String,
		},
		insatisfacao:{
			verdadeiro: Bool,
			recebeu_visita_tecnica: Bool,
			expectativa_atendida: Bool,
			observacao: String,
		},
		outros:{
			verdadeiro: Bool,
			observacao: String,
		}
	},
	equipamentos_retirados:{
		foram_retirados:Bool,
		observacao: String, //caso o retirados seja falso
		ativos_retirados: [
			{
				ativo: String, // ONT, ONU, Router, Outros...
				mac: String
			}
		],
		fontes_retiradas: Bool,
		fotos_anexadas: Bool,
	},
	relato_adicional: String, //Informaçoes adicionais relacionadas a Visita
}
```



