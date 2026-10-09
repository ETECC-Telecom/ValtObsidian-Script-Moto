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
### Grupo de botão

Código
```html
<div class="btn_group">
    <button 
        @click=""
        type="button" style="background-color: var(--btn-background-color); color: var(--btn-background-color-invert)" class="form-button">Cancelar</button>
    <button 
        @click=""
        type="button" class="form-button">Salvar</button>                        
</div>
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

.btn_group{
  display: flex;
  flex-direction: row;
  gap:1rem;
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
.form-group {
    margin-bottom: 20px;
    display: flex;
    flex-direction: column;
}

/* Estilização das Labels */
.form-label {
    font-size: 17px;
    font-weight: 600;
    margin-bottom: 6px;
    color: var(--btn-text-background-color);
}

/* Reset e Estilo Flat para Inputs de Texto, Select e Textarea */
.form-input,
.form-select,
.form-textarea {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    /* Zera o visual padrão do navegador */

    width: 100%;
    box-sizing: border-box;
    font-family: inherit;
    font-size: 15px;
    padding: 10px 12px;

    border: 2px solid #e2e8f0;
    border-radius: 6px;
    /* Bordas levemente arredondadas */
    background-color: #f8fafc;
    color: #1a202c;
    transition: border-color 0.2s ease, background-color 0.2s ease;
}

/* Estados de Foco */
.form-input:focus,
.form-select:focus,
.form-textarea:focus {
    outline: none;
    border-color: var(--destaque-color);
    /* Azul Flat */
    background-color: #ffffff;
}
```

### Campo de Texto

Código
```html
<textarea
	@change=""
	@input=""
	placeholder=""
	id="" name="" rows="" cols="" class="form-textarea"
    .value=""></textarea>
```

CSS
```css
/* Customizações específicas do Textarea */
.form-textarea {
    resize: vertical;
    min-height: 100px;
}
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