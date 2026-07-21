---
Criado: "2026-06-01"
Hora: "16:19"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---
## 1. Diagnóstico

A gestão de Ordens de Serviço (OS) finalizadas é um fluxo crítico em sistemas operacionais e de campo. Ao migrar os dados de troca de equipamento para uma estrutura separada no IndexedDB e centralizar a listagem, surgem alguns pontos de atenção em UX/UI:

* **Densidade de Informação vs. Ações Críticas:** Juntar visualização, edição e **exclusão definitiva** na mesma linha da tabela aumenta o risco de acionamento acidental do botão de exclusão, afetando diretamente a segurança dos dados persistidos localmente.
* **Sobrecarga Cognitiva na Busca:** A necessidade de filtrar simultaneamente por texto (Nome do Cliente), categoria (Tipo de OS) e ordem cronológica (Data) exige um componente de cabeçalho bem estruturado para não poluir a interface nem confundir a pessoa usuária.
* **Visibilidade de Dados Vinculados:** Com as trocas de equipamentos separadas no IndexedDB, o usuário pode perder o contexto imediato de que aquela OS possui dados adicionais indexados, a menos que haja um sinalizador visual sutil ou um indicador de status.
## 2. Melhor solução recomendada

A solução ideal para este cenário é um **Card List Responsivo (com fallback para Data Grid em telas ultra-wide)** acompanhado de uma **Barra de Filtro Fixa / Sticky**.

### Justificativa baseada em princípios de UX:

* **Hierarquia Visual & Carga Cognitiva:** Agrupar o Nome do Cliente em destaque (`font-weight: bold`), o tipo de OS etiquetado via **Badge/Tag** com cores distintas e a data de forma discreta reduz o tempo de escaneabilidade da tela (Lei de Hick).
* **Descoberta e Feedback Visual:** A inclusão de um **Modal de Confirmação destrutivo** antes de excluir a OS do IndexedDB evita erros irreversíveis. As ações (Ver, Editar, Excluir) ficam consolidadas em um menu de transbordamento (menu de três pontos) ou com botões de ação com hierarquias bem definidas (ícone + tooltip em telas maiores).
* **Usabilidade e Acessibilidade:** Uso do padrão de busca com *debounce* (para evitar re-renders excessivos no IndexedDB) e etiquetas com alto contraste para identificação rápida dos tipos de OS (WCAG 2.1 AA).
## 3. Alternativas

| Alternativa | Vantagens | Desvantagens | Quando utilizar |
| --- | --- | --- | --- |
| **1. Data Grid Tradicional (Tabela)** | Alta densidade de dados; fácil ordenação por colunas. | Dificuldade de adaptação para telas mobile; visual poluído se houver muitas ações. | Desktop corporativo com telas largas e foco em digitação rápida. |
| **2. Cards em Grid (Masonry / Flex)** | Excelente para dispositivos móveis e touch; layout limpo e moderno. | Consome mais espaço vertical; exibe menos itens por tela em desktops. | Ambientes híbridos/mobile em que técnicos operam no campo. |
| **3. Lista Expansível (Accordion List)** | Permite ver detalhes rápidos da OS (como resumo do IndexedDB) sem trocar de página. | Adiciona complexidade de interação e pode dificultar ações em massa. | Quando o usuário precisa verificar detalhes rápidos com frequência. |
## 4. Sugestão de componentes

* **Search Bar com Filtros Integrados:** Campo de texto simples com ícone de lupa e botão para limpar busca.
* **Segmented Buttons / Select Dropdown:** Para filtrar os tipos (*Todas*, *Completa*, *Retenção*, *Externa (LOS)*, *Retirada*).
* **Dropdown de Ordenação (Sort Menu):** Para alternar entre "Mais recentes", "Mais antigas".
* **Badges / Chips:** Para categorizar visualmente o Tipo de OS com cores funcionais.
* **IconButton + Menu / Action Group:** Para as ações "Ver" (olho), "Editar" (lápis) e "Excluir" (lixeira).
* **Dialog / Modal de Confirmação:** Modal de alerta crítico para confirmação da exclusão no IndexedDB.
* **Snackbar / Toast:** Para dar feedback imediato após salvar, editar ou excluir um registro.
## 5. Sugestão visual

### Estrutura de Layout Recomendada

```text
+-----------------------------------------------------------------------+
| [🔍 Buscar cliente...     ] [Tipo: Todos ▾] [Ordenar: Recentes ▾]    |
+-----------------------------------------------------------------------+
|                                                                       |
|  João Silva                     [🏷️ Completa]       15/07/2026, 14:30 |
|  Ações: [👁️ Ver] [✏️ Editar] [🗑️ Excluir]                            |
| --------------------------------------------------------------------- |
|  Maria Oliveira                 [🏷️ Externa (LOS)]  14/07/2026, 09:15 |
|  Ações: [👁️ Ver] [✏️ Editar] [🗑️ Excluir]                            |
|                                                                       |
+-----------------------------------------------------------------------+

```
## 6. Paleta e identidade visual

Para garantir escaneabilidade sem sobrecarregar a vista, sugerimos cores contrastantes e semânticas para os tipos de OS e estados do sistema:
### Cores de Status / Tipos de OS

* **Completa:** Verde Suave (Ex: `#E6F4EA` fundo, `#137333` texto) — Indica conclusão bem-sucedida.
* **Retenção:** Azul Neutro (Ex: `#E8F0FE` fundo, `#1A73E8` texto) — Indica processo comercial/administrativo.
* **Externa (LOS):** Roxo / Âmbar (Ex: `#F3E8FF` fundo, `#6B21A8` texto) — Indica operação externa/técnica.
* **Retirada:** Cinza Escuro / Larandja (Ex: `#FEF3C7` fundo, `#B45309` texto) — Indica recolhimento de equipamento.
### Ações e Alertas

* **Ação Destrutiva (Excluir):** Vermelho Amigável (`#DC2626`).
* **Ações Secundárias (Ver/Editar):** Tons neutros de cinza/azul (`#4B5563`).
* **Contraste mínimo:** Garantir pelo menos 4.5:1 entre texto e fundo das badges (conforme WCAG AA).
## 7. Boas práticas

* **Confirmação Obrigatória em Ações Destrutivas:** Nunca exclua dados do IndexedDB com apenas um clique direto. Utilize um Dialog de confirmação com a ação em destaque vermelho.
* **Debounce no Campo de Busca:** Aplique um atraso de 300ms na digitação da busca para otimizar as consultas locais na memória do navegador.
* **Estado Vazio (Empty State):** Exiba uma mensagem amigável e ilustrativa caso a busca/filtro não retorne resultados ou se o banco estiver sem registros finalizados.
* **Feedback Imediato (Optimistic UI / Toasts):** Após remover um item, atualize a lista imediatamente e exiba um Toast/Snackbar informando que a OS foi removida.
* **Acessibilidade via Teclado:** Garanta que todos os botões de ação e campos de busca sejam navegáveis usando a tecla `Tab` e executáveis via `Enter`/`Space`.
## 8. Erros comuns

* ❌ **Botão de exclusão sem proteção:** Deixar o botão de lixeira exposto e sem modal de confirmação, facilitando cliques acidentais.
* ❌ **Falta de indicadores de carregamento:** Não mostrar um *skeleton screen* ou *spinner* enquanto os dados do IndexedDB estão sendo lidos.
* ❌ **Filtros escondidos demais:** Ocultar o filtro de tipo de OS dentro de menus complexos quando ele é essencial para a rotina diária.
* ❌ **Depender apenas da cor para diferenciar tipos de OS:** Não incluir texto explícito nas badges dos tipos, prejudicando usuários daltônicos.
* ❌ **Perda de estado de filtro:** Não manter os filtros selecionados se o usuário clicar para editar a OS e depois voltar para a lista.