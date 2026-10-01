---
Criado: "2026-10-01"
Hora: "16:18"
tags: Snippets_Uteis
Pai: "[[Desenvolvimento]]"
---

[↩️ Voltar](Desenvolvimento.md)
```table-of-contents
```
## Descrição

Estarei listando aqui todos os componentes de formulário usados por mim dentro do código:

### Container para formulários

Código
```html
<div class="form-group" style="margin-top: 10px;">
                    
</div>
```

CSS
```css
.form-group {
    margin-bottom: 20px;
    display: flex;
    flex-direction: column;
}
```
### Butão Horizontal completo

Código
```html
<button 
	@click=""
	type="button" class="form-button">Titulo</button>
```

CSS
```css
.form-button {
    -webkit-appearance: none;
    appearance: none;
    font-family: inherit;
    font-size: 15px;
    font-weight: 600;
    background-color: var(--destaque-color);
    color: #ffffff;
    border: none;
    border-radius: 6px;
    padding: 12px 24px;
    cursor: pointer;
    transition: background-color 0.2s ease;
    width: 100%;
}

.form-button:hover {
    background-color: var(--destaque-color);
}

.form-button:active {
    background-color: var(--destaque-color);
}
```

### Input de Texto

Código
```html
<div class="form-group">
	<label for="fname" class="form-label">Nome do Cliente/Acompanhante:</label>
    <input 
	    @change=""
	    placeholder="" type="text" id="" name=""
	    value="" 
	    class="form-input">
</div>
```

CSS
```css

```

````
### nome_formulario

Código
```html

```

CSS
```css

```
````