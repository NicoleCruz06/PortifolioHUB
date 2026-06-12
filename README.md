# PortfolioHUB | Nicole Cruz
> **Status da Entrega:** Concluído & Publicado em Produção   

---

## O Projeto

* **Instituição:** Centro Universitário de Brasília (CEUB)
* **Curso:** Ciência de Dados e Machine Learning
* **Disciplina:** Bootcamp
* **Período:** 1º Semestre / 2026
* **Estudante:** Nicole Viana Cruz  

### Descrição do Projeto
O **PortfolioHUB** é uma plataforma centralizada projetada para exibir e gerenciar projetos, competências e portfólios digitais de forma dinâmica e elegante[cite: 1]. A arquitetura da aplicação foi concebida sob os pilares de **segurança da informação por design**, **experiência do utilizador (UX)** e **governança de dados**, atuando como um ecossistema integrado que conecta o desenvolvimento estático moderno às soluções em nuvem corporativas[cite: 1].

---

## 1. Planejamento e Trilha de Implantação (Fase 1)
O processo de implantação do **PortfolioHUB** foi estruturado seguindo as melhores práticas de gerenciamento de ciclo de vida de software (SDLC), contando com a inteligência artificial **Google GEMINI** como guia consultivo estratégico e co-piloto de engenharia. 

Abaixo, detalha-se a trilha metodológica planejada e executada para garantir a conformidade com os requisitos técnicos do projeto:

### Cronograma e Atividades da Trilha de Implantação
1. **Fase 1: Configuração do Ambiente e Repositório**
   * **Ação:** Criação do ambiente dedicado no GitHub, inicialização do controle de versão local via Git e estruturação das pastas do projeto.
   * **Papel do Google GEMINI:** Atuou na recomendação da estrutura de diretórios mais eficiente para páginas estáticas e validação dos comandos iniciais de versionamento.

2. **Fase 2: Integração e Armazenamento Dinâmico**
   * **Ação:** Vinculação dos repositórios de projetos reais ao PortfolioHUB e estruturação das requisições lógicas em JavaScript para renderização dinâmica dos cards.
   * **Papel do Google GEMINI:** Auxílio na lógica de paginação do carrossel e no cálculo matemático dinâmico para exibição dos projetos por página.

3. **Fase 3: Engenharia de Segurança (Autenticação SHA-256)**
   * **Ação:** Implementação do ecossistema de login administrativo utilizando criptografia baseada em hardware no navegador através da Web Crypto API.
   * **Papel do Google GEMINI:** Forneceu as diretrizes para mitigar a exposição de chaves e senhas em texto limpo (*Plain Text*) no código público do GitHub, sugerindo o uso de hashes SHA-256 e controle de ciclo de vida via `sessionStorage`.

4. **Fase 4: Integração Google Workspace & Governança de Dados**
   * **Ação:** Substituição dos dados de contato vulneráveis por um formulário embutido (*embed*) do Google Forms para contenção de spams[cite: 1].
   * **Papel do Google GEMINI:** Identificação do risco de segurança ligado a ataques de *Web Scraping* (colheita de e-mails brutos por robôs) e recomendação de arquitetura usando o ecossistema Google para anonimização e auditoria em banco de dados seguro (Google Sheets)[cite: 1].

5. **Fase 5: Ciclo de Testes e Ajustes Finais**
   * **Ação:** Execução de testes de caixa preta para segurança, refatoração do CSS para responsividade móvel com propriedades de alinhamento e inserção da lógica `scrollIntoView`[cite: 1].
   * **Papel do Google GEMINI:** Apoio na depuração do código JavaScript para garantir rolagem de tela suave (UX) e comportamento responsivo do grid[cite: 1].

---

## 2. Configuração Inicial e Integração com GitHub
* **Ambiente Dedicado:** Repositório criado e configurado sob controle de versão Git no ecossistema GitHub[cite: 1].
* **Armazenamento Dinâmico:** Integração das funcionalidades de gerenciamento do GitHub para distribuição automatizada de código.
* **Link da Aplicação em Produção:** [Acesse o PortfolioHUB aqui](https://nicolecruz06.github.io/PortifolioHUB/)

---

## 3. Gestão de Usuários, Segurança e Google Workspace
Para atender rigorosamente aos critérios de robustez de segurança, foram implementados dois protocolos principais validados via Google GEMINI[cite: 1]:

### A. Autenticação Restrita com Protocolo SHA-256 (Client-Side)
* **Vulnerabilidade Mitigada:** Exposição de credenciais administrativas em texto limpo (*Plain Text*) no código-fonte, visíveis via inspeção de elementos do navegador.
* **Solução Aplicada:** Criação de uma interface de login em **Modal flutuante** conectada à **Web Crypto API**. O sistema realiza a validação de segurança comparando o hash criptográfico dinâmico **SHA-256** das credenciais digitadas, impedindo engenharia reversa.
* **Persistência Segura:** Uso de `sessionStorage` para controle de sessão, destruindo os privilégios administrativos automaticamente ao fechar a aba.

### B. Integração com Google Workspace & Proteção Antispam
* **Vulnerabilidade Mitigada:** Colheita automatizada de dados por robôs (*Web Scraping*) para a disseminação de campanhas de phishing e spam em e-mails institucionais expostos de forma bruta na tela.
* **Solução Aplicada:** Remoção completa de e-mails em texto limpo do cabeçalho e do rodapé. Implementação de um canal centralizado de **Contacto & Feedback** embutido nativamente via **Google Forms** (Google Workspace)[cite: 1].
* **Governança de Dados:** Todas as mensagens de recrutadores e avaliações quantitativas de usabilidade são processadas pelo ecossistema Google e consolidadas em uma planilha protegida do Google Sheets para auditoria[cite: 1].

---

## 4. Tabela de Casos de Teste (Fase 5)
Abaixo constam os três cenários de testes fundamentais executados para garantir a estabilidade e a segurança da aplicação antes do lançamento real[cite: 1]:

| ID | Categoria | Descrição do Teste | Entrada (Input) | Resultado Esperado | Status |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **TC-01** | **Segurança** | Tentativa de login administrativo com credenciais incorretas. | Usuário: `admin`<br>Senha: `errada` | Bloquear acesso, exibir alerta e registrar aviso de segurança encriptado no console. | **Aprovado** |
| **TC-02** | **Integração Workspace** | Envio de Contacto e avaliação de usabilidade sem expor dados. | Motivo: `Proposta`<br>Nota Usabilidade: `5` | Transmitir os dados de forma segura, salvando-os direto no Google Sheets. | **Aprovado** |
| **TC-03** | **Interface (UX)** | Validação de navegação de projetos com carrossel dinâmico. | Clique nas setas esquerda/direita. | Rotacionar cards centralizados no grid e executar rolagem suave (`scrollIntoView`) para manter o foco ativo. | **Aprovado** |

---

## 🛠️ Tecnologias Utilizadas
* HTML5 / CSS3 / JavaScript (ES6+)
* Web Crypto API (Algoritmo Criptográfico SHA-256)
* Git & GitHub Pages (Controle de Versão e Hospedagem)[cite: 1]
* Google Workspace (Google Forms & Google Sheets como camada de dados)[cite: 1]
* Google GEMINI (Engenharia de Prompt e Apoio Consultivo)[cite: 1]

---

## Contato e Conexões

* **LinkedIn:** [https://www.linkedin.com/in/nicole-viana-cruz-b609ab40b/]
* **Portfólio Online:** [https://nicolecruz06.github.io/PortifolioHUB/]
