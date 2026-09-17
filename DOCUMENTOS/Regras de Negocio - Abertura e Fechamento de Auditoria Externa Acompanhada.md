---
Criado: "2026-09-17"
Hora: "17:16"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---
Para a abertura de OS no contexto de Auditoria Externa Acompanhada, a gente irá preencher tudo no mesmo formulário, sem a necessidade de abrir, para depois continuar. 

OS dados atrelados a uma OS de Auditoria Externa Acompanhada são:

- Data de Realização da Vistoria;
- Técnico que está sendo vistoriado;
- Nome do Cliente que estamos fazendo a vistoria;
- Tipo de Auditoria (Surpresa ou Acompanhada);
- Então entramos nas checklist e caixa de justificativa:
	- Interação com Cliente;
	- Checagem Física Completa;
	- Checagem Lógica Completa;
- Conclusão da Aud0itoria - Relatório sobre a conclusão do auditor;
- Avaliação de Softskills -Esse atributo também é puxado da ficha RPC, e atualizado na conclusão da auditoria. Quando atualizado, ele atualiza a pontuação, e adiciona na lista de justificativa o motivo da evolução ou degradação do atributo em questão. 
	- Comunicação - Nível 1 a 5 + justificativa;
	- Relacionamento Interpessoal - Nível 1 a 5 + justificativa;
	- Organização - Nível 1 a 5 + justificativa;
	- Inteligência Emocional - Nível 1 a 5 + justificativa;
	- Consciência de Segurança e Uso de EPIs - Nível 1 a 5 + justificativa;
	- Responsabilidade na Condução de Veículos - Nível 1 a 5 + justificativa;
- Pontuação - Pontos usados para metrificar a auditoria;
	- Uso de Pró-pé: +10 Utilização obrigatória ao entrar na residência, demonstrando cuidado com a higiene do ambiente.
	- Interação Positiva: +10 Escuta ativa, cordialidade no tom de voz e foco na resolução do problema do cliente.
	- Educação do Cliente: +10 Explicar de forma simples o funcionamento da rede (Wi-Fi 2.4/5G, barreiras físicas) e como evitar problemas futuros (bem como outros temas de rede).
	- Procedimento Físico: +10 Verificação de conectores, disposição, fixação de equipamentos e integridade dos cabos.
	- Procedimento Lógico: +10 Validação de banda contratada, níveis de sinal (dBm) e atualização de firmware se necessário.
	
	- Falta do uso do Pró-pé: -10 Não realizou a utilização obrigatória do Propé, sem justificativa que valide a ação.
	- Falta de Técnica: -10 Deixar de realizar testes básicos que resultem em reincidência de chamado (ex: falta de mapa de calor, ping e tracert).
	- Inconformidade Inicial: -20 Falha grave - não se identificar, ser rude, não explicar o que será feito ou entrar sem autorização.
## Dados da Ultima Vistoria

O Script final ou relatório resumido pela IA será associada num campo de Resumo da Ultima vistoria automaticamente para que o auditor possa verificar se o técnico melhorou desde a ultima vistoria. 

Esse dado será um atributo unico na ficha RPC do técnico, que será puxada em todo inicio de auditoria, e atualizada em toda finalização de auditoria. 
## Mensagens Para o Auditor

Mensagens interessantes para aparecer no formulário e auxiliar na tomada de decisão, pode ser um placeholder, uma callout de alerta ou um simples parâgrafo no meio do formulário. 

### Mensagem no começo do formulário

Por favor, oriente o técnico antes do início dos trabalhos: ele deverá justificar os procedimentos omitidos e relatar detalhadamente ao auditor as ações em execução.
Nota de Confidencialidade: Este alinhamento é estritamente interno da Empresa e não deve ser compartilhado ou apresentado na Auditoria da ISO.
### Mensagens dos Campos de avaliação técnica

**Interação com o Cliente:** 
Verificar nível de comunicação com o cliente no primeiro contato, e se está seguindo os protocolos requeridos pela empresa (inserção do pró-pé).

**Checagem Física Completa:**
Verificar sinal de fibra, integridade de fontes e cabos de rede, posicionamento correto dos equipamentos, fixações e demais aspectos estruturais.

**Feito o Procedimento Completo;**
Checagem Lógica (Teste De Rede):
Executar testes de velocidade, ping, tracert e mapa de calor para validar o desempenho e estabilidade da conexão.

**Conclusão da Vistoria:**
Registrar breve resumo do que foi verificado, ajustes realizados ou pontos de atenção identificados
### Alerta para o Auditor Pós Vistoria

Atenção! Após finalizar a vistoria, não se esqueça de revisar a baixa da OS do técnico para checagem de funcionário do mês. Ao todo devem ser analisados duas OS do técnico por mês após vistoria externa.
### Estrutura para justificativa de evolução/degradação de Softskills
> Aparece como placeholder no campo de texto de justificativa de softskills;

Verbo + O que fez + Em qual Situação + Efeito gerado. 
### Mensagem na sessão de pontuação

**Regra Geral de Penalização:**
Só deverá ser retirado ponto do colaborador quando o processo em si era necessário e viável, porém o técnico omitiu a execução sem apresentar justificativa, ou caso a justificativa apresentada não seja plausível.
## Scripts Esperado

### Script de Abertura:

```md
Realização de **Auditoria Técnica de Campo** referente ao atendimento do técnico **<Nome do Técnico>** em **17/07/2026**.

Esta visita visa assegurar a excelência operacional e a conformidade dos processos realizados em relação às normas técnicas da empresa.
```
### Script de Fechamento:

```md
**Ordem de Serviço** criada para vistoriar o atendimento realizado pelo técnico **<Nome do Técncio>** no dia **17/07/2026** ao Cliente **<Nome do Cliente>**

**TIPO DE AUDITORIA**: Acompanhada
### Checklist de Vistoria Técnica

**INTERAÇÃO COM CLIENTE:**

[OK] - Feito o Procedimento Completo;

**Observações:**
Nesta visita, cliente nao deu a iniciativa de acompanhar, deixando o tecnico por conta propria no local. Nao relatou a dificuldade que sentia, muito menos Acompanhou a visita. Apos o tecnico iniciar a tratativa, cliente informo o necessario, porem voltou a deixá-lo solo.

E na tratativa final, onde o tecnico passou as explicações ao cliente, a mesma manteve o som do local auto, dificultando essa finalização. Mas tecnico conseguiu realizar essa conclusão, mesmo nesse cenario. 

E no final, solicitou a cliente que todos testasse a rede no final do atendimento, para garantir estabilidade antes de sua retirada. 


**CHECAGEM FÍSICA COMPLETA:** 

Verificar sinal de fibra, integridade de fontes e cabos de rede, posicionamento correto dos equipamentos, fixações e demais aspectos estruturais.  
[OK] - Feito o Procedimento Completo;

**Observações:**

**CHECAGEM LÓGICA (TESTE DE REDE):** 

Executar testes de velocidade, ping, tracert e mapa de calor para validar o desempenho e estabilidade da conexão.  
[OK] - Feito o Procedimento Completo;

**Observações:**

**CONCLUSÃO DA VISTORIA:**  

No local tecnico identificou uma dificuldade atrelada a linha voip configurada aonde nao deveria estar. Essa dificuldade ja foi vista antes e realmente causa instabilidade na rede. Entao o mesmo alterou as configurações para se adequar ao padrão. 
### Resumo das Ultimas Vistoria do técnica

## Observações Comportamentais (Softskills)

- **COMUNICAÇÃO**:
    - **Nível:** 5
    - **Comentário:** Dhehhehdh

- **RELACIONAMENTO INTERPESSOAL**:
    - **Nível:** 4
    - **Comentário:** 

- **ORGANIZAÇÃO**:
    - **Nível:** Não Avaliado
    - **Comentário:** 

- **INTELIGÊNCIA EMOCIONAL**:
    - **Nível:** Não Avaliado
    - **Comentário:** 

- **CONSCIÊNCIA DE SEGURANÇA E USO DE EPIS**:
    - **Nível:** 4
    - **Comentário:** 

- **RESPONSABILIDADE NA CONDUÇÃO DE VEÍCULOS**:
    - **Nível:** Não Avaliado
    - **Comentário:** 

## Checklist de Pontos para Planilha:

- [✓] Uso de Pró-pé: +10 Utilização obrigatória ao entrar na residência, demonstrando cuidado com a higiene do ambiente.
- [✓] Interação Positiva:  +10 Escuta ativa, cordialidade no tom de voz e foco na resolução do problema do cliente.
- [✓] Educação do Cliente: +10 Explicar de forma simples o funcionamento da rede (Wi-Fi 2.4/5G, barreiras físicas) e como evitar problemas futuros (bem como outros temas de rede).
- [✓] Procedimento Físico: +10 Verificação de conectores, disposição, fixação de equipamentos e integridade dos cabos.
- [✓] Procedimento Lógico: +10 Validação de banda contratada, níveis de sinal (dBm) e atualização de firmware se necessário.
---
- [ ] Falta do uso do Pró-pé: -10 Não realizou a utilização obrigatória do Propé, sem justificativa que valide a ação.
- [ ] Falta de Técnica: -10 Deixar de realizar testes básicos que resultem em reincidência de chamado (ex: falta de mapa de calor, ping e tracert).
- [ ] Inconformidade Inicial: -20 Falha grave - não se identificar, ser rude, não explicar o que será feito ou entrar sem autorização.

**PONTOS TOTAIS**: 50
```

