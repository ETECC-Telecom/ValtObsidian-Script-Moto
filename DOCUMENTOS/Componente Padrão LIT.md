---
Criado: "2026-06-02"
Hora: "17:47"
tags: Snippets_Uteis
Pai: "[[Desenvolvimento]]"
---

[↩️ Voltar](Desenvolvimento.md)
```table-of-contents
```
## Descrição

Estrutura padrão para um componente LIT
### Código

```js
import { LitElement, html, css, unsafeCSS } from 'lit';
import globalStyle from "./index.css?inline";


export class Home_Page extends LitElement {
    // 1. Em vez de @property, use o objeto static properties
    static properties = {

    };

    static get styles() {
        return css`${unsafeCSS(globalStyle)}`;
    }

    constructor() {
        super();

    }

    // Executado assim que o componente é renderizado na tela
    firstUpdated() {

    }
    connectedCallback() {
        super.connectedCallback(); // ⚠️ Sempre chame o super PRIMEIRO no Lit

    }

    render() {
        return html`
            <!--Retorno renderizado-->
        `;
    }
}

// 2. Em vez de @customElement, use o registro manual
customElements.define('home-page', Home_Page);
```

Com CSS Embutido:

```js
import { LitElement, html, css, unsafeCSS } from 'lit';

export class Home_Page extends LitElement {
    // 1. Em vez de @property, use o objeto static properties
    static properties = {
        
    };

    static get styles() {
	  return css`
	    host: {

	    }
	  `;
	}

    constructor() {
        super();

    }
    
    // Executado assim que o componente é renderizado na tela
    firstUpdated() {
        
    }

    connectedCallback() {
        super.connectedCallback(); // ⚠️ Sempre chame o super PRIMEIRO no Lit

    }

    render() {
        return html`
            <!--Retorno renderizado-->
        `;
    }
}

// 2. Em vez de @customElement, use o registro manual
customElements.define('home-page', Home_Page);
```