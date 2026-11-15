# Planejamento do projeto

Como o Em Dia será construído: o ciclo de vida escolhido, por que a abordagem é ágil, como o Scrum foi organizado na equipe, o que entra no produto e em que ordem, os limites de escopo, tempo e custo e os Objetivos de Desenvolvimento Sustentável que o projeto apoia.

## 1. Ciclo de vida: Incremental com Prototipação

O Em Dia depende de integrações com órgãos de três esferas (Prefeitura, DETRAN-SP, Procuradoria Geral do Estado, Senatran e Receita Federal) e de uma interface que precisa funcionar para um público muito amplo, do jovem que resolve tudo pelo celular ao cidadão mais velho que hoje vai ao Poupatempo. Essas duas características definem a escolha do ciclo de vida.

**Incremental**, porque o produto pode ser entregue por fatias que já valem sozinhas. O primeiro incremento (pedido e diagnóstico de pendências) resolve o pior ponto da jornada atual, que é descobrir tarde demais o que está pendente, mesmo antes de existir pagamento ou agendamento. Os incrementos seguintes (plano com opções, pagamento único, acompanhamento e senha digital) acrescentam valor sem desfazer o que já está pronto. Cada órgão integrado também é um incremento: o MVP nasce com a jornada de veículos em São Paulo e cresce para outros serviços e estados.

**Com Prototipação**, porque as maiores incertezas do projeto não são técnicas, são de uso. O cidadão vai entender o diagnóstico? Vai confiar em autorizar a consulta aos órgãos? O plano explicado em linguagem simples é simples de verdade? Essas perguntas são respondidas de forma mais barata com protótipos navegáveis testados com usuários do que com código pronto. O protótipo valida antes; o incremento constrói depois.

**Por que não os outros.** O modelo em Cascata exigiria congelar os requisitos antes de qualquer integração, e as regras dos órgãos mudam (prazos, descontos, exigências de documento), o que tornaria o retrabalho caro. A Prototipação pura daria boas telas, mas não um sistema que escala com segurança e LGPD. O Espiral é adequado a projetos grandes e de alto risco, com análise formal de risco a cada volta; para uma equipe de três pessoas e um MVP de duas semanas, o custo de gestão não se paga, embora a ideia de atacar primeiro o maior risco (as integrações) tenha sido aproveitada no planejamento das sprints.

## 2. Abordagem clássica ou ágil: por que ágil

A abordagem clássica (plano completo, fases sequenciais, escopo fechado em contrato) faz sentido quando o problema é bem conhecido e a mudança é rara. No Em Dia acontece o oposto: a equipe vai aprender com cada teste de protótipo e com cada integração, e o que se aprende precisa voltar para o produto na mesma semana. Por isso a abordagem é **ágil**, com o framework **Scrum**: ciclos curtos (sprints de uma semana), entrega de um incremento funcional ao fim de cada ciclo, prioridade definida pelo valor para o cidadão e revisão com feedback real a cada sprint.

A escolha também combina com o contexto acadêmico e com a equipe: três integrantes, dedicação parcial e prazo curto. Um plano clássico detalhado consumiria boa parte do tempo disponível só para ser escrito; o Scrum concentra o planejamento no que será feito nos próximos sete dias e deixa o restante do backlog ordenado, mas aberto a mudanças. O custo dessa escolha é disciplina: Daily curta, backlog sempre priorizado e uma Definição de Pronto respeitada por todos.

## 3. Scrum na equipe Em Dia

### 3.1 Papéis

| Papel | Integrante | Responsabilidades |
| :--- | :--- | :--- |
| **Product Owner** | Guilherme da Cunha | Dono do backlog e da visão do produto. Prioriza pelo valor para o cidadão, escreve os critérios de aceite, representa os usuários entrevistados e valida o incremento na Review. |
| **Scrum Master** | Kenny Tanaka | Garante o funcionamento do Scrum: facilita Planning, Daily, Review e Retrospectiva, remove impedimentos (acesso a dados de teste, ambiente) e protege a equipe de mudanças de escopo no meio da sprint. |
| **Time de Desenvolvimento** | Pedro Moisés, Kenny Tanaka e Guilherme da Cunha | Multifuncional e auto-organizado: modelagem (BPMN), protótipo (Pencil), back-end Java e banco Oracle, integrações simuladas, testes (JUnit) e documentação. Pedro lidera a arquitetura de dados e as integrações; todos codificam. |

**Eventos:** Sprint Planning (1 h, segunda-feira), Daily Scrum (15 min, online, nos dias úteis), Sprint Review (45 min, sexta-feira, com demonstração do incremento) e Sprint Retrospective (30 min, logo após a Review).

**Artefatos:** Product Backlog, Sprint Backlog (quadro Kanban com as colunas Para fazer, Fazendo e Feito) e Incremento.

**Definição de Pronto:** funcionalidade testada, revisada por outro integrante, documentada e demonstrada na Review.

### 3.2 Como os requisitos foram levantados

- **Entrevista** com cidadãos que passaram por transferência ou licenciamento de veículo nos últimos 12 meses, com roteiro semiestruturado: o que tentou fazer, o que descobriu tarde, quantas vezes voltou ao posto, o que teria ajudado. As falas deram origem às histórias de Seu José e Marina usadas no pitch e no storyboard.
- **Observação** do atendimento presencial em uma unidade do Poupatempo: fluxo do guichê, documentos conferidos, motivos de devolução do cidadão e tempo entre agendamento e atendimento. É a base do processo atual modelado em BPMN.
- **Benchmarking** de serviços públicos digitais que já resolveram o problema do dado pedido uma vez só: X-Road e o rastreador de acessos da Estônia, OOTS da União Europeia, Tell Us Once do Reino Unido, LifeSG de Singapura, Diia da Ucrânia e, no Brasil, a conta gov.br e o Pix. Daí vêm os requisitos de pagamento único, consentimento por órgão e "quem viu meus dados".

### 3.3 Product Backlog priorizado (MVP)

Prioridade pelo método MoSCoW e ordem de execução definida pelo Product Owner. Estimativa em pontos (1, 2, 3, 5, 8). RF é requisito funcional; RNF é requisito não funcional.

| # | ID | Tipo | Requisito | Prioridade | Pontos | Origem |
| :---: | :--- | :---: | :--- | :---: | :---: | :--- |
| 1 | RF01 | RF | Como cidadão, quero fazer meu pedido em linguagem natural, por texto ou voz ("quero licenciar meu carro"), para não precisar saber qual órgão cuida de quê. | Must | 5 | Entrevista |
| 2 | RNF01 | RNF | O sistema deve seguir a LGPD por padrão: consentimento explícito por órgão antes de qualquer consulta, minimização de dados e registro de todo acesso. | Must | 5 | Benchmarking (Estônia) e legislação |
| 3 | RF02 | RF | Como cidadão, quero ver num único diagnóstico todas as pendências que travam meu pedido no município, no estado e na União, com órgão de origem e valor. | Must | 8 | Observação e entrevista |
| 4 | RNF02 | RNF | Autenticação pela conta gov.br (níveis prata e ouro), comunicação criptografada com os órgãos e trilha de auditoria; sem senha própria do Em Dia. | Must | 3 | Benchmarking (gov.br) |
| 5 | RF03 | RF | Como cidadã, quero um plano na ordem certa, com opções (à vista, parcelado, indicar condutor) e consequências explicadas em linguagem simples, para decidir com segurança. | Must | 5 | Entrevista |
| 6 | RF04 | RF | Como cidadã, quero pagar tudo num único Pix e que o Em Dia repasse o valor a cada órgão, para não entrar em três sites nem guardar três boletos. | Must | 8 | Benchmarking (Pix, Tell Us Once) |
| 7 | RNF03 | RNF | Inclusão: linguagem simples, entrada por voz, contraste e fontes conforme WCAG 2.1 AA e funcionamento em conexões lentas e celulares básicos. | Must | 3 | Entrevista |
| 8 | RF05 | RF | Como cidadã, quero acompanhar a baixa de cada pendência e receber o documento liberado no app (por exemplo, o CRLV-e), sem conferir órgão por órgão. | Should | 3 | Observação |
| 9 | RF06 | RF | Como cidadã, quando o serviço exigir presença, quero que o app agende e emita a senha digital do Poupatempo, para chegar e ser atendida sem fila. | Should | 5 | Observação (Poupatempo) |
| 10 | RF07 | RF | Como cidadão, quero ver "quem viu meus dados" (órgão, data e finalidade) e poder contestar um acesso, para confiar na plataforma. | Should | 3 | Benchmarking (Estônia) |
| 11 | RNF04 | RNF | Escala e desempenho: diagnóstico completo em até 10 segundos, disponibilidade de 99,5% e arquitetura preparada para a base de 175 milhões de contas gov.br. | Should | 5 | Benchmarking (gov.br) |
| 12 | RNF05 | RNF | IA supervisionada: o modelo interpreta o pedido e explica opções, nunca decide nem paga sozinho; respostas rastreáveis e revisão humana em caso de dúvida. | Should | 3 | Entrevista e benchmarking |

Fora do MVP (Could): notificação preventiva antes do vencimento, perfil para MEI, versão assistida para atendentes do Poupatempo e expansão para outros estados e para a camada nacional.

### 3.4 Plano de sprints (duas sprints de uma semana)

| | Sprint 1 (23 a 27/11) | Sprint 2 (30/11 a 04/12) |
| :--- | :--- | :--- |
| **Meta da sprint** | "O cidadão faz um pedido e vê, em segundos, tudo o que o impede nas três esferas." | "O cidadão resolve: escolhe o plano, paga num Pix só, acompanha as baixas e já sai com a senha quando precisar ir ao posto." |
| **Itens do backlog** | RF01, RNF01, RF02 e RNF02 (21 pontos) | RF03, RF04, RNF03, RF05, RF06 e RF07 (27 pontos) |
| **Sprint Backlog** | Modelo de dados (Oracle) de cidadão, veículo e pendência; serviço de interpretação do pedido (IA); conectores simulados de Prefeitura, DETRAN-SP, PGE-SP e Senatran; tela de consentimento por órgão; tela de diagnóstico; testes JUnit dos conectores; registro de acessos (LGPD) | Motor de regras do plano (ordem e dependências); opções e consequências; integração Pix em sandbox e repasse por órgão; acompanhamento de baixas; agendamento e senha digital; tela "quem viu meus dados"; acessibilidade (voz e contraste); testes de ponta a ponta |
| **Incremento** | Protótipo funcional do pedido ao diagnóstico, demonstrado com os dados do caso Marina. | Jornada completa demonstrável: pedido, diagnóstico, plano, Pix e documento liberado ou senha. |
| **Critério de sucesso** | Cinco usuários de teste entendem o diagnóstico sem ajuda; diagnóstico em menos de 10 segundos. | Cinco usuários concluem a jornada sem ajuda; nenhum dado além do consentido é consultado. |

## 4. Tripla restrição

Escopo, tempo e custo se puxam: mexer em um altera os outros, e a qualidade é o resultado desse equilíbrio. Para o Em Dia a tripla restrição foi fixada assim:

| Restrição | Definição no projeto | Como é controlada |
| :--- | :--- | :--- |
| **Escopo** | MVP de uma jornada (licenciamento e transferência de veículo em São Paulo) com quatro órgãos integrados e as 12 histórias do backlog (Must e Should). | Backlog priorizado pelo PO; o que não cabe sai pela ordem inversa de prioridade (primeiro os Should: RF07, RNF04 e RF06). |
| **Tempo** | Duas sprints de uma semana (10 dias úteis), com Review ao fim de cada uma; entrega acadêmica em 19/11/2026. | Sprints com duração fixa; a meta da sprint não muda no meio; Daily para detectar atraso em até 24 horas. |
| **Custo** | Três integrantes com cerca de 10 horas semanais cada (perto de 60 horas no total); infraestrutura acadêmica e gratuita (Java, Oracle, sandbox do Pix, Packet Tracer). | Horas registradas no quadro; nenhum serviço pago; integrações reais substituídas por simuladores no MVP. |

**Um exemplo de decisão.** Se a integração simulada com a PGE-SP (dívida ativa) atrasar na Sprint 1, a equipe não estende o prazo nem adiciona horas: reduz o escopo, retirando primeiro a senha digital (RF06) da Sprint 2, porque o diagnóstico de dívida ativa é o que mais dói para o cidadão (o caso de Seu José) e precisa estar no incremento.

## 5. Objetivos de Desenvolvimento Sustentável (ONU)

| ODS | Meta | Como o Em Dia contribui |
| :--- | :--- | :--- |
| **ODS 10**, Redução das desigualdades | 10.2, promover a inclusão social, econômica e política de todos | Quem mais perde dia de trabalho em fila é quem menos pode. O pedido em linguagem simples e por voz, a senha digital e o plano explicado tiram da conta do cidadão o custo de entender a burocracia. |
| **ODS 9**, Indústria, inovação e infraestrutura | 9.c, aumentar o acesso às tecnologias de informação e comunicação | Usa a infraestrutura pública que já existe (conta gov.br, Pix e as bases dos órgãos) e a conecta; funciona em celulares básicos e conexões lentas. |
| **ODS 16**, Paz, justiça e instituições eficazes | 16.6, instituições eficazes e transparentes; 16.9, identidade legal para todos; 16.10, acesso à informação | Cada consulta é registrada e visível ao cidadão em "quem viu meus dados"; as três esferas respondem como um Estado só; regularização mais simples significa mais gente com documentos válidos e mais arrecadação recuperada. |
