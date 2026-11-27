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
# Introdução 

Como o CentralOS não possui nenhum banco de dados externos com servidores dedicados, usamos as planilhas do Google como recurso para armazenar informações. Todos os dados de informações que serão encaminhados pelos técnicos irão se comunicar com essa mesma planilha. 

O payload geral vai seguir uma estrutura simples:

```json
{
	"tecnico": String, //Nome do técncio que encaminhou os dados
	"categoria": String, //Qual página da Planilha irá usar
	"data": String, //Data DD/MM/AAAA que foi encaminhado a informação
	"hora": String, //Hora HH:MM que foi encaminhado a informação;
	"sinc": Bool, //Informa se esse dado já foi sincronizado;
	"dados": {
		//Objeto que varia de acordo com oque está sendo enviado para a página. 
	}
}
```

A planilha terá várias funções para armazenar os dados, onde cada função vai representar uma Categoria, para que possamos chamá-las com `CASE`. 

> [!danger] Lembre-se que esse processo usará um AppScript com chave de acesso. Essa chave não poderá ser adicionada ao código. Deverá ser cadastrada no App pelos técnicos devido a segurança de dados.
## Categorias

As categorias criadas até o momento são:
### Cliente sem Contato

Usado pelo técnico para relatar quando um cliente estiver sem contato. Assim conseguimos registrar o dia exato e o tempo médio perdido entre deslocamento e espera. Além de usarmos para validar ofensores quando estamos analisando.

Dados esperados:

```json
{
	"cliente": String, //Nome do cadastro na OS
	"minutos_perdidos": Int, //Tempo aproximado de espera em minutos com deslocamento e esperade contato pela Torre.
	"quantidade_visitas": Int, //Quantas vezes já visitou no dia;
	"observacao": String, //Em caso de observação adicional, adicione aq. 
}
```
### Atraso no Inicio da Rota

Se por algum motivo o técnico for atrasar no inicio da Rota, ele deverá registrar esse atraso usando esse formulário, assim conseguimos registrar o acontecimento de forma automática evitando esquecimentos futuros que possam prejudicar o técnico. Atrasos que forem observados sem relato nessa página, serão devidamente cobrados. 

Dados Esperados:

```json
{
	"motivo": String, //Descrição geral do motivo de atraso da rota;
	"tempo": Int, //Tempo em minutos que o técnico levou para iniciar a rota
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
- Logística - Devido a um deslocamento fora do padrão;
- Demanda - Devido a uma demanda muito acima do esperado, ou atendimento demorado anterior;
- Prioridade - Foi solicitada a visita ainda no dia de hoje;
- Manutenção - Por algum motivo foi necessário arrumar a moto no final do expediente;
### Imprevisto na Rota

Alguma coisa ocorreu durante a rota do técnico, sendo necessário parar a mesma para resolver, pode ser um pneu furado ou alguma outra manutenção, ou até um acidente. 

```json
{
	"Motivo": String,
}
```
### Desvio de Rota

Qualquer deslocamento que for fazer, por exemplo, ir na base buscar equipamentos ou quando estiver QAP.

```json
{
	"motivo": String,
	"categoria": String, //QAP, Deslocamento;
	"torre": Bool, //Informou a torre sobre esse deslocamento?
}
```
### Reajuste no ponto

Quando o técnico por algum motivo precisa realizar o reajuste de ponto. Em muitos casos não temos o motivo registrado, e esse formulário servirá para marcar esses motivos:

```json
{
	"motivo": String, 
	"data": String, //Dia que está sendo reajustado;
	"ponto": Array, //Lista com os pontos que foram reajustados, Entrada, saída, Entrada_Almoço, Saída_Almoço. 
}
```
### Região com Chuva

Essa página será usada para auxiliar no registros dos dias atípicos. Todo tempo de chuva deverá ser registrada pelo técnico. Os principais gatilhos de registros são: Inicio de Expediente e retorno do almoço. Porém em qualquer momento do dia que se iniciar uma chuva, poderá registrar, por exemplo, está em uma região as 13h00, e está chovendo, registra. Foi para outra região e parou de chover, porém depois ás 14h começou a chover novamente, registra.

```json
{
	"categoria": String, //Chuva: Forte, Moderada, Leve,
	"parado": Bool, //Precisou aguardar a chuva passar?
	"relatorio": String, //Relatorio do porque precisou parar a rota no momento!
	"cidade": String, //Qual a cidade da ocorrência.
}
```
### Falta de Informação

Pode ocorrer do técnico receber uma OS sem informações adequadas para o entendimento daquela da mesma. Nesses casos, o mesmo pode reportar isso a supervisão para futura analise e alinhamento com o líder do setor. 

```json
{
	"cliente": String, //Nome do cadastro na OS
	"operador": String, //Nome do operador que abriu aquela OS.
	"informacoes_omitidas": [
		//Lista de informações encaminhadas.
	]
}
```

> [!note] Esse tipo de informação será gerada automaticamente pela OS quando ela for fechada, e será adicionada ao banco para ser sincronizado. 
### Informações Adicionais

As informações extras, são informações escritas pelos técnicos durante o atendimento que foram adicionadas manualmente. Essas listas de informações serão sincronizadas com a planilha para que o gestor possa adicionar essa informação a lista de informações passadas ao cliente.

```json
{
	"informacoes_extras": [
		//Lista de informações encaminhadas.
	]
}
```

# Métodos do Sistema

### EXPORTAR_PLANILHA

Esse é o método encontrado em `controller` responsável por encaminhar cada um dos relatórios separadamente. Ele recebe o `objetoData`, que nada mais é do que o objeto estruturado do relatório, contendo o cabeçalho, `tecnico`, `categoria`, `data`, `hora`, `sinc` e também os `dados` que pode variar de acordo com a categoria do relatório criado. 

**Parâmetros** 
- `objetoData`: Objeto data com a estrutura que deverá ser encaminhada para a planilha. 

**Retorno**
	Pode retornar `true` quando todo o processo é bem sucedido, ou pode retornar `false` quando uma falha ocorreu.
# Classes de Relatório Externo

## Classe Principal (Mãe)

- [[Classe - Relatório Externo]]
## Classe de Instância

- [[Classe - Categoria Cliente_sem_Contato]]
- [[Classe - Categoria Atraso_Inicio_Rota]]
- [[Classe - Categoria Motivo_Hora_Extra]]
- [[Classe - Categoria Imprevisto_Rota]]
- [[Classe - Categoria Desvio_Rota]]
- [[Classe - Categoria Reajuste_ponto]]
- [[Classe - Categoria Chuva]]
- [[Classe - Categoria Informacao_Extra]]
- [[Classe - Categoria Falta_Informacao]]