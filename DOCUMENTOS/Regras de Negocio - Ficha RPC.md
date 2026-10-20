---
Criado: "2026-10-20"
Hora: "16:01"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---
## Atualização de Status de Elegibilidade

O status de elegibilidade possui ao todo 4 atributos que devem ser monitorados para definir se o técnico está apto a subir de cargo. Até o momento temos apenas uma regra, porém iremos adicionar mais critérios para os demais cargos do setor:
### Atributos de progressão para a primeira progressão:

Auxiliar de Suporte Externo -> Assistente de Suporte Externo
- **Tempo de Casa**: 12 meses;
- **Capacitação**: Trila especifica da Fiberschool;
- **Conduta**: Sem advertências no histórico;
- **Frota**: Sem Sinistros/Multas no ultimo ano.

Esses atributos de progressão são calculados automaticamente quando aberto a ficha. E é responsabilidade da classe pai calcular essas regras de negocio. 
## Sincronismo com a Planilha

Cada registro de ficha RPC estará gravada em uma planilha de dados simples contendo as colunas: UUID, Nome, Data Atualização, e Payload (dados de estrutura do objeto geral da ficha). Quando um lider abre os registros de fichas, eles fazem um sinc entre o app e essa planilha que solicita todos os cadastros da ficha. 

Quando um item é sincronizado ele possui dois atributos de controle principais:

- **data_mod**: codigo da ultima modificação do objeto contendo um código resumido de (DDMMAAAAHHMMSS).
- **ultima_mod_sinc**: código sincronizado da planilha. Quando abrimos a página de gestão das fichas, ele verifica todos os registros cadastrados, e valida se precisam ser enviados a planilha para se manterem sincronizados. 
## Linha do Tempo Evolutiva

Cada objeto responsável por uma categoria de atributo irá fornecer a classe uma lista com os dados evolutivos do técnico. Após receber diversos desses dados o algoritmo irá organizá-lo em uma ordem cronológica para montar uma linha do tempo evolucional.

A saída de cada elemento listado deverá conter: 
- Data do Evento (DD-MM-AAAA);
- Evento; 

E para cada categoria de evento teremos um ícone de destaque:

- ícone para Progressão de Cargo;
- ícone de Performance;
- ícone de gestão de ativos e Segurança;
- ícone para softskills;
- ícones para habilidades técnicas;
- ícone para capacitações;
- ícone para proatividade;
- ícone para feedback;