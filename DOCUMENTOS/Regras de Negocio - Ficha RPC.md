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

Cada registro de ficha RPC estará gravada em uma planilha de dados simples contendo as colunas: 
- **uuid**: Identificador único e permanente da ficha.
- **versao**: Versão atual do registro na planilha, incrementada pelo backend após cada gravação confirmada.
- **modificacao**:	Contador local que aumenta a cada alteração realizada na ficha.
- **lock**: Indica se a ficha está bloqueada para edição por outro usuário.
- **lock_owner**: Identifica o líder que obteve o bloqueio.
- **payload**: Contém os dados completos da ficha RPC.

Ao abrir a página de lista da ficha, o sistema consulta na planilha o lock de todas as fichas, e trava elas para edição caso **lock** for verdadeiro. O que gera o lock é a ação de edição do líder sobre uma ficha especifica. Quando clicamos em uma ficha para edição, o sistema pergunta a planilha se essa ficha pode ser editada, caso ainda esteja verdadeira, ele retorna true e então, modificamos o estado dela na planilha para false e o nome do líder editor em lock_owner. Apenas o líder editor poderá abrir a ficha para edição.

Um lock só será retirado quando o líder editor clicar em salvar na ficha para enviar os dados para a planilha e liberar a mesma para edição. 

Versão representa a versão que está sincronizada com a planilha, ela será um valor numérico de 1 ao infinito, e sua lógica trabalha diretamente com o atributo de modificação. Quando o valor entre eles são diferentes, significa que vc não tem uma versão atual do banco ou você modificou o item atual.

Essa verificação também é validada quando abrimos a página de lista de fichas.

Os atributos Lock, Lock_Owner, e Versão são salvos em cache para serem usados em caso de falha de internet. 

O Atributo de modificação é alterado somando +1 somente quando ele é igual ao atributo versão. Independente de quantas alterações forem feitas na ficha, a modificação sempre será 1 valor a mais do que a versão. 

Essa edição local deve ser sincronizada com a planilha, e enquanto as versões forem diferentes, o atributo lock se mantem travando a ficha para qualquer outro editor. 
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

Todas as principais classes dessa ficha, irão precisar ter uma função para exportar esses dados já formatados no padrão usado para gerar a linha do tempo. 
## Leitura da Ficha

A visualização e edição da ficha RPC será feito em uma única interface, mas ela terá duas funções de exportação de relatório. Uma mais simples e textual. E outra mais completa em Markdown exclusivo para ser visualizado no Obsidian devido a compatibilidade com os plugins de plotagem. 

**Exportação Simples** - Será um texto mais simples com formatação por caracteres para serem lidos em texto campos de texto simples como Whatsapp.
**Exportação Markdown** - Aqui iremos exportar já usando estruturas de formatação markdown, bem como estruturas de formatação para plotagem de gráficos de plugins obsidian. Além das formatações com callouts e mermaids.

