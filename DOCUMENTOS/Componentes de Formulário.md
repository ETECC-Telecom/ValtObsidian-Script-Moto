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

### Componente Select

Código
```html
<div class="form-group">
    <label for="parentesco" class="form-label">Qual o Parentesco?</label>
    <select 
        @change=""
        id="parentesco" name="parentesco" class="form-select">
        <option ?selected="" value="">legenda</option>
    </select>
</div>
```

CSS
```css
.form-group {
    margin-bottom: 10px;
    display: flex;
    flex-direction: column;
    gap:.5rem;
}
/* Customizações específicas do Select */
.form-select {
    cursor: pointer;
    background-image: url("data:image/svg+xml;charset=UTF-8,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 24 24' fill='none' stroke='%234a5568' stroke-width='2' stroke-linecap='round' stroke-linejoin='round'%3e%3cpolyline points='6 9 12 15 18 9'%3e%3c/polyline%3e%3c/svg%3e");
    background-repeat: no-repeat;
    background-position: right 12px center;
    background-size: 16px;
    padding-right: 40px;
    /* Espaço para a seta customizada */
}

/* Reset e Estilo Flat para Inputs de Texto, Select e Textarea */

.form-select{
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
.form-select:focus {
    outline: none;
    border-color: var(--destaque-color);
    /* Azul Flat */
    background-color: #ffffff;
    
}
```

### Duplo RadioButton

Código
```html
<div class="radio-container">
    <label class="radio-box aprovado">
        <input type="radio" name="status" value="aprovado">
        <span>Aprovado</span>
    </label>
    
    <label class="radio-box reprovado">
        <input type="radio" name="status" value="reprovado">
        <span>Reprovado</span>
    </label>
</div>
```

CSS
```css
/* Container principal responsivo */
.radio-container {
    display: flex;
    gap: 15px; /* Espaço entre os botões */
    width: 100%;
    max-width: 400px; /* Ajuste conforme a sua necessidade */
}

/* Estilo base para os botões */
.radio-box {
    flex: 1; /* Faz com que ambos ocupem o mesmo espaço proporcionalmente */
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 12px 20px;
    border-radius: 8px;
    cursor: pointer;
    font-weight: bold;
    transition: all 0.3s ease;
    border: 2px solid transparent;
}

/* Esconde o radio button nativo padrão */
.radio-box input[type="radio"] {
    display: none;
}

/* Estilo específico: APROVADO (cores neutras que mudam ao selecionar) */
.radio-box.aprovado {
    background-color: #f0fdf4;
    border-color: #bbf7d0;
    color: #166534;
}

.radio-box.aprovado input:checked + span,
.radio-box.aprovado:has(input:checked) {
    background-color: #22c55e;
    color: #ffffff;
    border-color: #16a34a;
}

/* Estilo específico: REPROVADO */
.radio-box.reprovado {
    background-color: #fef2f2;
    border-color: #fecaca;
    color: #991b1b;
}

.radio-box.reprovado input:checked + span,
.radio-box.reprovado:has(input:checked) {
    background-color: #ef4444;
    color: #ffffff;
    border-color: #dc2626;
}

/* Efeito ao passar o mouse */
.radio-box:hover {
    opacity: 0.9;
}
```

### Callouts

Código
```html
<div class="callout callout-warning">
    <div class="callout-icon">
        ⚠️
    </div>
    <div class="callout-content">
        <h4 class="callout-title">Atenção Necessária</h4>
        <p>Este é um aviso importante. Certifique-se de conferir todos os dados antes de prosseguir.</p>
    </div>
</div>
```

CSS
```css
/* Estilo Base da Div Callout */
.callout {
    display: flex;
    align-items: flex-start;
    gap: 16px;
    padding: 16px 20px;
    margin: 16px 0;
    border-radius: 8px;
    border-left: 5px solid; /* Borda de destaque na esquerda */
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
    font-family: system-ui, -apple-system, sans-serif;
}

/* Tamanho e alinhamento do ícone */
.callout-icon {
    font-size: 1.25rem;
    line-height: 1.2;
    flex-shrink: 0; /* Impede o ícone de encolher */
}

/* Conteúdo de texto */
.callout-content {
    flex: 1;
}

.callout-title {
    margin: 0 0 4px 0;
    font-size: 1rem;
    font-weight: 600;
}

.callout-content p {
    margin: 0;
    font-size: 0.925rem;
    line-height: 1.5;
}

/* ==============================================
   ESTILO ESPECÍFICO: AVISO / ALERTA (WARNING)
   ============================================== */
.callout-warning {
    background-color: #fffbeb; /* Fundo amarelo suave */
    border-color: #f59e0b;     /* Borda amarela/laranja */
    color: #78350f;            /* Texto num tom escuro contrastante */
}

.callout-warning .callout-title {
    color: #92400e;            /* Título um pouco mais destacado */
}

/* Responsividade para telas muito pequenas */
@media (max-width: 480px) {
    .callout {
        padding: 12px 16px;
        gap: 12px;
    }
}
```

```css
/* Variação: Informação (Azul) */
.callout-info {
    background-color: #eff6ff;
    border-color: #3b82f6;
    color: #1e3a8a;
}

/* Variação: Sucesso (Verde) */
.callout-success {
    background-color: #f0fdf4;
    border-color: #22c55e;
    color: #14532d;
}

/* Variação: Erro/Perigo (Vermelho) */
.callout-danger {
    background-color: #fef2f2;
    border-color: #ef4444;
    color: #7f1d1d;
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
