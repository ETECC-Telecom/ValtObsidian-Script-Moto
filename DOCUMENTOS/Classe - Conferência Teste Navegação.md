---
Criado: "2026-10-27"
Hora: "17:45"
tags:
  - Classe
Pai: "[[]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

Classe responsável pela gestão dos ativos que foram testados no local. Esse classe faz a gestão de uma lista de ativos testados no local, cada item segue a seguinte estrutura:

`Objeto Ativos`
```json
{
	Ativo_Empresa: true, //Indica se o ativo é da empresa ou do cliente
	Categoria: "", //Vinculado a partir da lista de Tipos de Ativos de Teste
	Relatorio: null, //Relatório geral do ativo testado quando adequado	
}
```

- [[Variáveis de Lista Exportadas - Lista de Tipos de ativos de Teste]]
## Atributos
> [!cite]- Estrutura para uso
> ```
> - `(Tipo_Atributo) Nome_atributo`: Descrição...
> ```

- `(Lista) Ativos`: Lista de todos os ativos testados no local.

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


## Diagrama

```mermaid
classDiagram
    class Controller_Teste_Navegacao{
		-Int nome_atributo
      
		+Nome_Método()
    }
```




