---
Criado: "2026-10-20"
Hora: "15:38"
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
	UUID: null, //codigo unico do técnico criado junto a sua ficha RPC.
	versao: null,	//Versão atual do registro na planilha, incrementada pelo backend após cada gravação confirmada.
	modificacao:null, //Contador local que aumenta a cada alteração realizada na ficha.
	lock:null, //Indica se a ficha está bloqueada para edição por outro usuário.
	lock_owner:null, //Identifica o líder que obteve o bloqueio.
	nome: null,
	perfil: null, //foto do técnico em base64
	cargo_atual: null,
	data_admissao: null,
	historico_upgrade: [ //Evoluão de cargo por dissídio ou mérito
		{
			data: null,
			cargo: null,
			categoria: null, //Dissídio/Mérito
		},
	],
	resumo_perfil: null, //Resumo do técnico para monitoria.
	indicadores_performance:{
		{
			data: null,
			qtd_os: null,
			media_diaria_os: null,
			reincidencia: null,
			ofensores: null,
			advertencias: null,
			tmr_pf: null,
			tmr_pj: null,
			relatorios:[
				//String de relatorio.
			]
		}
	},
	gestao_ativos_seguranca:[
		{
			data:null
			multas: null,
			sinitros: null,
			ativos: null,
			ferramental: null, 
			alertas:[
				
			]			
		}
	],
	softskills:[
		{
			nome: null, //Nome da softskill
			nivel: 0, // nível de 1 a 5, 0 = não observado;
			relatorio_evolucional: [
				{
					nivel_avaliado: 0,
					relatorio: [
						{
							data: null, 
							titulo: null, //(-/+ nível) Data atr
							elevado: false, // informa se foi adiciionado ou removido
							descricao: null // Relato
						}
					] //Motivo de ter subido ou regredido o nível.
				},
			],
		}
	],
	habilidades_tecnicas:[
		{
			nome: null, //Nome da Hardskill (Competênia Técnica)
			categoria: null, // Categoria cadastrada ao qual a competência pertence;
			nivel: null, //nível de 0 a 5;
			historico_evolucional: [
				//String com o nível upado/removido com a descrição geral
			]
		}
	],
	capacitacao: [
		{
			nome: null, //Nome da capacitação
			data: null, //Data da conclusão
			relatorio: null, //Caso o técncio n conclua a capacitação, devemos justificar nesse relatório.
			codigo_ci: null, //codigo de comunicado interno em caso de reciclagem/treinamento
			categoria: null, //treinamento, reciclagem, cursos, fiberschool
			plataforma: null, //fiberschool, nome de outras plataforma, ou etecc em caso de reciclagem ou treino interno.
			local_treino: null, //Onde foi aplicado o treinamento/reciclagem
			nota: 0, //VAlor quando aplicável (Treinamento/REciplagem)
		}
	],
	historico_geral:[
		{
			categoria: null, //feedback ou proatividade
			data: null,
			categoria:null, //Positivo/Negativo/Neutro para categoria de feedback
			relatorio: null
		}
	]
}
```



