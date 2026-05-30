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
	
	informacao_atendimento: {
		foi_atendido: Bool, 
		local_ocupado: Bool, // casa/ap está em ocupação pelo titular ou outras pessoas?
		telefone: String, // telefone do cliente atualizado
		acordo: Bool, //O cliente aceitou o acordo proposto na ordem de serviço?
		alt_data_vencimento: Bool, //Houve alteração na data de vencimento?
		info: { //Informações negociadas com vizinho, amigo, parente ou outra pessoa além do titular?
			verdadeiro: Bool, 
			observacao: String, //Qual é o nome e a relação com a pessoa que atendeu no local (ex.: vizinho, amigo, parente)?
		},		
		observacao: String, // 
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
	
}
```




