---
Criado: "2026-10-27"
Hora: "16:08"
tags:
  - Classe
Pai: "[[]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

Classe usada para os atributos relacionados a OS's do qual é necessário encaminhar equipe externa.

## Atributos
> [!cite]- Estrutura para uso
> ```
> - `(Tipo_Atributo) Nome_atributo`: Descrição...
> ```

- `(Boolean) Necessidade`: Verdadeiro ou Falso para o caso da necessidade de encaminhar equipe externa.
- `(String) Observacao`: Necessário uma observação do motivo de encaminhar externa quando aplicável. 
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

Esse método irá validar, que, se for necessário encaminhar externa, o campo de observação da mesma deverá estar preenchido, diferente de `null`. 
## Diagrama

```mermaid
classDiagram
    class Controller_Encaminhar Externa{
		-Boolean Necessidade
		-String Observacao
		
	    +Retornar_Objeto_Json()
		+Importar_Objeto_Json()
		+Exportar_Estrutura_Simplificado()
		+Exportar_Estrutura_Markdown()
		+Exportar_Relatorio_Simplificado()
		+Exportar_Relatorio_Markdown()
		+Validar_Finalizacao()

		+SET_Necessidade()
		+GET_Necessidade()
		+SET_Observacao()
		+GET_Observacao()
    }
```




