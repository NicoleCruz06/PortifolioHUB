# PortfolioHUB | Nicole Cruz
> **Status da Entrega:** Concluído & Publicado em Produção  
> **Data de Entrega:** 14/06/2026  

---

## O Projeto

* **Instituição:** Centro Universitário de Brasília (CEUB)
* **Curso:** Ciência de Dados e Machine Learning
* **Disciplina:** Bootcamp
* **Período:** 1º Semestre / 2026
* **Estudante:** Nicole Viana Cruz  

### Descrição do Projeto
O **PortfolioHUB** é uma plataforma centralizada projetada para exibir e gerenciar projetos, competências e portfólios digitais de forma dinâmica e elegante. A arquitetura da aplicação foi concebida sob os pilares de **segurança da informação por design (Security by Design)**, **experiência do utilizador (UX)**, **conformidade legal** e **governança de dados**, atuando como um ecossistema integrado que conecta o desenvolvimento estático moderno às soluções em nuvem corporativas.

---

## 1. Planejamento e Trilha de Implantação (Fase 1)
O processo de implantação do PortfolioHUB foi estruturado seguindo as melhores práticas de gerenciamento de ciclo de vida de software (SDLC), contando com a inteligência artificial **Google GEMINI** como guia consultivo estratégico e co-piloto de engenharia em todas as tomadas de decisão técnica.

Abaixo, detalha-se a trilha metodológica planejada e executada:

*   **Fase 1: Configuração do Ambiente e Repositório**
    *   *Ação:* Criação do ambiente dedicado no GitHub, inicialização do controle de versão local via Git e estruturação das pastas do projeto.
    *   *Apoio GEMINI:* Recomendação da estrutura de diretórios mais eficiente para páginas estáticas e validação dos comandos iniciais de versionamento.
*   **Fase 2: Integração e Armazenamento Dinâmico**
    *   *Ação:* Vinculação dos repositórios de projetos reais ao PortfolioHUB e estruturação das requisições lógicas em JavaScript para renderização dinâmica dos cards.
    *   *Apoio GEMINI:* Auxílio na lógica de paginação do carrossel e no cálculo matemático dinâmico para exibição proporcional de itens por tela.
*   **Fase 3: Engenharia de Segurança (Autenticação SHA-256 & DevOps)**
    *   *Ação:* Implementação do ecossistema de login administrativo via Web Crypto API e configuração de travas de governança no repositório remoto.
    *   *Apoio GEMINI:* Diretrizes para mitigar a exposição de credenciais em texto limpo (*Plain Text*), sugerindo o uso de hashes SHA-256, persistência via `sessionStorage` e proteção de ramificações (*Branch Protection*).
*   **Fase 4: Integração Google Workspace, Compliance & Governança**
    *   *Ação:* Substituição de e-mails públicos expostos por formulário do Google Forms e desenvolvimento de barreira nativa de privacidade (LGPD).
    *   *Apoio GEMINI:* Identificação do risco de ataques de *Web Scraping* (colheita de e-mails por robôs) e orientação arquitetural para conformidade legal com a LGPD e centralização de banco de dados seguro (Google Sheets).
*   **Fase 5: Ciclo de Testes e Ajustes Finais**
    *   *Ação:* Execução de testes de caixa preta para segurança, refatoração do CSS para responsividade móvel com propriedades de alinhamento e inserção da lógica `scrollIntoView`.
    *   *Apoio GEMINI:* Apoio na depuração do código JavaScript para garantir rolagem de tela suave (UX) e comportamento responsivo do grid.

---

## 2. Configuração Inicial e Governança no GitHub (Fase 2)
*   **Ambiente e Hospedagem:** Repositório criado e configurado sob controle de versão Git no ecossistema GitHub, com deploy automatizado via **GitHub Pages**.
*   **Link da Aplicação em Produção:** [Acesse o PortfolioHUB aqui](https://nicolecruz06.github.io/PortifolioHUB/)
*   **Branch Protection Rules (DevOps):** Configuração de regras estritas na branch principal (`main`), bloqueando commits diretos e protegendo o código contra *Force Push*. Toda e qualquer alteração em produção exige obrigatoriamente a abertura e aprovação de um fluxo formal de *Pull Request* para auditoria.
*   **Supply Chain Security (Segurança da Cadeia de Suprimentos):** Ativação do **GitHub Dependabot** para análise estática e contínua do repositório, garantindo varreduras automatizadas contra vulnerabilidades conhecidas em scripts ou dependências de terceiros.

---

## 3. Gestão de Usuários, Segurança e Google Workspace (Fases 3 e 4)

### A. Autenticação Restrita com Protocolo SHA-256 (Client-Side)
*   **Vulnerabilidade Mitigada:** Exposição de credenciais administrativas em texto limpo no código-fonte, visíveis via inspeção de elementos do navegador.
*   **Solução Aplicada:** Interface de login em modal conectada à **Web Crypto API**. O sistema realiza a validação comparando o hash criptográfico dinâmico **SHA-256** das credenciais digitadas, impedindo engenharia reversa.
*   **Persistência Segura:** Uso de `sessionStorage` para controle de sessão, destruindo os privilégios administrativos automaticamente ao fechar a aba.

### B. Integração com Google Workspace & Proteção Antispam
*   **Vulnerabilidade Mitigada:** Captura automatizada de dados por robôs maliciosos (*Web Scraping*) para a disseminação de campanhas de phishing e spam em e-mails expostos.
*   **Solução Aplicada:** Remoção completa de e-mails em texto limpo do layout. Implementação de canal centralizado de contato embutido nativamente via **Google Forms**.
*   **Governança de Dados:** Todas as mensagens de recrutadores e avaliações quantitativas de usabilidade são enviadas de forma segura e consolidadas em tempo real em uma planilha protegida do **Google Sheets** (banco de dados auxiliar).

### C. Conformidade Legal com a LGPD
*   **Solução Aplicada:** Implementação de um banner nativo de consentimento de privacidade e aviso de coleta de dados em estrita conformidade com a Lei Geral de Proteção de Dados (LGPD).
*   **Persistência de Escolha:** Utilização de lógica em JavaScript com `localStorage` para registrar o consentimento do usuário, evitando a reexibição incômoda do aviso em acessos futuros na mesma máquina.

---

## 4. Arquitetura da Solução e Estrutura de Código
A interface foi projetada utilizando **HTML5 estrutural** e **CSS3 responsivo** sob o modelo de Single Page Application (SPA) híbrida.
*   **Grid Dinâmico no CSS:** Uso de `display: grid` com `justify-content: center` no container de projetos, garantindo que os cards permaneçam centralizados de forma harmônica independentemente da resolução da tela ou da quantidade de itens atuais.
*   **Lógica de Foco (UX):** Inclusão da propriedade dinâmica `scrollIntoView({ behavior: 'smooth' })` atrelada aos botões do carrossel, forçando o navegador a reajustar o foco visual suavemente a cada transição de página.
*   **Automação de Notificações:** A arquitetura prevê o acoplamento de gatilhos via **Webhooks** conectados ao banco de dados do Google Sheets, permitindo o disparo automatizado de alertas de novos leads de recrutamento.

---

## 5. Tabela de Casos de Teste (Fase 5)
Abaixo constam os cenários de testes fundamentais executados para garantir a estabilidade, conformidade legal e segurança da aplicação antes do lançamento real:

| ID | Categoria | Descrição do Teste | Entrada (Input) | Resultado Esperado | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-01** | **Segurança** | Tentativa de login administrativo com credenciais incorretas. | Usuário: `admin`<br>Senha: `errada` | Bloquear acesso, exibir alerta e registrar aviso de segurança encriptado no console. | **Aprovado** |
| **TC-02** | **Integração & Dados** | Envio de contato e avaliação de usabilidade sem expor dados. | Motivo: `Proposta`<br>Nota Usabilidade: `5` | Transmitir os dados de forma segura, salvando-os direto no Google Sheets e disparando a automação. | **Aprovado** |
| **TC-03** | **Compliance (LGPD)** | Validação da persistência do banner de consentimento de privacidade. | Clique em "Aceitar e Continuar". | Ocultar o banner com efeito fluido e gravar o registro de aceitação no `localStorage` do navegador. | **Aprovado** |

---

## Tecnologias Utilizadas
*   **HTML5 / CSS3 / JavaScript (ES6+):** Estruturação, estilização responsiva e lógica de comportamento client-side.
*   **Web Crypto API & LocalStorage:** Processamento criptográfico do algoritmo SHA-256 e controle de persistência de dados local.
*   **Git & GitHub (Pages/Dependabot):** Controle de versão granular, hospedagem em nuvem, regras de Branch Protection e varredura de vulnerabilidades em dependências.
*   **Google Workspace (Forms & Sheets):** Camada serverless de banco de dados e captação segura de formulários.
*   **Google GEMINI:** Inteligência artificial consultiva configurada para engenharia de prompt e apoio na governança do projeto.

---

## Contato e Conexões

* **LinkedIn:** [https://www.linkedin.com/in/nicole-viana-cruz-b609ab40b/]
* **Portfólio Online:** [https://nicolecruz06.github.io/PortifolioHUB/]
