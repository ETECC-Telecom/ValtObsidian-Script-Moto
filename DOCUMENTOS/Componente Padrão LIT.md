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
Você precisa preencher os campos de Titulo e Script
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

CSS:

```css
:host {
    display: block;
    box-sizing: border-box;
    color: var(--text-color);
  }

  /* Reset básico para o Shadow DOM */
  *, *::before, *::after {
    box-sizing: inherit;
    margin: 0;
    padding: 0;
  }
  
h2 {
    color: var(--text-color);
    text-align: center;
}

p {
    font-size: var(--paragraph);
    font-weight: 100;
    text-align: left;
}
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