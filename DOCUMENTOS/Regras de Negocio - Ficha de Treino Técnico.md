---
Criado: "2026-09-19"
Hora: "12:58"
tags:  
Pai: "[[]]"
Descrição: 
---

[↩️ Voltar](HOME)
```table-of-contents
```
---
Agora vamos abordar todas as regras de negocio atrelados a ficha de Treinamento do técnico junior. 

Essa ficha será gerida pelo Treinador durante todo o processo de treino, e quando encerrada, será encaminhada a liderança para dar inicio a ficha RPC (*Registro de Performance em Campo*). E claro, que o treinador poderá exportar um relatório semanal ao lider com os dados da ficha. Esse relatório terá o formato markdown especifico para o obsidian.

O formato obsdian foi escolhido devido a sua alta capacidade de formatar o markdown, permitindo callouts e outros elementos visuais que podem ser facilmente exportados em pdf quando se deseja encaminhar essas informações. 

Além dos campos que iremos detalhar a baixo, teremos que ter um espaço para notação do próprio treinador, uma caixa de texto livre em algum canto da interface que permita o líder a fazer suas anotações. 
## Dados iniciais da Ficha

A primeira coisa que teremos preenchido são:

- **Nome do Técnico**: Preenchido pelo Treinador;
- **Treinador Responsável**: Preenchido pelo Central OS;
- **Data da Contratação**: Preenchido pelo Treinador;
- **Data de Inicio**: Data que iniciou-se o treino, preenchido pelo treinador.  
- **Data Previsto para Termino**: Preenchido automaticamente pelo sistema levando em consideração 4 semanas a partir da abertura da ficha;
## Cronograma e Evolução Semanal

O cronograma de evolução será separado em 3 ciclos, que inicialmente pode ser representado pela semana de treino, mas devido a possibilidade de prolongação, alterei para ciclo, no qual o técnico terá que observar coisas especificas:

- **Ciclo 1**: principal foco - Observação Logística e Habilidades Básicas.
- **Ciclo 2**: principal foco - Execução Supervisionada e Comportamental.
- **Ciclo 3**: principal foco - Atendimento Solo com Auxílio Remoto.

Cada vez que passar a semana, o técnico irá marcar a mesma como concluída, e o sistema deverá adicionar a data de conclusão. Lembrando que após o check, ficar um alerta para o técnico encaminhar o relatório ao líder responsável. 

O esperado é 1 semana para a analise de cada etapa. Caso seja necessário se prolongar, o treinador precisa registrar essa informação, com uma data prevista para conclusão da etapa. 
## Avaliação de Competências Comportamentais (Soft Skills)

Aqui é onde o treinador irá avaliar as competências do técnico em questão. Essas competências são: Comunicação, Organização, Inteligência Emocional, Uso de EPIs, Condução Veicular, Relacionamento Interpessoal, podendo dar notas de 1 a 4 para cada uma dessas soft skills.

Cada nota atribuída a uma softskill segue com uma observação necessária para aquela nota seguindo uma estrutura semelhante a `Verbo + O que fez + Em qual Situação + Efeito gerado.` por exemplo:

> [!quote] **Apresentou** uma solução alternativa de contorno com linguagem clara e acessível **durante** o atendimento a um cliente insatisfeito com a indisponibilidade temporária da plataforma, **o que** reduziu a ansiedade do usuário, alinhou as expectativas de prazo e garantiu a manutenção da confiança no serviço sem a necessidade de escalonar o chamado.

Cada nível de 1 a 4 representa uma melhora na softskills: 

- **Insuficiente**: Necessita supervisão constante.
- **Em Desenvolvimento**: Falha sob pressão/situações complexas.
- **Proficiente**: Autônomo, atende às expectativas.
- **Referência**: Supera expectativas e serve de exemplo.

Para cada Softskill, deixar um campo para consultar o que a mesma representa no contexto técnico, bem como um placeholder nos formulários de justificativa de aumento de nível contendo `Verbo + O que fez + Em qual Situação + Efeito gerado`. E também, a descrição de cada nível para consulta rápida. 
## Habilidades Técnicas

Teremos basicamente uma lista de habilidades a serem treinadas durante todo o processo de treino. O Cenário ideal de treino é que no final de tudo, o técnico tenha tudo isso preenchido e bem justificado. 

Como vai funcionar. Para cada item da lista, o treinador poderá preencher com: 

- **Não Ensinado** - Aplicado ao final de todo o processo de treinamento com a justificativa do motivo de não ter passado essa informação ao junior; 
- **Teórico** - Passou a teoria ao técnico durante um atendimento ou em momentos de QAP;
- **Prático** - Ensinou na prática o técnico sobre o conceito do contexto.

Em todos os três casos, deveremos justificar quando preencher, para saber o motivo de não ter sido ensinado, quais os meios de ensino teórico foram utilizados ou em qual situação o técnico realizou a prática da habilidade. 

Atualmente a lista de competências técnicas são divididas em 3 categorias, cada uma contendo seus itens:
### Infraestrutura e Redes

- Crimpagem de Conector Fibra (APC/UPC)
- Crimpagem de RJ11 (Telefonia)
- Crimpagem de RJ45 (Padrão de rede)
- Leitura de Topologia de Rede Residencial
- Limpeza de Conectores Ópticos
- Identificação de Atenuação Anormal
- Remanejamento de DROP (Mínimo Teórico)
- Identificação em Shaft/DIO (Mínimo Teórico)
### Configurações e Diagnóstico

- Configuração de Roteador / AP
- Provisionamento de ONU / ONT
- Configuração de Wi-Fi (2.4GHz / 5GHz)
- Troca de PPPoE / Titularidade
- Troca de VLAN
- Teste de Velocidade / Ping / Tracert
- Site Survey / Mapa de Calor (WiFiMan)
- Isolamento de Falha (Cliente vs Rede)
- Redirecionamento de Portas (Mínimo Teórico)
### Execução Operacional

- Identificação de Fontes (Amperagem/Voltagem)
- Identificação de Falha Física (UTP e Fibra)
- Configuração de TV (TipPlay / Sky+)
- Configuração de Conectividade Móvel (Chip/APN)
- Padronização de Instalação (Qualidade ETECC)
- Gestão de Tempo em Campo
- Preenchimento de OS (Qualidade Etecc Conclusões)
## Capacitação FiberSchool

Conforme o treinamento ocorre, o treinador deve cobrar do junior as capacitações do fiberschool. Ao todo o técnico precisa concluir obrigatoriamente até o final do treino as seguintes capacitações: 

- Atendimento Encantador
- Fibra Óptica do Zero
- Dominando o Ping

Caso não consiga concluir até o final da jornada, o treinador deve justificar o motivo dessa não conclusão. E caso tenha concluído, o treinador pode adicionar a data de conclusão. 
## Integração Digital e Ferramentas

O Treinador precisará ensinar ao junior as principais ferramentas que usamos em campo. Essa integração visa que o treinador demonstre o funcionamento ao junior e deixe que o mesmo use elas na prática, principalmente no período de treino que o junior seguirá solo ao cliente.

As ferramentas até o momento são:

- MK Agentes+ (Logística de OS)
- INT6 (Provisionamento)
- Etecc Conclusões (Scripts)
- SpeedTest (Teste de Velocidade)
- WiFiMan (Analise da rede WiFi)
- Guia Telecom (Consultas)
- WhatsApp: Equipe Moto, Suporte Externo, Manutenção Moto, Almoxarifado, Retenção e Vendas.
- CentralOS: Aplicativo de baixa e gestão pessoal do técnico. 

Caso alguma ferramenta não seja ensinada ao técnico junior, devemos justificar isso no relatório. 
## Validação de Boas Práticas

As boas práticas são comportamentos esperados dos técnicos em campo durante sua jornada. Também é dever do treinador passar esses ensinamentos ao junior em campo. Até o momento temos as seguintes boas práticas: 

- Realização da Vistoria Semanal (Segunda-feira);
- Registro de ativos trocados (Notion/WhatsApp/Notas);
- Legenda de fotos e mapas de calor nos anexos;
- Hábito de zerar o TRIP na troca de óleo;
- Comunicação ativa de atrasos ou QAP;
- Registro correto de clientes sem contato;
- 
## Finalização do Treinamento

Após o período de avaliação e treinamento, o treinador deverá encerrar o mesmo a partir de um relatório final indicando se:

- O Técnico foi aprovado para atuação autônoma;
- O técnico ainda precisa de treinamento durante x dias para especializar em alguma'as área especifica.  Nesse caso, será gerado um relatório em md para ser encaminhado ao líder, com essa observação em destaque, e registrado no próprio treinamento.
- Ou ele poderá ser reprovado. Nesse caso, o treinador deverá encerrar o treino como não aprovado repassando um relatório detalhado do motivo do porque o técnico não possui um **Perfil aderente à função**. 

> [!caution] Encerramento de Reprovado Não fecha a Ficha de Treino
> Quando o treinador colocar como reprovado, ele terá que anexar um relatório do motivo dessa reprovação, e em seguida, encaminhar o relatório feito pelo app ao líder responsável. E após a liberação do líder, o treinador poderá encerar a OS;

O encerramento do treino , após o clique do botão e envio do relatório entra em estado de revisão, liberando um outro botão para encerrar ou cancelar encerramento. Quando cancelado, ele deleta a ficha da lista do treinador.  

Quando encerrado, o Líder responsável terá que receber esse relatório, converter em PDF e encaminhar ele ao Treinador para encerramento. 

E será também fixado ao relatório final para o líder do setor um checklist do que deve ser entregue ao junior: 

- Liberação de Kit de Ferramental Completo
- Vistoria de Ferramental Registrada
- Assinatura dos Termos de Responsabilidade (Notebook/Celular)

