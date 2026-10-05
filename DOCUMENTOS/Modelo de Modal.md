---
Criado: "2026-10-05"
Hora: "13:38"
tags: Snippets_Uteis
Pai: "[[Desenvolvimento]]"
---

[↩️ Voltar](Desenvolvimento.md)
```table-of-contents
```
## Descrição

Modelo de modal padrão usado no sistema:
### Código

html
```html
<div class="container_modal_background">
                
</div>
```

CSS
```css
.container_modal_background {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    z-index: 9999;

    /* Centraliza o modal na tela */
    display: flex;
    justify-content: center;
    align-items: center;

    /* Glassmorphism */
    background: var(--background-color-alfa);
    backdrop-filter: blur(10px);
    -webkit-backdrop-filter: blur(10px);

    overflow-y: auto;
    overscroll-behavior: contain;
}

```
