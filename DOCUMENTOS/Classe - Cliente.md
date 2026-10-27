---
Criado: "2026-10-23"
Hora: "16:45"
tags:
  - Classe
Pai: "[[]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

Classe responsável por todos os atributos relacionados aos clientes. 

## Atributos

- `(String) Nome_Cliente`: Nome de quem acompanhou a visita;
- `(String) Nome_Cadastro`: Nome do cadastro da OS;
- `(String) Telefone`: Número de contato;
- `(String) Parentesco`: Titular, Esposa'o, Filho'a, Funcionário, Avó'ô, Tio'a, 
- `(String) Parentesco_info`: Em caso de outros
- `(String) Relato_cliente:`: O problema relatado pelo cliente, obrigatório ser preenchido!

- 
## Métodos

### Validar_Finalizacao

Valida se o técnico preencheu o Nome do Cliente, Nome do Cadastro, Telefone, Parentesco e o mais importante de todos: Relato do Cliente. 
### Nome do Método

Descrição...

**Parâmetros** 
- `Nome_parametro`: Descrição

**Retorno**
	Descrição do retorno.
## Diagrama

```mermaid
classDiagram
    class Controller_Cliente{
		-String Nome_Cliente
		-String Nome_Cadastro
		-String Telefone
		-String Parentesco
		-String Parentesco_info
		-String Relato_cliente
      
		+Retornar_Objeto_Json()
		+Importar_Objeto_Json()
		+Exportar_Estrutura_Simplificado()
		+Exportar_Estrutura_Markdown()
		+Exportar_Relatorio_Simplificado()
		+Exportar_Relatorio_Markdown()
		+Validar_Finalizacao()
		
		+Set_Nome_Cliente()
		+Get_Nome_Cliente()
		+Set_Nome_Cadastro()
		+Get_Nome_Cadastro()
		+Set_Telefone()
		+Get_Telefone()
		+Set_Parentesco()
		+Get_Parentesco()
		+Set_Parentesco_info()
		+Get_Parentesco_info()
		+Set_Relato_cliente()
		+Get_Relato_cliente()
		
    }
```




