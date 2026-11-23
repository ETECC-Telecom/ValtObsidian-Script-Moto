---
Criado: "2026-11-23"
Hora: "12:29"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---
Como o CentralOS não possui nenhum banco de dados externos com servidores dedicados, usamos as planilhas do Google como recurso para armazenar informações. Todos os dados de informações que serão encaminhados pelos técnicos irão se comunicar com essa mesma planilha. 

O payload geral vai seguir uma estrutura simples:

```json
{
	"Técnico": String, //Nome do técncio que encaminhou os dados
	"Categoria": String, //Qual página da Planilha irá usar
	"Data": String, //Data DD/MM/AAAA que foi encaminhado a informação
	"Hora": String, //Hora HH:MM que foi encaminhado a informação;
	"Dados": {
		//Objeto que varia de acordo com oque está sendo enviado para a página. 
	}
}
```

A planilha terá várias funções para armazenar os dados, onde cada função vai representar uma Categoria, para que possamos chamá-las com `CASE`. 
## Categorias

As categorias criadas até o momento são:

### Cliente sem Contato

Usado pelo técnico para relatar quando um cliente estiver sem contato. Assim conseguimos registrar o dia exato e o tempo médio perdido entre deslocamento e espera. Além de usarmos para validar ofensores quando estamos analisando.

Dados esperados:

```json
{
	"Cliente": String, //Nome do cadastro na OS
	"Minutos_Perdidos": Int, //Tempo aproximado de espera em minutos com deslocamento e esperade contato pela Torre.
	"Quantidade_Visitas": Int, //Quantas vezes já visitou no dia;
	"Observacao": String, //Em caso de observação adicional, adicione aq. 
}
```
### Atraso no Inicio da Rota

Se por algum motivo o técnico for atrasar no inicio da Rota, ele deverá registrar esse atraso usando esse formulário, assim conseguimos registrar o acontecimento de forma automática evitando esquecimentos futuros que possam prejudicar o técnico. Atrasos que forem observados sem relato nessa página, serão devidamente cobrados. 

Dados Esperados:

```json
{
	"Motivo": String, //Descrição geral do motivo de atraso da rota;
	"Tempo": Int, //Tempo em minutos que o técnico levou para iniciar a rota
}
```

Devido a essa observação do tempo, é necessário que o técnico só preencha esse formulário quando de fato for iniciar a rota. 
### Motivo de Hora Extra

Em caso de hora extra, por algum motivo em particular, seja deslocamento ou por alguma solicitação, o técnico precisará registrar aqui esse motivo.

Dados Esperados:

```json
{
	"Motivo": String, //Relatório do motivo da hora extra.
	"Categoria": String, //Categorias mais usadas.
}
```

As categorias pensadas até o momento:
- Logística - Devido a um deslocamento maior;
- 
### Imprevisto na Rota
### Desvio de Rota

Qualquer deslocamento que for fazer ou quando estiver QAP
### Reajuste no ponto