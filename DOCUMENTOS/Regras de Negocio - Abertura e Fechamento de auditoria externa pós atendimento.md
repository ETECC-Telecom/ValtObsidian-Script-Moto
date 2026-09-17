---
Criado: "2026-09-17"
Hora: "16:18"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---
Para a abertura de uma OS de vistoria externa pós atendimento, devemos recolher os seguintes atributos:
- Data de Abertura Vistoria;
- Técnico que realizou a visita no cliente;
- Nome do Cliente;
- Na parte física validamos se foi realizado a seguintes checagens:
	- Fonte dos Ativos;
	- Posicionamento dos dispositivos;
	- Cabos de Rede;
- Na parta Lógica validamos; 
	- Configurações gerais do Router; 
	- Sinal da Fibra;
	- Velocidade;
	- Ping e Tracert;
	- Mapa de Calor; 
- E na educação do cliente, validamos se o técnico passou alguma informação.
- Campo de Texto para preenchimento livre, no qual podemos associar uma Lista de itens a validar, ou a própria OS do técnico para consulta rápida. 

Esses atributos de checagem são levantados na abertura da OS, conforme a baixa da OS do técnico que alegou ter checado, para que possamos validar no local. 

Ela deverá nos retornar um Script para a abertura da O.S no MK semelhante ao a baixo:

```md
Realizar a **vistoria de pós-visita** referente ao atendimento do técnico **<Nome do Técnico>** ao cliente <Nome do Cliente> no dia **17/09/2026**, com o objetivo de confirmar se todas as manutenções informadas na **baixa da OS** foram devidamente executadas.

**ORDEM DE SERVIÇO DE FECHAMENTO DO TÉCNICO:**  
Check-list do que foi realizado pelo técnico no local.

- Sinal de Fibra: OK
- Cabos de Rede: OK
- Fontes dos Ativos: OK
- Posicionamento dos ativos: OK
- Mapa de Calor: OK
- Configuração dos Ativos: OK
- Teste de Velocidade: OK
- Teste de Ping e Tracert: OK
- Informações passadas ao Cliente: OK

---

**OS PARA CONSULTA:**

- lista de itens inseridos manualmente no app.
- lista de itens inseridos manualmente no app.
- lista de itens inseridos manualmente no app.

> Não se esqueça de colher do cliente um feedback sobre a visita recebida pelo técnico, para que possamos além de todos os dados coletados, levantar o Status do Feedback Cliente.
```

A partir do momento que fazemos a abertura, teremos um item em lista para ser concluído, e quanto clicado, irá nos permitir acessar o formulário de fechamento, que por sua vez, terá que conter os seguintes dados:

- Data da Vistoria - Usada quando iniciamos a vistoria na casa do cliente; 
- Validar os Seguintes Itens - Normalmente são checklists que podemos apenas clicar;
	- Confirmar se todas as manutenções declaradas pelo técnico foram efetivamente realizadas.
	- Validar funcionamento geral dos equipamentos e estabilidade do serviço após o atendimento.
	- Registrar eventuais divergências entre o relatório técnico e a situação encontrada no local.
- Observações Finais - Aqui entra o registro da conclusão da Vistoria, possíveis correções realizadas no local, e melhorias para repassar ao técnico. 
	- Estou querendo dividir essa parte em três para que possamos manipular facilmente comunicações relacionadas a falhas encontras e oportunidades de melhoria;
- Feedback do Cliente com relação ao Técnico - Aqui entra o que o cliente achou do atendimento desse técnico no local;
- Tabela de Pontos para a Planilha - Esse atributo de check irá contabilizar a pontuação que encaminharemos para a RPC do Técnico. 
	- Experiencia do Cliente: +30 Cliente relata satisfação total, elogia a postura do técnico ou destaca a clareza nas explicações.
	- Excelência Tecnica: +20 Nenhum ajuste necessário.
	- Divergência de Relatório: -10 O que foi escrito na OS não condiz com o que foi feito.
	- Feedback Negativo: -30 Cliente reclama de má postura, sujeira deixada no local ou falta de educação.

No final poderemos exportar um script para o fechamento da O.S. no MK semelhante ah:

```md
**Ordem de Serviço** criada para vistoriar o **pós-visita** do técnico **<Nome do Técnico>** no cliente <Nome do Cliente>.

Data da Vistoria: **17/09/2026** 
## Itens de Verificação

Será necessário validar todos os pontos a baixo para uma auditoria pós atendimento ser considerada completa!

[OK] - Confirmar se todas as manutenções declaradas pelo técnico foram efetivamente realizadas. 
[OK] - Validar funcionamento geral dos equipamentos e estabilidade do serviço após o atendimento.
[OK] - Registrar eventuais divergências entre o relatório técnico e a situação encontrada no local.

**Observações Finais:** 

Observações relacionadas a vistoria 

**Feedback do Cliente com Relação a Visita:** 

Feedback do cliente...

## Tabela de Pontos para Planilha:

- [✓] Experiência do Cliente: +30 Cliente relata satisfação total, elogia a postura do técnico ou destaca a clareza nas explicações.
- [✓] Excelência Técnica: +20 Nenhum ajuste necessário.
- [ ] Divergência de Relatório:	-10 O que foi escrito na OS não condiz com o que foi feito.
- [✓] Feedback Negativo:	-30 Cliente reclama de má postura, sujeira deixada no local ou falta de educação. 

PONTOS TOTAIS: 20
```

## Encaminhamento ao RPC

Para a Ficha RPC do técnico em questão, iremos encaminhar O **nome do Cliente**, **data** de realização da vistoria, **pontos** acumulados, observações finais contendo a conclusão, pontos de erro encontrados e possíveis melhorias identificadas. Vou tentar implementar esse resumo por ia com base no script gerado para ser anexado mais facilmente através do botão de ação de resumo por IA. 

