# 🏛️ Em Dia: Global Solution 2026.2

> **Um pedido. Todas as pendências. Um plano.**
> A CitizenTech que descobre tudo o que trava a vida do cidadão com o governo, no município, no estado e na União, e resolve num plano só.

---

## 📌 Sobre o projeto

Hoje o cidadão descobre a pendência no guichê, depois de agendar, reunir papéis e esperar, e cada órgão resolve só a sua parte: o Poupatempo manda procurar a PGE, a PGE emite a guia, o DETRAN só conclui depois. Com o **Em Dia** ele pede uma vez (texto ou voz), vê em segundos tudo o que o impede nas três esferas, recebe um plano em linguagem simples, paga num único Pix repassado a cada órgão e, quando precisa ir ao posto, já chega com a senha.

| | |
| :--- | :--- |
| **Disciplina** | Business Systems Planning, Analysis & Design |
| **Professor** | Me. Junior Freitas de Amaral |
| **Curso / turma** | Sistemas de Informação · 2SIZ · FIAP |
| **Desafio** | CitizenTech · Global Solution 2026.2 |

---

## 👥 Equipe Em Dia

| Nome | RM |
| :--- | :---: |
| **Guilherme da Cunha** | `567633` |
| **Kenny Tanaka** | `567742` |
| **Pedro Moisés Pereira da Silva** | `567206` |

---

## 🛠️ Tecnologias e ferramentas

- **Back-end:** Java · **Banco:** Oracle · **Testes:** JUnit
- **Autenticação e pagamento:** conta gov.br · Pix
- **IA supervisionada:** interpreta o pedido e explica opções; nunca decide nem paga sozinha
- **Modelagem e prototipação:** Bizagi Modeler (BPMN 2.0) · Pencil (Evolus) · Scrum
- **Rede (simulação):** Cisco Packet Tracer · **Privacidade:** LGPD por padrão

---

## 📂 Documentos do projeto

| Etapa | Arquivo |
| :--- | :--- |
| 📄 Documento completo da entrega (capa, planejamento, processos, protótipo, storyboard e referências) | [`Em_Dia_Entrega_Final.pdf`](Em_Dia_Entrega_Final.pdf) |
| 🗂️ Planejamento do projeto: ciclo de vida, abordagem ágil, Scrum, backlog, sprints, tripla restrição e ODS | [`Planejamento_do_Projeto.md`](Planejamento_do_Projeto.md) |
| 🔁 Modelagem de processos em BPMN (como é hoje e como fica com o Em Dia) | [`Modelagem_de_Processos.md`](Modelagem_de_Processos.md) · [`Em_Dia_Modelo_Bizagi.bpm`](Modelagem_de_Processos/Em_Dia_Modelo_Bizagi.bpm) · [`.bpmn`](Modelagem_de_Processos/) |
| 📱 Protótipo das telas no Pencil | [`Prototipo_de_Telas.md`](Prototipo_de_Telas.md) · [`Em_Dia_Prototipo.epgz`](Prototipo_de_Telas/Em_Dia_Prototipo.epgz) |
| 🎬 Storyboard da jornada (oito quadros) | [`Storyboard.md`](Storyboard.md) · [`Storyboard/`](Storyboard/) |
| 🎤 Apresentação e roteiro do vídeo de pitch | [`Pitch/`](Pitch/) |

As quatro partes seguem a ordem pedida no roteiro da disciplina.

---

## 🔁 Modelagem de processos (BPMN)

**Hoje: transferência de um veículo arrematado em leilão, sem o Em Dia**

![Processo atual](Modelagem_de_Processos/Processo_atual_AS-IS.png)

**Com o Em Dia: regularização em um fluxo só**

![Processo proposto](Modelagem_de_Processos/Processo_proposto_TO-BE.png)

---

## 📱 Protótipo no Pencil

| Tela 1 · Início e pedido | Tela 2 · Autorização | Tela 3 · Diagnóstico |
| :---: | :---: | :---: |
| ![Tela 1](Prototipo_de_Telas/telas/Tela_01_Inicio@2x.png) | ![Tela 2](Prototipo_de_Telas/telas/Tela_02_Autorizacao@2x.png) | ![Tela 3](Prototipo_de_Telas/telas/Tela_03_Diagnostico@2x.png) |

| Tela 4 · Plano | Tela 5 · Pagamento único | Tela 6 · Acompanhamento |
| :---: | :---: | :---: |
| ![Tela 4](Prototipo_de_Telas/telas/Tela_04_Plano@2x.png) | ![Tela 5](Prototipo_de_Telas/telas/Tela_05_Pagamento@2x.png) | ![Tela 6](Prototipo_de_Telas/telas/Tela_06_Acompanhamento@2x.png) |

---

## 🎬 Storyboard

| | |
| :---: | :---: |
| ![1](Storyboard/Quadro_01_Leilao.png) | ![2](Storyboard/Quadro_02_Poupatempo.png) |
| ![3](Storyboard/Quadro_03_Pedido.png) | ![4](Storyboard/Quadro_04_Autorizacao.png) |
| ![5](Storyboard/Quadro_05_Diagnostico.png) | ![6](Storyboard/Quadro_06_Pix_unico.png) |
| ![7](Storyboard/Quadro_07_Documento_e_senha.png) | ![8](Storyboard/Quadro_08_Impacto.png) |

---

## 🌍 ODS

| ODS | Meta | Contribuição do Em Dia |
| :--- | :--- | :--- |
| **10** Redução das desigualdades | 10.2 | Pedido em linguagem simples e por voz, senha digital e plano explicado tiram do cidadão o custo de entender a burocracia |
| **9** Indústria, inovação e infraestrutura | 9.c | Conecta a infraestrutura pública que já existe (gov.br, Pix, bases dos órgãos); funciona em celulares básicos |
| **16** Paz, justiça e instituições eficazes | 16.6 · 16.9 · 16.10 | Cada consulta é registrada e visível ao cidadão; as três esferas respondem como um Estado só |
