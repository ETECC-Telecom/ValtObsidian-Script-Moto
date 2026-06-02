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
import { LitElement, html, css, unsafeCSS} from 'lit';

export class Home_Page extends LitElement {
    // 1. Em vez de @property, use o objeto static properties
    static properties = {
        nome: { type: String },
        url_config: {type: String}
    };

    static styles = [
        // Transformamos o CSS importado em um objeto que o Lit entende
        css`
        
        `
      ];

    constructor() {
        super();
        this.url_config = ''
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

