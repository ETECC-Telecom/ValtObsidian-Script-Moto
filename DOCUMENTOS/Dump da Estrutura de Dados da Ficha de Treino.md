---
Criado: "2026-09-19"
Hora: "16:55"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

Dump da estrutura de dados que usarei como referência para desenhar a interface e classes dessa fase do projeto. Representa a estrutura de uma ficha de treino. Claro que essa estrutura não irá ser fixa dessa foram, quero criar classes especializadas em cada comportamento da ficha, então ela será segmentada, mas a classe principal pode exportar ela em json nesse mesmo formato de Payload. 

```json
{
	nome_tecnico: null,
	treinador: null,
	data_contratacao: null,
	data_inicio: null,
	previsao_termino: null, //Data prevista para o termino (~3 semanas)
	data_encerramento: null,
	relatorio_geral_treinador: null //campo onde o treinador registra observações avulsas.
	aprovacao: {
		valor: null, // Aprovado/Observação/Reprovado,
		estado: "aberto", //Aberto/revisão
		relatorios: [
			{
				categoria: null, //Aprovado/Observação/Reprovado
				relatorio: null //Explicação dessa categoria.
			}
		]
	}
	
	cronograma_evolucao_semanal:[
		{
			nome: "ciclo_01", //teremos por padrão 1º a 3º ciclo, e poderesmo adicionas mais;
			finalizada: false,
			data_conclusao: null,
			relatorios: [
				//Relatórios avulsos adicionados a semana, caso ela se prolongue; 
			]
		}
	],
	softskills:[
		{
			nome: null, //Nome da softskill
			nivel: 0, // nível de 1 a 4, 0 = não observado;
			relatorio_evolucional: [
				{
					nivel_avaliado: 0,
					relatorio: null //Motivo de ter subido ou regredido o nível.
				},
			],
		}
	],
	habilidades_tecnicas:[
		{
			nome: null, //Nome da Hardskill (Competênia Técnica)
			categoria: null, // Categoria cadastrada ao qual a competência pertence;
			ensino: [
				false, // Não ensinado
				false, // Ensino Teórico
				false  // Ensino Prático 
			],
			relatorio_evolucional: [
				{
					categoria: null, //Não encinado/ Teórico/ Prático
					relatorio: null 
				}
			]
		}
	],
	capacitacao: [
		{
			nome: null, //Nome da capacitação
			data: null, //Data da conclusão
			relatorio: null //Caso o técncio n conclua a capacitação, devemos justificar nesse relatório. 
		}
	],
	integracao_ferramentas: [
		{
			nome: null, //Nome da ferramenta
			data: null, //Data da monitoria
			relatorio: null //Caso o técncio n aprenda, o treinador deverá justificar o motivo. 
		}
	],
	boas_praticas:[
		{
			nome: null, //Nome da boa prática
			data: null, //Data da monitoria
			relatorio: null //Caso o técncio n aprenda, o treinador deverá justificar o motivo. 
		}
	],
	instrucoes_trabalho:[
		{
			nome: null, //Nome da boa prática
			data: null, //Data da monitoria
			relatorio: null //Caso o técncio n aprenda, o treinador deverá justificar o motivo. 
		}
	]
	
}
```




