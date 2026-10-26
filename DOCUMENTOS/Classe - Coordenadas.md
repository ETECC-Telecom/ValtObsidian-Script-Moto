---
Criado: 2026-10-23
Hora: 13:37
tags:
  - Classe
Pai: "[[]]"
Descrição:
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

O Objeto de Coordenadas é responsável por gerar as coordenadas da OS na primeira inicialização de Ordens de Serviço.

Para a geração da **localização** basta usar o template: `https://www.google.com/maps?q=<Latitude>,<Longitude>`
## Atributos

- `(String) latitude`: Latitude retornada da função de geolocalização;
- `(String) longitude`: Longitude retornada da função de geolocalização;
- `(String) precisao`: Precisão retornada da função de geolocalização;
- `(String) localizacao`: Localização gerada para o Google maps usando os valores de coordenada;
- `(Boolean) Fachada_Anexada:`: Atributo que informa se a fachada da residência foi anexada.
- `(String) Relatorio_Fachada`: Caso a fachada seja false, necessário explicar o motivo. 

## Métodos

### Definir_Coordenadas

Define as coordenadas atuais do técnico. Esse método será chamado assim que uma OS for iniciada pela primeira vez, definindo os atributos.
### Gerar_Localizacao

Usado para formatar a estrutura do atributo de localização a partir dos atributos de latitude e longitude. 

**Retorno:**
### Set_Fachada_Anexada

Serve para definir o fachada anexada para verdadeiro ou falso, usado para validar se a fachada na OS foi anexada.
### Validar_Finalizacao

Serve para validar se podemos encerrar a OS a partir dessa classe. Ela valida apenas o técnico anexou a foto da fachada, caso falso, valida se foi justificado, e em caso de falso, não permite o encerramento da OS. 
## Diagrama

```mermaid
classDiagram
    class Controller_Coordenadas{
	    -String latitude
		-String longitude
		-String precisao
		-Boolean Fachada_Anexada
		-String Relatorio_Fachada
      
	    +Definir_Coordenadas()
	    +Gerar_Localizacao()
	    +Set_Fachada_Anexada()
	    
		+Retornar_Objeto_Json()
		+Importar_Objeto_Json()
		+Exportar_Estrutura_Simplificado()
		+Exportar_Estrutura_Markdown()
		+Exportar_Relatorio_Simplificado()
		+Exportar_Relatorio_Markdown()
		+Validar_Finalizacao()
    }
```
