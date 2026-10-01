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
|                                           |                                                |                                                              |                                                           |
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

Abaixo está um detalhamento completo de interface (UI/UX) projetado para a aba **Capacitação FiberSchool**, focando em facilidade de uso para o treinador no dia a dia, clareza das informações e garantia de preenchimento das regras de negócio.
### 1. Visão Geral da Aba

A interface deve permitir que o treinador veja rapidamente o progresso do técnico júnior, marque conclusões com facilidade e insira justificativas obrigatoriamente se o treinamento chegar ao fim sem a conclusão dos cursos.
### 2. Elementos de Cabeçalho (Resumo de Progresso)

No topo da aba, apresentamos um resumo do status atual para dar feedback imediato:

* **Barra de Progresso:** Um indicador visual simples (ex: `2/3 Capacitações Concluídas` ou `66%`).
* **Status Geral:**
* 🟡 *Em andamento* (enquanto o período de treinamento estiver ativo).
* 🟢 *Concluído* (todas as 3 capacitações registradas).
* 🔴 *Pendente de Justificativa* (treinamento encerrado com algum curso em aberto).
### 3. Lista de Capacitações (Cards ou Tabela)

Cada uma das 3 capacitações obrigatórias possui um card individual:

1. **Atendimento Encantador**
2. **Fibra Óptica do Zero**
3. **Dominando o Ping**
#### Estrutura de Cada Card:

* **Título do Curso:** Nome da capacitação.
* **Tag de Status:**
* `Concluído` (Verde)
* `Pendente` (Amarelo / Cinza)

* **Campo de Ação — Se Concluído:**
* **Data de Conclusão:** Campo do tipo *Datepicker* (calendário) para registrar o dia exato em que o júnior finalizou o curso.
* *Botão de Edição/Remoção:* Para alterar a data ou desmarcar caso haja erro.

* **Campo de Ação — Se Não Concluído (Ao final da jornada):**
* **Campo de Justificativa:** Caixa de texto para o treinador detalhar o motivo do não cumprimento (ex: *"Falta de tempo na rotina de campo"*, *"Dificuldade de acesso à plataforma"*, etc.).
### 4. Regras de Validação & Comportamento (UX)

* **Obrigatoriedade Condicional:**
* Se a opção `Concluído` for marcada, o campo **Data de Conclusão** torna-se obrigatório.
* Se o treinamento for encerrado/finalizado pelo treinador e qualquer um dos 3 cursos estiver como `Pendente`, o sistema abre automaticamente um modal ou destaca em vermelho o campo de **Justificativa do motivo da não conclusão**.

* **Bloqueio de Encerramento:** O botão "Finalizar Treinamento do Técnico" só é liberado após as 3 capacitações terem uma **Data de Conclusão** OU uma **Justificativa registrada**.
### 5. Layout Sugerido (Prototipagem em Texto)

```text
--------------------------------------------------------------------------------
[Aba: Capacitação FiberSchool]

PROGRESSO GERAL: [██████████████░░░░░░] 2/3 Concluídos

--------------------------------------------------------------------------------
1. Atendimento Encantador
   Status: [ Concluído v ]
   Data de Conclusão: [ 15/09/2026 ]

--------------------------------------------------------------------------------
2. Fibra Óptica do Zero
   Status: [ Concluído v ]
   Data de Conclusão: [ 22/09/2026 ]

--------------------------------------------------------------------------------
3. Dominando o Ping
   Status: [ Não Concluído v ]
   
   ⚠️ Justificativa de Não Conclusão (Obrigatória para encerramento):
   [ Digite aqui o motivo pelo qual o júnior não concluiu o curso...       ]

--------------------------------------------------------------------------------
[ Salvar Rascunho ]                               [ Finalizar Treinamento ]
--------------------------------------------------------------------------------

```
## Integração e Boas Práticas

Com base nas regras de negócio apresentadas, preparei uma proposta detalhada para a estrutura e interface da aba **"Integração Digital, Ferramentas e Boas Práticas"**.
### 1. Cabeçalho da Aba

* **Título:** Integração Digital & Ferramentas de Campo
* **Subtítulo:** Validação do uso prático de aplicativos e sistemas operacionais pelo técnico júnior.
* **Barra de Progresso:** Um indicador visual simples que atualiza em tempo real (ex.: `5 de 8 ferramentas concluídas`).
### 2. Lista / Tabela de Ferramentas

Cada ferramenta listada abaixo deve apresentar um card ou linha interativa com os seguintes elementos:

* **Status da Capacitação:**
* `[ ] Demonstrado pelo Treinador`
* `[ ] Aplicado na Prática pelo Júnior`
* `[ ] Não Aplicado / Não Ensinado`

* **Campos de Ação:**
* **Status Final:** *Concluído* | *Pendente* | *Não Aplicável*.
* **Observações Técnicas:** Campo de texto livre curto para o treinador pontuar facilidades ou dificuldades do júnior.
* **Justificativa Obrigatória:** Campo de texto que é **habilitado automaticamente** quando o status "Não Aplicado" ou "Não Ensinado" é selecionado.
### 3. Mapeamento dos Itens de Ferramentas

| Ferramenta | Descrição / Foco do Treinamento | Status | Justificativa (se não ensinado) |
| --- | --- | --- | --- |
| **MK Agentes+** | Logística e gestão de Ordens de Serviço (OS) | `[ Concluído / Pendente / Não Ensinado ]` | *Campo condicional* |
| **INT6** | Provisionamento de acessos e equipamentos | `[ Concluído / Pendente / Não Ensinado ]` | *Campo condicional* |
| **Etecc Conclusões** | Execução e consulta de Scripts padrão | `[ Concluído / Pendente / Não Ensinado ]` | *Campo condicional* |
| **SpeedTest** | Aferição e validação de velocidade de banda | `[ Concluído / Pendente / Não Ensinado ]` | *Campo condicional* |
| **WiFiMan** | Análise de sinal, canais e interferências Wi-Fi | `[ Concluído / Pendente / Não Ensinado ]` | *Campo condicional* |
| **Guia Telecom** | Consultas técnicas e procedimentos operacionais | `[ Concluído / Pendente / Não Ensinado ]` | *Campo condicional* |
| **WhatsApp Operacional** | Contatos com setores: Equipe Moto, Suporte Externo, Manutenção Moto, Almoxarifado, Retenção e Vendas | `[ Concluído / Pendente / Não Ensinado ]` | *Campo condicional* |
| **CentralOS** | Baixa de atendimentos e gestão pessoal do técnico | `[ Concluído / Pendente / Não Ensinado ]` | *Campo condicional* |
### 4. Regras de Validação e Comportamento da Tela

* **Bloqueio de Envio:** O relatório final ou a conclusão da aba só pode ser salvo/assinado se todas as ferramentas estiverem marcadas como **Concluído** OU se o campo de **Justificativa** estiver preenchido para os itens marcados como **Não Ensinado**.
* **Seção de Confirmação:** Ao final da página, um checkbox de confirmação do treinador:
> *"Declaro que demonstrei e acompanhei o uso prático das ferramentas assinaladas acima pelo técnico júnior."*

## Notas Gerais
### 1. Estrutura Vertical e Hierarquia (Mobile)

No mobile, o fluxo deve ser **100% vertical**, empilhando as informações de forma limpa, priorizando a leitura e o toque com os polegares.

#### A. Topo Fixo (Sticky Header)

* **Barra Superior Limpa:**
* Botão Voltar / Menu hambúrguer.
* Título compacto da tela (ex: *Notas Gerais*).
#### B. Seção Principal (Regras de Negócio e Campos)

* **Cards com Cantos Arredondados e Espaçamento Generoso:**
* Campos com alvos de toque maiores (mínimo 48px de altura para botões e inputs).
* Inputs numéricos com teclados específicos chamados pelo SO (ex: teclado numérico para notas/métricas).
* Uso de *Dropdowns* no estilo **BottomSheet** (gaveta que sobe da parte inferior da tela), facilitando o toque com uma mão em vez de selects tradicionais de desktop.
#### C. Soluções de UI para a "Caixa de Anotações do Treinador"

Para a anotação livre no mobile, existem duas ótimas abordagens visuais. Escolha a que melhor se adapta ao fluxo do treinador:

#### Opção 1: Card Fixo na Sequência da Rolagem (Recomendado)

* O bloco de anotações fica localizado no final da página (ou logo abaixo do perfil/resumo do aluno).
* **Textarea Adaptável:** Expande a altura conforme o treinador digita para não criar barra de rolagem interna (o que gera "scroll duplo" incômodo no celular).
* **Barra de Ações Flutuante no Teclado:** Quando o teclado virtual sobe, aparece uma micro-barra com ícones de formatação rápida (negrito, lista) e o botão de salvar.

#### Opção 2: Botão Flutuante + BottomSheet (Acesso Rápido)

* **Floating Action Button (FAB):** Um botão redondo flutuante no canto inferior direito com ícone de lápis/bloco de notas.
* Ao tocar no FAB, sobe um painel (*BottomSheet*) ocupando 70% da tela dedicado exclusivamente às anotações do treinador.
* **Vantagem:** Permite ao treinador anotar de qualquer ponto da tela sem ter que rolar até o final da página.

