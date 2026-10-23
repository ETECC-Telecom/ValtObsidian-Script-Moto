---
Criado: 2026-10-23
Hora: 11:54
tags:
  - regras
Pai: "[[]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---
# Métodos Padrões

Todas as classes com essas funções devem receber o nome igual para evitar divergência.
## Métodos padrões das classes gestoras

- **Salvar_OS_Banco**: Salva a OS no banco na sua primeira criação;
- **Editar_OS_Banco**: Edita a OS no banco quando o mesmo está sendo editado;
- **Excluir_OS_Banco**: Deleta a OS do banco quando chamado;
- **Gerar_Estrutura_Banco**: Gera o Payload que será adicionado ao banco de dados antes de salvar/editar o mesmo. 
- **Carregar_Estrutura_Banco**: Carrega o Payload do banco e reestrutura o objeto do zero.
- **Exportar_OS_Simplificado**: Gera o relatório final para anexar na baixa da OS;
- **Exportar_OS_Markdown**: Gera o relatório no formato markdown para verificar pelo próprio dispositivo. 
- **Validar_Finalizacao**: Valida se é possível encerrar aquela baixa, validando se não tem nenhum atributo obrigatório em aberto que deverá ser justificado.
- **Validar_Sincronismo**: Valida se existem classes filhas com informações favoráveis para encaminhar a planilha. Caso algum retorno seja verdadeiro, o relatório formatado será adicionado ao banco de sincronismo para posterior validação. Esse método será usado apenas na finalização do script, quando o mesmo for fechado.  
## Métodos padrões para classes filhas

- **Retornar_Objeto_Json**: Retorna a classe formatada em Json para ser salva a estrutura geral do objeto principal;
- **Importar_Objeto_Json**: Importa o objeto json exportado e adiciona ele ao objeto para ser usado. 
- **Exportar_Estrutura_Simplificado**: Gera a estrutura de relatório da classe em questão para ser anexado a finalização da classe pai; 
- **Exportar_Estrutura_Markdown**: Gera a estrutura de relatório da classe em questão para ser anexado a visualização Markdown da classe pai;
- **Exportar_Relatorio_Simplificado**: Gera o relatório de campo de texto simplificado para anexo ao final da baixa de OS;
- **Exportar_Relatorio_Markdown**: Gera o relatório de campo de texto markdown para anexo ao final da baixa de OS;
- **Validar_Finalizacao**: Valida se todos os atributos necessários da classe foram fechados. Seu retorno é um array: `[boolean, string]` com o valor verdadeiro ou falso para indicar que tudo foi preenchido corretamente, e uma string que informa uma mensagem de erro para correção. 
- **Validar_Sincronismo**: Esse métodos que pode aparecer nas classes filhas será usado para validar se aquelas informações especificas da classe são favoráveis para adicionar um objeto de sincronismo. Ele retornar um Array de dois índices: Verdadeiro ou Falso, e o Relatório, que será anexado no payload final que irá ao banco de sincronismo para ser encaminhado posteriormente. E ele se comunica diretamente com os métodos `Validar_Sincronismo` das classes filhas correspondentes. 
# Estrutura das Classes

## Classes de Ordens de Serviço

- [[Classe - Ordem de Serviço Completa]]
## Classes Filhas das Ordens de Serviço

- [[Classe - Coordenadas]]
- [[Classe - Educação do Cliente]]