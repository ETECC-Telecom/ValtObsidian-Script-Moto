---
Data de Inicio: 2026-05-30
Frameworks:
Última atualização: 0
Repositório: GitHub
Linguagem:
Ideia: true
Desenvolvimento: false
Teste: false
Concluído: false
cssclasses:
  - dashboard
---

![[MocsHome.base]]
# CentralOS

CentralOS é um aplicativo PWA cujo a função é fazer a gestão dos Scripts de Ordens de Serviço, permitindo o técnico criar atendimentos, e gerir os mesmos ao longo do tempo. Seu nome passa a ideia de que tudo o que o técnico precisa (links, scripts, histórico) está centralizado ali.

Quando o Técnico iniciar uma OS, a mesma irá ser adicionada a estrutura de gestão "LocalStorage" enquanto o técnico estiver trabalhando na quela OS. Quando o mesmo copiar a mesma para anexar ao MK, essa OS será salva em sistema para o "IndexedDB".
## Objetivo Principal

O principal objetivo desse sistema seria:

- Permitir em um único app que o técnico consiga desenvolver todo o script durante o atendimento;
- Consultar Scripts realizados anteriormente através do histórico do APP;
	- Permitir ver informações importantes isoladamente, como a troca de ativos no local;
- Função que permita o técnico encaminhar informações relacionadas ao complemento de "Informações passadas ao cliente", do qual, toda vez que ele ter que criar novas informações, teremos um banco somente para elas para serem encaminhadas a uma planilha de controle, para serem implementadas ao aplicativo no futuro. 
- Controle sobre a quantidade de OS's realizadas no dia/semana/mês;
- Além da gestão de Script, os técnicos imploram para que o app tenha uma função para encaminhar informações ao cliente referentes a visita do local. 
- O Aplicativo deverá permitir o cadastro do Nome do Técnico para anexo em automático em mensagens automáticas do sistema. Essa função irá aparecer toda vez que o app for aberto pela primeira vez, um modal com caixa de texto para adicionar o nome do técnico.
- Também um campo de checklist, onde o técnico irá receber uma lista em markdown, que será convertidos para lista de afazeres no cliente. Usado para visitas que são extremamente importantes seguir certos passos, que pode ser encaminhado direto pela supervisão. E essa lista mostra a porcentagem dos itens já checkados.
- Além disso, terei que disponibilizar um canto para consulta e links rápidas com:
	- Links Rápidos para:
		- Ramais: Torre, Retenção e demais;
		- Grupos do Whats;
		- Guia Telecom;
		- Site Etecc;
		- Aplicativo SAC;
		- Pague com o Pix;
	- Lista dos Planos;