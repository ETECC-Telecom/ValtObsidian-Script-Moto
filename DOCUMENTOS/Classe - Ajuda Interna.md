---
Criado: 2026-10-27
Hora: 12:39
tags:
  - Classe
Pai: "[[]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

Essa classe é responsável por gerir a ajuda interna que o técnico recebeu durante o atendimento ao cliente. Ela informa se o técnico recebeu ou não ajuda interna, e quem foi que auxiliou o mesmo. 

## Atributos
> [!cite]- Estrutura para uso
> ```
> - `(Tipo_Atributo) Nome_atributo`: Descrição...
> ```

- `(Boolean) Ajuda_Interna`: Padrão False, e em caso de verdadeiro, significa que o técnico recebeu ajuda interna;
- `(String) Setor`: Setor responsável por auxiliar o técnico;
- `(String) Nome`: Nome do técnico responsável pelo auxilio;
- 
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
### Set_Ajuda_Interna

Altera o Valor de `True` para `False` e vice versa do atributo `Ajuda_Interna`, retornando o valor atual.

**Retorno**
	Retorna o valor atual do atributo `Ajuda_Interna`;
## Diagrama

```mermaid
classDiagram
    class Controller_Ajuda_Interna{
		-Boolean Ajuda_Interna
		-String Setor
		-String Nome
      
		+Retornar_Objeto_Json()
		+Importar_Objeto_Json()
		+Exportar_Estrutura_Simplificado()
		+Exportar_Estrutura_Markdown()
		+Exportar_Relatorio_Simplificado()
		+Exportar_Relatorio_Markdown()
		
		+Set_Ajuda_Interna()
		+Get_Ajuda_Interna()
		+Set_Setor()
		+Get_Setor()
		+Set_Nome()
		+Get_Nome()
    }
```




