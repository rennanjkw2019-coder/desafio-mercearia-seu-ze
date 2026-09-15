# 🛒 Desafio Mercearia do Seu Zé

Presença digital da **Mercearia do Seu Zé** — mercearia tradicional com mais de 40 anos no Centro Histórico de Curitiba.

Projeto acadêmico de **HTML5 + Git/GitHub** desenvolvido a partir do estudo de caso proposto em aula.

👥 **Integrantes:** Rennan Jackowski Pereira · Paulo Geandre Pinto  
🎓 **Curso:** Análise e Desenvolvimento de Sistemas — Universidade Positivo

🔗 **Site publicado:** https://rennanjkw2019-coder.github.io/desafio-mercearia-seu-ze/

---

##  Passo 1 — Definição do objetivo

### Objetivo principal da página

Criar a **presença digital oficial da Mercearia do Seu Zé no Google**, garantindo que o estabelecimento seja encontrado por quem pesquisa por mercados, produtos coloniais e conveniência no Centro de Curitiba.

A página funciona como um **cartão de visitas digital**: rápido, informativo e confiável. Não é um e-commerce — o objetivo não é vender on-line, e sim **fazer o cliente novo descobrir a loja e ir até ela** (ou chamar no WhatsApp).

Isso respeita as duas condições impostas pelo Seu Zé:

- **Não custa uma fortuna:** uma única página estática, sem banco de dados, sem mensalidade de plataforma. Hospedagem gratuita no GitHub Pages.
- **Não muda o jeito dele trabalhar:** o atendimento continua sendo olho no olho, na loja. O site só leva gente até a porta.

### Público-alvo do site

**Público primário — jovens adultos digitais do Centro (18 a 35 anos)**

- Universitários, jovens profissionais e novos moradores de apartamentos funcionais do Centro e do Alto da XV.
- Passam todo dia na calçada da mercearia, mas olhando para a tela do celular.
- **Comportamento decisivo:** pesquisam no Google/Google Maps *antes* de sair de casa. Se o comércio não existe na internet, para eles ele simplesmente não existe.
- **O que procuram:** "mercado perto de mim", "mercearia Centro Curitiba", "onde comprar queijo colonial em Curitiba", horário de funcionamento e se dá para chamar no WhatsApp.
- **Acesso:** majoritariamente pelo **celular** → por isso o layout é responsivo e pensado primeiro para tela pequena.

**Público secundário — filhos e netos dos clientes antigos (35 a 60 anos)**

- Não compram para si: buscam informação **em nome dos pais e avós** que moram há décadas no Centro.
- Querem resolver rápido: confirmar horário, endereço e telefone para orientar ou acompanhar um familiar idoso.
- Por isso as informações de contato e horário aparecem **logo no topo**, sem precisar rolar a página.

> **Observação importante:** o público-alvo do *site* não é o mesmo público-alvo da *loja hoje*. A clientela fiel atual (senhoras e senhores do bairro) continua sendo atendida no balcão, como sempre foi. O site existe justamente para alcançar quem **ainda não entra** na mercearia.

### As 3 informações essenciais na tela

| # | Informação | Por que é essencial | Onde está na página |
|---|---|---|---|
| 1 | **Endereço completo + ponto de referência**, com indicação de localização no mapa | Resolve o problema central: hoje a loja não aparece em busca nenhuma. Sem endereço localizável, não há visita. | Faixa de destaque no topo + seção "Onde estamos" com `<address>` e mapa incorporado |
| 2 | **Horário de funcionamento** atualizado, semana e fim de semana | É a informação nº 1 pesquisada antes de sair de casa. Dúvida sobre horário = cliente que não vem. | Faixa de destaque no topo + tabela completa na seção "Horário de atendimento" |
| 3 | **Canais de contato direto** (WhatsApp e telefone fixo) **+ lista de produtos e promoções** | O WhatsApp aproxima o público jovem sem exigir sistema novo do Seu Zé. A lista de produtos mostra o diferencial (coloniais) que ninguém vê da calçada. | Faixa de destaque no topo, seção "Produtos e promoções" (tabela + lista) e seção "Fale com a gente" |

### Requisito extra do Seu Zé

Currículo e perfil profissional dos desenvolvedores neste `README.md` — veja a seção [👥 Quem desenvolveu](#-quem-desenvolveu).

---

##  Passo 2 — Arquitetura da informação e wireframe

Wireframe de baixa fidelidade definido antes de escrever qualquer código:

```
┌──────────────────────────────────────────────┐
│               🛒 LOGO / NOME                  │  ← CABEÇALHO
│        Mercearia do Seu Zé                    │
│    "Tradição em cada prateleira desde 1982"   │
├──────────────────────────────────────────────┤
│  Sobre │ Produtos │ Local │ Horários │ Contato│  ← MENU
├──────────────────────────────────────────────┤
│ ┌──────────┐ ┌──────────┐ ┌──────────┐       │
│ │📍ENDEREÇO│ │🕗HORÁRIO │ │💬CONTATO │       │  ← 3 INFOS ESSENCIAIS
│ │ Rua XV   │ │ 8h-19h   │ │ WhatsApp │       │     (sem rolar a tela)
│ └──────────┘ └──────────┘ └──────────┘       │
├──────────────────────────────────────────────┤
│  BEM-VINDO À NOSSA MERCEARIA                  │
│  Texto de apresentação da loja e da           │  ← CONTEÚDO
│  história de mais de 40 anos.                 │
├──────────────────────────────────────────────┤
│  PRODUTOS E PROMOÇÕES DA SEMANA               │
│  ┌────────────┬────────────┬────────┐        │
│  │ Produto    │ Descrição  │ Preço  │        │  ← TABELA
│  ├────────────┼────────────┼────────┤        │
│  │ Café       │ 500 g      │ R$ ... │        │
│  └────────────┴────────────┴────────┘        │
│  • Hortifruti  • Frios  • Padaria ...         │  ← LISTA
├──────────────────────────────────────────────┤
│  ONDE ESTAMOS                                 │
│  ┌───────────────┐  ┌───────────────┐        │
│  │ Endereço      │  │     MAPA      │        │
│  │ Referência    │  │   (Google)    │        │
│  │ [Ver no Maps] │  │               │        │
│  └───────────────┘  └───────────────┘        │
├──────────────────────────────────────────────┤
│  HORÁRIO DE ATENDIMENTO                       │
│  Tabela: dia | abertura | fechamento          │
├──────────────────────────────────────────────┤
│  FALE COM A GENTE                             │
│  [Chamar no WhatsApp]   [Ligar agora]         │
├──────────────────────────────────────────────┤
│  © 2026 · Instagram · Facebook · WhatsApp     │  ← RODAPÉ
└──────────────────────────────────────────────┘
```

### Hierarquia visual — o que chama atenção primeiro

1. **Nome da loja + slogan** (fundo verde escuro, alto contraste): identidade imediata.
2. **Faixa com as 3 informações essenciais** (cartões claros sobre fundo areia, borda laranja): quem só quer o endereço, o horário ou o telefone resolve em **menos de 5 segundos, sem rolar a página**. Essa foi a decisão de layout mais importante do projeto.
3. **Botões de ação** (WhatsApp em verde vivo): os únicos elementos em cor saturada fora do topo, para puxar o clique.
4. **Tabela de promoções**: cabeçalho verde e preços em laranja, escaneável.

No celular as colunas empilham automaticamente e a ordem vira exatamente a ordem de prioridade acima.

---

##  Justificativa da solução escolhida

| Decisão | Por quê |
|---|---|
| **Página única (landing page)** em vez de site com várias páginas | O cliente precisa de 3 informações. Espalhar isso em várias páginas aumentaria o custo e o abandono. Uma página = um scroll = zero cliques até a informação. |
| **HTML5 semântico** (`header`, `nav`, `main`, `section`, `address`, `footer`, `time`) | Além de ser o conteúdo da disciplina, tags semânticas são lidas por buscadores e leitores de tela — ajudam diretamente no objetivo de aparecer no Google. |
| **CSS embutido no próprio `index.html`** | Entrega de arquivo único, abre com duplo clique em qualquer computador, sem dependência externa. Mantém o projeto simples como o Seu Zé pediu. |
| **Dados estruturados `schema.org/GroceryStore` (JSON-LD)** | É o que permite ao Google exibir **endereço, telefone e horário direto no resultado de busca e no Maps**. Custo zero e ataca o problema central do caso. |
| **Layout responsivo (mobile first)** | O público-alvo pesquisa no celular na calçada. Um site quebrado no celular não resolveria nada. |
| **Links `wa.me` e `tel:`** | Um toque abre a conversa ou a ligação. Aproxima o jovem sem exigir que o Seu Zé aprenda sistema novo. |
| **Sem carrinho / sem e-commerce** | O Seu Zé é resistente a tecnologia e não teria como operar pedidos on-line. O WhatsApp faz a ponte usando algo que ele já entende: conversa. |
| **Zero custo de hospedagem** (GitHub Pages) | Atende à condição "não pode custar uma fortuna". |

---

## 🗂️ Estrutura do projeto

```
desafio-mercearia-seu-ze/
├── index.html    → página completa (HTML5 semântico + CSS embutido)
├── README.md     → este arquivo: análise, justificativa e currículos
└── .gitignore    → arquivos ignorados pelo Git
```

## 🛠️ Tecnologias utilizadas

- **HTML5** com tags semânticas
- **CSS3** — Flexbox, variáveis CSS e media queries
- **JSON-LD / schema.org** para SEO local
- **Git** e **GitHub** para versionamento

## ▶️ Como visualizar

1. Clone o repositório:
   ```bash
   git clone https://github.com/rennanjkw2019-coder/desafio-mercearia-seu-ze.git
   ```
2. Abra o arquivo `index.html` no navegador (duplo clique já funciona).

---

## 👥 Quem desenvolveu

> Conforme solicitado pelo Seu Zé e pelo Lucas, esta seção apresenta o perfil profissional da dupla responsável pelo projeto.

### Rennan Jackowski Pereira

**Formação atual:** Análise e Desenvolvimento de Sistemas — Universidade Positivo

**Competências técnicas em desenvolvimento:**
- HTML5 semântico e estruturação de páginas
- CSS3: Flexbox, responsividade e variáveis
- Versionamento com Git (branches, commits organizados) e GitHub
- Lógica de programação e boas práticas de código legível

**Perfis profissionais:**
- GitHub: [@rennanjkw2019-coder](https://github.com/rennanjkw2019-coder)

**Motivação:**
Escolhi tratar este desafio como um problema de negócio, não apenas como um exercício de código. Antes de escrever a primeira tag, analisei quem é o cliente do Seu Zé hoje, quem ele precisa alcançar e qual é a menor solução possível que resolve isso sem quebrar a rotina de uma loja com 40 anos de história. Entrego uma página enxuta, rápida e pensada para ser encontrada no Google — porque o problema da mercearia não é falta de qualidade, é falta de visibilidade.

---

### Paulo Geandre Pinto

**Formação atual:** Análise e Desenvolvimento de Sistemas — Universidade Positivo

**Competências técnicas em desenvolvimento:**
- HTML5 semântico e acessibilidade básica
- CSS3 e construção de layouts responsivos
- Git e GitHub: fluxo de commits, push e colaboração em dupla
- Organização de conteúdo e arquitetura da informação

**Perfis profissionais:**
- GitHub: [@paulogeandre](https://github.com/paulogeandre)

**Motivação:**
Acredito que um bom site começa no papel. Participei da definição do público-alvo e do wireframe que organizou a hierarquia da página, garantindo que as três informações essenciais aparecessem antes de qualquer rolagem. Meu compromisso neste projeto foi com a clareza: qualquer pessoa, de qualquer idade, precisa achar o endereço, o horário e o contato da mercearia em poucos segundos.

---

## 📅 Status da entrega

- [x] Passo 1 — Definição do objetivo, público-alvo e informações essenciais
- [x] Passo 2 — Arquitetura da informação e wireframe
- [x] Passo 3 — Estrutura em HTML5 semântico
- [x] Passo 4 — Versionamento com Git e GitHub
- [x] Passo 5 — Entrega do repositório com `index.html` e `README.md`

---

<p align="center">
  Projeto acadêmico — <strong>Mercearia do Seu Zé</strong><br>
  Unindo 40 anos de tradição do comércio curitibano à nova geração. 🛒
</p>
