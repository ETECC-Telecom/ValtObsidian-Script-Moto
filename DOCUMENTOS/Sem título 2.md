---
Criado: "2026-09-04"
Hora: "16:39"
tags: Snippets_Uteis
Pai: "[[Desenvolvimento]]"
---

[↩️ Voltar](Desenvolvimento.md)
```table-of-contents
```
## Descrição

Objeto padrão para a função de log usados em TryCatch
### Código

```js
await registrarLog({
    tipo: 'NOME DO ERRO EM MAIUSCULO',
    mensagem: error?.message || String(error), //Mensagem retornada do erro
    fonte: 'modulo_exemplo.js', //Pode ser o arquivo que está rolando o TryCatch ou o link da url
    linha: null,
    coluna: null,
    stack: error?.stack || null,
    contexto: 'Descrição' //Oque está sendo feito nessa função;
}
```

