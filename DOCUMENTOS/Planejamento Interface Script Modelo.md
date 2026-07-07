---
Criado: 2026-07-07
Hora: 15:43
tags:
Pai: "[[Design]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

Essa página servirá para adicionar Script pre-criados pelos técnicos para agilizar a baixa da OS. O Fluxo é simples. nos campos de texto permitidos, o técnico poderá dar um duplo clique, que por sua vez, irá abrir um modal focado na categoria especifica daquele campo, e dentro dessa categoria teremos uma lista de scripts padrões que o técnico pode clicar para associar ao campo de texto.

Iremos estruturar as categoria com base no seu contexto geral, como:

**Diagnóstico Técnico**
- Ping, Tracert, Velocidade, Fibra;
**Infraestrutura / Hardware**
- Fonte, Troca de Equipamento, Site Survey;
**Atendimento / Processos**
- Relato do Cliente, Encaminhar Externa, Outros

Não teremos uma função para criar categorias, apenas para vincular novos scripts as categorias existentes. 

A baixo segue o planejamento da estrutura de dados que deverá ser usada no banco!
- [[Estrutura dos Modelos de Script]]
## Drawer de Adição

Para o cenário dos técnicos de rua que usam o aplicativo em campo (dispositivos móveis), o **Drawer (ou Bottom Sheet)** costuma ser a melhor opção, enquanto o **Modal (Pop-up centralizado)** funciona melhor se eles utilizarem notebooks ou tablets grandes.

Quando o técnico inicia o processo de adicionar um texto a caixa de texto, o mesmo não irá substituir o texto já existente, e sim, ser somado a partir do cursor do mouse.




