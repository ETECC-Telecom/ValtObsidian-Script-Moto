---
Criado: "2026-06-01"
Hora: "15:22"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---
Separar o fluxo por **categorias de scripts** antes de abrir o formulário é uma decisão de UX fantástica. Técnicos odeiam formulários gigantescos onde eles precisam ignorar 20 campos que não fazem sentido para o atendimento atual (como preencher dados de sinal óptico em uma retirada de equipamento).

Eliminar esse ruído vai fazer com que eles preencham o rascunho muito mais rápido.

Vamos estruturar o brainstorming dessa segunda tela (que podemos chamar de **"Seletor de Fluxo"**). Pensando no ambiente de rua, aqui está uma proposta de design funcional para essa etapa:
### 1. O Cabeçalho (Header Dinâmico)

O topo da tela muda sutilmente para dar contexto ao técnico.

* **De um lado:** Botão `← Voltar` (essencial caso ele tenha clicado em "Iniciar OS" sem querer).
* **No centro:** Título claro: **"Qual o tipo de atendimento?"**
### 2. A Disposição dos Cards (Os "Gatilhos rápidos")

Em vez de uma lista simples de texto (estilo *select* ou *dropdown*), que é ruim de clicar no celular enquanto se anda, usamos **Cards Verticais ou Horizontais Grandes**, divididos em duas seções bem definidas:
#### Seção A: Scripts de Campo (Foco Operacional)

Estes cards usam a cor de ação principal (`#38BDF8`) nos ícones para indicar que geram scripts de fechamento.

* **Card 1: Atendimento Completo**
* *Ícone:* `🛠️` ou `⚡`
* *Subtexto explicativo:* "Instalação, reparo de lentidão ou mudança de endereço. (Todos os campos).

* **Card 2: Encaminhar Externa (LOS)**
* *Ícone:* `❌` ou `📡`
* *Subtexto explicativo:* "Rompedura, sem sinal na ONU, problema na CTO. Envio para a equipe de rede."

* **Card 3: Retenção de Cliente**
* *Ícone:* `🤝` ou `🔄`
* *Subtexto explicativo:* "Negociação no local, alteração de viabilidade ou upgrade para evitar cancelamento."

* **Card 4: Retirada de Equipamento**
* *Ícone:* `📦` ou `🚚`
* *Subtexto explicativo:* "Cancelamentos concluídos. Foco no recolhimento de ONU, roteador e fontes."
#### Seção B: Comunicados Internos (Foco Administrativo)

Para separar o que é uma OS de atendimento do que é um aviso para a base, criamos uma linha divisória sutil e uma subseção. Esses cards podem ter ícones em uma cor secundária (como um cinza azulado ou amarelo de atenção) para o técnico diferenciar o chip visualmente.

* **Card 5: Comunicado de Ausência**
* *Ícone:* `🚪` ou `⏳`
* *Subtexto explicativo:* "Cliente não estava no local, portaria recusou a entrada ou imóvel fechado."

* **Card 6: [Ideia Adicional] Comunicado de Infraestrutura Obstruída**
* *Ícone:* `⚠️`
* *Subtexto explicativo:* "Tubulação congestionada, poste sem acesso ou árvore impedindo o lançamento." (Geralmente os técnicos precisam muito avisar a empresa sobre isso rapidamente).
### O Pulo do Gato do UX para essa Tela

1. **Memória de Clique:** O card de **"Atendimento Completo"** deve ser o primeiro e talvez o maior de todos, já que estatisticamente deve representar de 60% a 70% do dia a dia deles.
2. **Gatilho de Input Automático:** Ao clicar em qualquer um desses cards, o app já deve carregar internamente no *LocalStorage* a tag do tipo da OS. Por exemplo, se ele clicar em *Retirada de Equipamento*, o formulário seguinte **esconde automaticamente** campos como "Sinal do cliente", deixando visível apenas "Número de Série dos Itens Recolhidos".




