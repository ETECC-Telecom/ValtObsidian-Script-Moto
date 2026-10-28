---
Criado: "2026-10-28"
Hora: "09:47"
tags:
  - Classe
Pai: "[[]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

Classe responsável pelas regras de negócio geral do ping e tracert. A lista de pings vai conter um objeto de ping, que pode ser inserido manualmente, ou através de sistemas automáticos de teste, como o NetScanQR. Porém, esses dados externos não podem permitir edição;

`Objeto Ping`
```json
{
	Latencia: ["Min", "Med", "Max"],
	Pacotes: ["Enviados", "Recebidos", "Perdidos"],
	Protocolo: "IPV6/IPV4",
	Ativo: "Empresa/Cliente",
	Destino: "" //Valor da lista de Destinos de IP's
}
```

- [[Variáveis de Lista Exportadas - Lista de Destinos de IP's]]
## Atributos
> [!cite]- Estrutura para uso
> ```
> - `(Tipo_Atributo) Nome_atributo`: Descrição...
> ```

- `(String) Relatorio`: Relatório geral dos testes de ping;
- `(Lista) Pings`: Lista de Todos os pings testados no local; 
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
    class Controller_Nome_Classe{
		-Int nome_atributo
      
		+Retornar_Objeto_Json()
		+Importar_Objeto_Json()
		+Exportar_Estrutura_Simplificado()
		+Exportar_Estrutura_Markdown()
		+Exportar_Relatorio_Simplificado()
		+Exportar_Relatorio_Markdown()
    }
```




