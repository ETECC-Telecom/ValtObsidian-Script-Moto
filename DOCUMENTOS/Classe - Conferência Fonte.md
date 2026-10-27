---
Criado: "2026-10-27"
Hora: "16:27"
tags:
  - Classe
Pai: "[[]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

Classe responsável pela checagem das fontes no local. Os atributos de `Mau_Contato`, `Amperagem`
e `Conexao` devem ser iniciados como **falso** para evitar falso positivo do qual o técnico não valida os atributos e relata da baixa geral que não realizou nenhum teste.
## Atributos
> [!cite]- Estrutura para uso
> ```
> - `(Tipo_Atributo) Nome_atributo`: Descrição...
> ```

- `(Boolean) Mau_Contato`: Atributo Booleano que armazena verdadeiro ou falso para validar se foi verificado questões de mau contato no local.
- `(Boolean) Amperagem`: Atributo Booleano que armazena verdadeiro ou falso para validar se foi verificado a amperagem correta do dispositivo.
- `(Boolean) Conexao`: Atributo Booleano que armazena verdadeiro ou falso para validar se foi verificado o mau uso, ou seja, se está ligado em benjamins ou na gambiarra.
- `(String) Relatorio`: Aqui é onde iremos justificar caso o técnico não realize o check em alguns desses campos. 
## Métodos
> [!cite]- Estrutura para uso
> ```
> ### Nome do Método
> 
> Descrição...
> 
> **Parâmetros** 
> - `Nome_parametro`: Descrição
> 
> **Retorno**
> 	Descrição do retorno.
> ```
### Validar_Finalizacao

Esse método valida a finalização verificando se todos os atributos foram validados. Caso exista algum item não checkado, e o campo de relatório esteja vazio, o método retorna false. 

**Retorno**
	Lista do qual o primeiro índice é `True` ou `False`, enquanto o segundo índice é a mensagem em caso de false, nesse caso: `Você não justificou no relatório o motivo de não ter feito a conferência técnica <tal> nas fontes`
## Diagrama

```mermaid
classDiagram
    class Controller_Fontes{
		-Boolean Mau_Contato
		-Boolean Amperagem
		-Boolean Conexao
		-String Relatorio
      
		+Retornar_Objeto_Json()
		+Importar_Objeto_Json()
		+Exportar_Estrutura_Simplificado()
		+Exportar_Estrutura_Markdown()
		+Exportar_Relatorio_Simplificado()
		+Exportar_Relatorio_Markdown()
		+Validar_Finalizacao()
		
		+SET_Mau_Contato()
		+GET_Mau_Contato()
		+SET_Amperagem()
		+GET_Amperagem()
		+SET_Conexao()
		+GET_Conexao()
		+SET_Relatorio()
		+GET_Relatorio()
    }
```




