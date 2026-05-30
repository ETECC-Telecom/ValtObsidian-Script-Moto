---
Criado: "{{date:YYYY-MM-DD}}"
Hora: "{{time:HH:mm}}"
tags: Casos_de_Testes
Pai: "[[Testes]]"
ID: CT-{{date:YYYYMMDD-HHmm}}
Responsável: ""
Status: false
---

[↩️ Voltar](Desenvolvimento.md)
```table-of-contents
```
## Objetivo

Descreva claramente o que este teste pretende validar.

## Pré-condições

- Liste aqui o que precisa existir antes do teste (usuário cadastrado, ambiente configurado, dados no banco, etc.)
## Entradas

- Input 1:  
- Input 2:  
- Input 3:  
## Passos de Execução

1.  
## Saída Esperada

- Descreva o que deve acontecer quando o teste for bem-sucedido.  
- Pode incluir mensagens, estados do sistema, redirecionamentos, cálculos etc.
## Saída Obtida

(Preencher somente após rodar o teste)
## Observações

Notas adicionais, prints, erros encontrados, links, logs etc.

*Exemplo Modelo*

```markdown
### Caso de Teste: Login com credenciais válidas
**ID:** CT-001  
**Objetivo:** Verificar se o usuário consegue logar com e-mail e senha corretos.

**Pré-condições:**  
- Usuário cadastrado no sistema.

**Entradas:**  
- Email: usuario@teste.com  
- Senha: 123456  

**Passos de Execução:**  
1. Abrir página de login  
2. Inserir email válido  
3. Inserir senha válida  
4. Clicar em "Entrar"  

**Saída Esperada:**  
- Sistema redireciona para a dashboard  
- Exibe mensagem "Login realizado com sucesso"  

**Saída Obtida:** (deixar em branco até testar)

**Status:** (Aprovado/Reprovado)
```