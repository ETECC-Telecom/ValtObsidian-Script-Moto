---
Criado: "2026-09-28"
Hora: "17:16"
tags: Nota_Diário_Desenvolvimento
Pai: "[[Desenvolvimento]]"
---

[↩️ Voltar](Desenvolvimento.md)
```table-of-contents
```
---
A Interface será divida em abas assim como nas OS, onde teremos as seguintes abas:

- Informações;
- Soft Skills;
- Habilidades Técnicas;
- Capacitação;
- Integração e Boas Práticas;
- Notas Gerais - Campo de texto livre para o treinador adicionar observações. 
## Aba de Informações

Nessa aba também teremos a configuração inicial e controle geral da ficha. Nela teremos o campo de edição e consulta de: 

- Nome do Técnico
- Treinador Responsável
- Data da Contratação
- Data de Inicio
- Data Previsto para Termino
### Cronograma e Evolução Semanal

Nessa sessão teremos um botão para adicionar um novo ciclo, lembrando que novos ciclos podem ser removidos, porém o 1,2 e 3 não podem. Cada ciclo padrão terá uma pequena descrição do objetivo daquele ciclo, um botão para concluir o ciclo (*após confirmação via modal*), e após concluído, o objeto ficará semitransparente. 

Ao clicar no ciclo, será exibido um modal full que irá mostrar os relatórios associados a aquele ciclo, onde poderemos adicionar e retirar relatórios. 
## Aba de Soft Skills

Aqui será onde o técnico irá gerenciar as softskills do técnico junior. No topo da página teremos um gráfico mostrando o nível em cada uma das softskills cadastradas.

A baixo teremos uma lista das softskills, bem como inputs para manipulá-las. 

Teremos um nome da habilidade, um botão para adicionar e remover nível, e a cada clique do botão, teremos que adicionar uma justificativa seguindo o padrão de escrita já abordada. Além disso, cada grupo terá um icone de exclamação, que ao clicado, abrirá uma dica informando do que se trata aquela softskill em questão. 
## Habilidades Técnicas

Para estruturar essa interface de forma funcional e intuitiva para o treinador, o ideal é focar em uma visualização clara do progresso geral e na rapidez do preenchimento individual.

Abaixo está o detalhamento estruturado para a aba de **Habilidades Técnicas**.
### Estrutura Geral da Interface

### 1. Cabeçalho de Resumo (Status do Treinamento)

No topo da página, um painel fixo exibe a evolução do técnico em tempo real, permitindo que o gestor ou treinador identifique gargalos rapidamente.

* **Progresso Geral:** Barra de progresso percentual ($X\%$ concluído).
* **Métricas Rápidas:**
* **Prático:** Total de habilidades consolidadas em prática (ex: 12/23).
* **Teórico:** Total de habilidades transmitidas em teoria (ex: 8/23).
* **Não Ensinado:** Total de itens justificadamente omitidos (ex: 1/23).
* **Pendente:** Itens ainda não preenchidos (ex: 2/23).

* **Filtros e Busca:**
* Campo de busca rápida por nome da habilidade.
* Filtro por status (*Todos, Pendentes, Prático, Teórico, Não Ensinado*).
* Botão de ação rápida: *"Expandir Todos"* / *"Recolher Todos"*.
### 2. Corpo Principal: Accordion por Categorias

A lista é organizada nas 3 categorias principais através de cartões expansíveis (*accordions*). Cada categoria exibe o nome e um indicador de progresso interno (ex: *Infraestrutura e Redes - 6/8 preenchidos*).

Ao expandir uma categoria, os itens são dispostos em formato de **Tabela Interativa** ou **Cards de Habilidade**.
#### Estrutura de cada Linha / Item de Habilidade

| Habilidade Técnica                        | Status (Seleção)                               | Justificativa / Detalhamento                                 | Ações / Histórico                                         |
| ----------------------------------------- | ---------------------------------------------- | ------------------------------------------------------------ | --------------------------------------------------------- |
| **Crimpagem de Conector Fibra (APC/UPC)** | `[ Não Ensinado ]` `[ Teórico ]` `[ Prático ]` | Campo de texto dinâmico (Placeholder muda conforme o status) | Ícone de data/usuário (ex: *Editado por Carlos em 10/10*) |
### 3. Dinâmica de Preenchimento e Justificativas

O campo de justificativa adapta seu comportamento e *placeholder* com base na opção selecionada nos seletores de status (`Radio Buttons` estilizados ou `Pills` clicáveis):

#### Opção A: **Prático**

* **Estilo Visual:** Tag verde ou azul (indica consolidação).
* **Campo de Justificativa:** Caixa de texto de linha única ou expansível.
* **Placeholder Padrão:** *"Informe o cenário/atendimento em que o técnico executou a prática (ex: OS #1234, atendimento presencial no cliente X)..."*

#### Opção B: **Teórico**

* **Estilo Visual:** Tag amarela ou laranja.
* **Campo de Justificativa:** Caixa de texto.
* **Placeholder Padrão:** *"Descreva como a teoria foi repassada (ex: Explicado durante QAP no dia DD/MM, orientação técnica sobre a topologia)..."*

#### Opção C: **Não Ensinado**

* **Estilo Visual:** Tag cinza ou vermelha.
* **Campo de Justificativa:** Caixa de texto (obrigatória para salvar/concluir o treino).
* **Placeholder Padrão:** *"Motivo do item não ter sido repassado ao técnico ao final do processo..."*
### 4. Funcionalidades e Regras de Validação (UX)

* **Salva Automático (Autosave) ou Salvar Rascunho:** Alterações no status ou na justificativa salvam automaticamente ao perder o foco do campo, exibindo um indicador visual discretamente no canto superior (*"Salvo às 14:30"*).
* **Validação de Conclusão de Treinamento:**
* Se houver itens com status `Pendente` (não preenchidos), o sistema exibe um aviso: *"Existem X habilidades pendentes de avaliação"*.
* Se a opção `Não Ensinado` for selecionada, o botão de finalização exige que o campo de justificativa não esteja em branco.

* **Destaque para Requisitos Mínimos:**
* Os itens etiquetados na regra de negócio como **(Mínimo Teórico)** — ex: *Remanejamento de DROP*, *Identificação em Shaft/DIO* e *Redirecionamento de Portas* — podem conter um pequeno selo informativo (*Badge*) para orientar o treinador de que a validação teórica já é suficiente para aprovação naquele item.

### 5. Apresentação dos Dados para Exportação / Relatórios

Na visualização final (modo de leitura/relatório de encerramento do junior):

* Exibe a lista completa em formato legível para auditoria ou gestão.
* Agrupa visualmente o motivo de cada `Não Ensinado`, os meios de ensino do `Teórico` e as situações práticas do `Prático`, garantindo histórico para acompanhamentos futuros.
## Capacitação


## Integração e Boas Práticas


## Notas Gerais

