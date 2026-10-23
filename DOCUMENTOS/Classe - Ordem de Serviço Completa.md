---
Criado: "2026-10-23"
Hora: "13:06"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---

A classe de Ordem de Serviço completa é usada para fazer a gestão geral das OS

## Atributos 

- `(Int) ID`: é o identificador único daquela OS localizada no banco de dados;
- `(String) Tipo_OS`: Tipo da Ordem de serviço, que pode ser: Completa, Retenção, LOS, Retirada, Chip;
- `(Boolean) Finalizada`: Atributo boolean que informa se essa OS já foi finalizada;
- `(Boolean) Usado_Resumo_IA`: Atributo boolean que informa se essa OS foi submetida ao resumo por IA;
- `(Boolean) Data_Alteracao`: Atributo que armazena a data e hora que essa OS foi modificada;
- 
## Diagrama

```mermaid
classDiagram
    class OS_Completa{
		-Int ID
		-String Tipo_OS
		-Boolean Finalizada
		-Boolean Usado_Resumo_IA
		-String Data_Alteracao
      
	    +Salvar_OS_Banco()
		+Editar_OS_Banco()
		+Excluir_OS_Banco()
		+Gerar_Estrutura_Banco()
		+Carregar_Estrutura_Banco()
		+Exportar_OS_Simplificado()
		+Exportar_OS_Markdown()
		+Validar_Finalizacao()
		+Validar_Sincronismo()
    }
```

