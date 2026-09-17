---
Criado: 2026-09-17
Hora: 10:18
tags:
Pai: "[[]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---
A página da liderança será habilitada a partir de senha apenas para os líderes do setor. Sua função é organizar o modelo de Auditoria Externa, bem como a gestão da ficha RPC digital dos técnicos. O objetivo desse documento é orquestrar todo o planejamento dessa sessão, bem como definir todas as regras de negócio. 

Todo o controle de gestão será feito em um banco de dados local, e que será sincronizado com uma planilha do Google para a fácil gestão entre os líderes de um mesmo setor. O fluxo vai funcionar da seguinte forma: 

NO Central OS na página de liderança, o gestor irá criar um novo técnico. A geração irá criar uma nova ficha RPC com todas as regras de negocio desse sistema. Cada técnico irá possuir um UUID próprio. O gestor então irá sincronizar com uma link endpoint de planilha já pré configurada, que irá salvar o uuid na primeira coluna, data de sincronismo na segunda, nome do técnico na terceira, e os demais dados serão adicionados no formato JSON nas demais colunas. Assim, quando outro gestor precisar realizar ações naquele técnico, ele pode importar essas informaçoes salvas na planilha e salvar no indexedb local do Central OS. 

```mermaid
sequenceDiagram
    autonumber
    actor Gestor1 as Gestor (Origem)
    participant OS1 as Central OS (Local 1)
    participant Planilha as Endpoint / Planilha
    actor Gestor2 as Gestor (Destino)
    participant OS2 as Central OS (Local 2)

    %% Fluxo de Criação e Sincronização
    Gestor1->>OS1: Acessa Página de Liderança
    Gestor1->>OS1: Cria novo técnico
    OS1->>OS1: Gera ficha RPC com regras de negócio
    OS1->>OS1: Atribui UUID único ao técnico
    Gestor1->>OS1: Inicia sincronização
    OS1->>Planilha: Envia dados (Col 1: UUID | Col 2: Data | Col 3: Nome | Col 4+: JSON)
    Planilha-->>OS1: Confirmação de salvamento

    %% Fluxo de Importação por Outro Gestor
    Gestor2->>Planilha: Solicita importação dos dados
    Planilha-->>OS2: Retorna dados do técnico
    OS2->>OS2: Salva informações no IndexedDB Local
    Gestor2->>OS2: Realiza ações no técnico importado
```

A gestão da ficha RPC foi uma escolha devido a facilidade de consulta e edição, auxiliando em momentos de observação recente e evitando que o gestor venha a esquecer de realizar um registro no futuro. Futuramente a ideia é integrar essa gestão também ao Etecc Frotas, migrando da planilha para a Ferramenta. Assim teremos acesso aos dados e plotagem rapidamente pelo Central OS, e também pelo Frotas. 

[[Regras de Negocio - Sistema de Registro de Performance em Campo (RPC)]]
## Planejamento da Página de Liderança

A página tem como objetivo agrupar todas as ferramentas usadas pela liderança do setor de Suporte Externo. Então teremos o controle da gestão dos técnico, bem como ferramentas de Script para os processos externos que temos que realizar. 
### Scripts

Estarei adicionando a ela o Script da Liderança usando todas as regras de negocio associadas a esse projeto. Atualmente os scripts são:

- **Abertura e Fechamento de Auditoria Externa Pós Atendimento** - Usada para auditorias externas pós atendimento técnico. Embora essa auditoria não seja feita diretamente na página técnica (*que iremos falar em seguida*), sua pontuação será associada a sua ficha RPC;
	- [[Regras de Negocio - Abertura e Fechamento de auditoria externa pós atendimento]]
- **Abertura e Fechamento de Auditoria Externa Pré Atendimento** - Usado para fazer o relatório de auditoria externa acompanhada com o técnico. A premissa aqui é a mesma da anterior, onde os pontos acumulados serão associadas ao técnico em questão cadastrado no sistema.
	- [[Regras de Negocio - Abertura e Fechamento de Auditoria Externa Acompanhada]]
- **Vistoria de Ferramental** - Usado para fazer a abertura e fechamento da vistoria de ferramental do técnico em campo;
- **Vistoria Veicular** - Usado para fazer a vistoria veicular do técnico em campo.

Normalmente auditorias de pós atendimento, devem ser preeviamente estudadas antes de seguirmos para o cliente. Devido a esse fluxo, uma vistoria em aberto permitirá acessar os dados de abertura para consulta enquanto estivermos preenchendo os atributos do fechamento.

Já a auditoria externa acompanhada, ela tem os atributos de abertura e fechamento no mesmo formulário, para isso, basta seguir ao técnico e iniciar o formulário. 

Ambos, poderemos abrir diversas instâncias e trabalhá-las de forma simultânea até o encerramento e finalização. A lista terá uma página para Vistorias em Aberto e finalizadas. 

### Ficha RPC 

Estarei adicionando a essa página uma lista de todos os técnicos cadastrados em sistema, ao clicar no card, seremos direcionados para uma outra página que irá exibir todo o registro RPC do técnico, bem como campos para manipular esses dados, e uma função para exportar como PDF para facilitar o envio. 







