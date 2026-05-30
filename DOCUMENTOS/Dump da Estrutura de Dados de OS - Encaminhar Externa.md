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
	
	conferencias_tecnicas: {
		rompimento_externo: Bool, //Foi identificado algum rompimento externo:
		fibra_padrao: Bool, //A fibra interna está nos padrões:
		pto: Bool, //A PTO está instalada Corretamente?
		cordao_obtico: Bool, //Verificou o patch cord (se está dobrado ou quebrado):
		limpeza: Bool, //Realizou a limpeza do leitor óptico da ONU e do conector:
		checagem: Bool, //Verificou se o causador do LOS não seria o próprio equipamento:
		anexos: Bool, //Todas as fotos das verificações solicitadas acima foram anexadas no MK:
	},
	indicacao: {
		solicitado: Bool,
		indicado: Bool, //Cliente passou indicação?
		observacao: String //Numero de contato do indicado!
	},
	
	relato_adicional: String, //Informaçoes adicionais relacionadas a Visita
}
```




