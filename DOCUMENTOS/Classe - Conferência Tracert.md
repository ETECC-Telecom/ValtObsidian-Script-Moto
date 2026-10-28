---
Criado: "2026-10-28"
Hora: "10:17"
tags:
  - Classe
Pai: "[[]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

Classe responsável pelas regras de negocio do Tracert. 

Assim como o ping, o a lista de `Tracerts` recebe um objeto pré estruturado:

`Objeto Tracert`
```Json
{
	Ativo: "Empresa/Cliente",
	Destino: "",//Capturado da lista de destinos
	Protocolo: "", //Capturado da lista de protocolos
}
```

O atributo `Destino` recebe um valor que será retirado da [[Variáveis de Lista Exportadas - Lista de Destinos de IP's|Lista de Destinos]] já pré estabelecida. E o atributo `Protocolo` recebe um valor extraído da [[Variáveis de Lista Exportadas - Lista de Protocolos|Lista de Protocolos]]
## Atributos
> [!cite]- Estrutura para uso
> ```
> - `(Tipo_Atributo) Nome_atributo`: Descrição...
> ```

- `(String) Relatorio`: Relatório geral do Tracert
- `(Lista) Tracerts`: Todos os objetos tracerts vinculados a OS.
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
    class Controller_Tracert{
		-String Relatorio
		-Lista Tracerts
      
		+Retornar_Objeto_Json()
		+Importar_Objeto_Json()
		+Exportar_Estrutura_Simplificado()
		+Exportar_Estrutura_Markdown()
		+Exportar_Relatorio_Simplificado()
		+Exportar_Relatorio_Markdown()
		
		+SET_Relatorio()
		+GET_Relatorio()
		+SET_Tracert(Objeto_Ping)
		+GET_Tracert()
		+GET_Tracert(Indice)
    }
```




