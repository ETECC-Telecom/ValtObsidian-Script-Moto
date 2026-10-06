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
	<div class="container_modal">
	
	</div>        
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

.container_modal{
    color: var(--btn-background-color);
    padding: .5rem;
    width: 90%;
    border-radius: var(--border-radius);
    display: flex;
    flex-direction: column;
    gap:1rem;
    
}

/* Telas grandes: Desktops (a partir de 1024px de largura) */
@media (min-width: 1024px) {
    .container_modal {
        width: 60%;
    }
}
```
