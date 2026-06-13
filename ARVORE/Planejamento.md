---
tags:
  - Planejamento
  - MOC_Home
Pai: "[[HOME]]"
Descrição:
Thumb: Pasted image 20260507141529.png
---

[↩️ Voltar](HOME)
```table-of-contents
```
## Ideia Base

A ideia surgiu de um APP que já existe no setor, porém foge de meu controle, impedindo a adição de novas atualizações. 
## Requisitos

> [!info]- Sobre
> Primeiro você faz o **levantamento de requisitos**, porque ele define o que o sistema precisa fazer (requisitos funcionais), como deve se comportar (não funcionais) e quais restrições existem. Somente depois de saber _o que_ o sistema deve entregar é que você consegue escrever os **casos de uso**, que descrevem _como_ cada usuário interage com o sistema para cumprir esses requisitos. Em outras palavras: **requisitos definem o que é necessário; casos de uso explicam como isso será usado na prática**.
### Funcionais

**[RF001] - Cadastro do Técnico**
	O aplicativo, permitirá alterar ou cadastrar um novo técnico na home da interface. A ideia é que, no primeiro uso do app, estoure um modal solicitando o nome do mesmo para armazenar no sistema (LocalStorage). Com isso, poderemos usar essa variável em todos os cantos do sistema.
	
**[RF002] - Criação de OS Completa**
	Permitir o técnico de criar uma OS completa, com todas as informações necessárias para que o técnico possa completar a Ordem de Serviço, com persistência de dados automática controladas por Local Storage e um objeto dedicado para cada tipo de OS que temos no sistema. 
	
**[RF003] - Finalizar OS**
	O requisito de finalizar OS terá que seguir alguns passos após o técnico clicar em finalizar a OS. Quando o técnico preencher todos os dados, dois botões irão aparecer, um para copiar o Script, outro para copiar as informações passadas ao cliente, e outro para encerrar a OS. Quando esse botão for clicado, sua função responsável estará no objeto que ministra a estrutura da OS, e ela deverá preencher alguns requisitos, como:
- Gerar o Script da OS;
- Gerar o Script de Informações passadas ao cliente (Quando necessário);
- Validar se o técnico adicionou falta de informação na abertura da OS para encaminhar a estrutura de sincronização com a planilha;
- Validar se o técnico adicionou informações extras passadas ao cliente, para encaminhar para a planilha. 

### Não Funcionais

**[RNF001] - Nome do Requisito não funcional**
	Descrição de cada requisito não funcional
## Descrição dos Casos de Uso

![[Casos de Uso.base]]

## Estudo e Pesquisas

Links, anotações, vídeos, artigos…
## Escopo Inicial

> [!info]- Sobre
> **Escopo Inicial** é a definição clara e objetiva do que **a primeira versão do seu projeto realmente precisa ter para funcionar**, sem incluir extras ou melhorias futuras. É uma lista do **mínimo necessário** para entregar algo utilizável, testável ou demonstrável — como as funções básicas, telas essenciais, regras principais ou integrações obrigatórias. Tudo que não for indispensável fica para versões futuras. É a forma de evitar que o projeto cresça demais antes de ficar pronto e garantir foco no que importa primeiro.

