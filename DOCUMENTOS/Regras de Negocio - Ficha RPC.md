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
- **ultima_mod_sinc**: código sincronizado da planilha.

Antes de qualquer modificação na ficha local, devemos verificar atualizações.

Quando abrimos a página das fichas e clicamos em verificar, ele baixa o código (Data Atualização) de todos os registros de ficha, e compara com as **ultima_mod_sinc** locais. Se tivermos códigos divergentes, significa que o item da planilha foi alterada e deve ser sincronizada novamente para substituir a ficha local. Apenas após essa sincronização, poderemos editar uma ficha. 

Quando entramos na ficha e editamos qualquer coisa, ela altera o codigo de **data_mod**, e quando esse código diverge do código **ultima_mod_sinc** da mesma ficha, significa que ela deverá ser upada a planilha para manter a atualização. 

Ou seja, quando data_mod e ultima_mod_sinc são iguais, significa que a planilha e o banco local estão sincronizados.
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