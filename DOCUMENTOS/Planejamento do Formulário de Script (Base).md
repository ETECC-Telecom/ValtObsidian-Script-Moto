---
Criado: "2026-06-01"
Hora: "15:58"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---
Perfeito! Vamos puxar o freio de mão no visual e focar puramente na **arquitetura da informação e na usabilidade (UX)**.

Olhando para o seu JSON, você tem uma estrutura rica, mas ela é **gigante**. Se jogarmos isso na tela de qualquer jeito, o técnico vai surfar em uma rolagem infinita e desistir de preencher corretamente.

Para resolver o seu desejo de ter **Tabs, Partes Recolhíveis (Accordions) e Indicadores de Progresso**, precisamos fatiar esse JSON de forma lógica. Minha proposta é dividi-lo em **3 Grandes Tabs**, e dentro de cada uma, colocar os blocos de campos recolhíveis.

Vamos estruturar o cérebro desse formulário:
## 📑 Divisão das 3 Grandes Tabs (A Linha do Tempo do Atendimento)

Para fazer sentido na cabeça do técnico, o formulário deve seguir a ordem real do que ele faz na casa do cliente:
### 🟢 Tab 1: Chegada e Contexto (`info_cliente` + `endereco_info_os`)

*Isso é o que ele preenche nos primeiros 5 minutos de atendimento.*

* **Bloco 1 (Recolhível) - Dados do Visitante:** Nome do acompanhante, o parentesco (com o campo "Outros" condicional) e o relato do que está acontecendo.
* **Bloco 2 (Recolhível) - Evidência de Local:** Captura da geolocalização (`loc`) em segundo plano, checklist da foto da fachada e se as informações iniciais batem.
* **💡 Regra de Progresso:** Essa Tab é curta (uns 6 campos). Ele preenche rápido e já vê o indicador de **100%** nela, o que dá uma injeção de ânimo (gamificação) para continuar.
### 🔵 Tab 2: Conferência Técnica (O "Grosso" do JSON)

*Aqui está o coração do seu sistema. Para não assustar, vamos quebrar o `conferencia_technical` em blocos bem específicos.*

* **Bloco 1 - Infraestrutura Base (Cabos e Fontes):** Agrupa a checagem dos cabos UTP (Giga/Power/Ping), se a fonte tem mau contato/amperagem e o local do equipamento.
* **Bloco 2 - A Fibra Óptica:** Campo de sinal (float ou texto "LOS"), limpeza e anexo.
* **Bloco 3 - Configuração e Wi-Fi (`conferencia_router`):** Firmware, DNS, largura de banda, UPnP, IPv6, e aqueles alertas vitais de *ativos acima do normal* e *tempo de atividade ligado há mais de uma semana*.
* **Bloco 4 - Testes e Performance:** Teste de navegação, mapa de calor, e as tabelas dinâmicas de **Ping, Tracert e Velocidade adicionais** (onde ele pode ir adicionando linhas conforme testa no notebook ou celular).
### 🟡 Tab 3: Encerramento e Pós-Venda (`ajuda_interna` + `indicacao` + `educacao_cliente` + etc.)

*O que ele faz antes de pegar a assinatura ou apertar o botão de copiar.*

* **Bloco 1 - Troca de Ativos:** O inventário que você criou (Retirados vs. Inseridos vs. Já existentes). *Esse bloco só pontua no progresso se houver troca marcada.*
* **Bloco 2 - Suporte Interno:** Se precisou acionar a Torre/TI e quem ajudou.
* **Bloco 3 - Relacionamento e Venda:** Checklist de quais orientações de educação ele passou pro cliente (ex: "expliquei sobre barreiras no Wi-Fi") e se o cliente indicou algum amigo (com o telefone de contato).
* **Bloco 4 - Fechamento Técnico:** O campo do relatório de estabilidade (onde ele cola o resultado do `.bat`) e o relato adicional.
## 📉 Como calcular o "Indicador de Progresso" por Categoria?

Para o técnico ver a porcentagem subindo (ex: *Conf. Técnica: 45% preenchido*), precisamos definir o que é "campo válido" no JS.

1. **Campos Booleanos (`Bool`):** Devem começar como `null` ou `undefined` no banco (não como `false`), para sabermos que o técnico ainda não interagiu com eles. Quando ele clica em "Sim" ou "Não", o campo conta como preenchido.
2. **Campos Dinâmicos (Arrays/Listas):** Os blocos de Cabos UTP, Roteadores e Testes de Velocidade começam vazios (`[]`). Se o técnico adicionar pelo menos 1 item e preencher os dados dele, aquele bloco pontua como "concluído".
3. **Campos Opcionais (Observações):** Campos de texto de `observacao` **não devem** contar para os 100% de progresso, senão o técnico vai ser obrigado a encher linguiça só para o app deixar ele fechar a OS. O progresso deve olhar apenas para os dados obrigatórios.
## 🔥 Insights de UX para debatermos no Brainstorming:

1. **O Bloco de Troca de Equipamentos:** No JSON, você colocou uma estrutura excelente de ativos retirados e inseridos. O que acha de fazermos esse bloco aparecer **apenas** se o técnico marcar um botão "Houve troca de equipamento no local"? Se for "Não", o bloco fica oculto e aquela porcentagem de progresso é redistribuída (ou dada como concluída automaticamente), evitando que o técnico veja campos que não vai usar.
2. **A Tabela de Testes (Ping/Tracert/Velocidade):** Como eles estão em formato de lista (Array), o ideal na interface é ter um botão de `[+ Adicionar Teste]`. O técnico clica, escolhe o dispositivo (ex: Notebook da Empresa) e digita os valores. Fica mais limpo do que deixar campos fixos na tela.

O que você achou dessa divisão das 3 Tabs e da lógica de pontuação do progresso? Faz sentido para o fluxo de campo?


