# cauã.dev — Portfólio Pessoal

Este repositório contém o portfólio pessoal de **Cauã Cozzarin**, estudante de Engenharia de Software e desenvolvedor júnior com foco em backend, automação de processos (RPA) e integração entre sistemas.

O objetivo do site é reunir, em uma única página, as informações que um recrutador ou colega de área normalmente procura: quem é o desenvolvedor, onde trabalha, quais projetos já construiu, quais tecnologias domina e como entrar em contato. Tudo isso foi feito com **HTML e CSS puros**, sem frameworks, bibliotecas de componentes ou etapa de build, o que torna o projeto leve, rápido de carregar e fácil de publicar em qualquer hospedagem estática.

---

## Sumário

1. [Conceito visual](#conceito-visual)
2. [Seções da página](#seções-da-página)
3. [Tecnologias utilizadas](#tecnologias-utilizadas)
4. [Decisões técnicas de CSS](#decisões-técnicas-de-css)
5. [Acessibilidade](#acessibilidade)
6. [Responsividade](#responsividade)
7. [Estrutura de arquivos](#estrutura-de-arquivos)
8. [Como executar localmente](#como-executar-localmente)
9. [Como publicar no GitHub Pages](#como-publicar-no-github-pages)
10. [Como personalizar](#como-personalizar)
11. [Próximos passos](#próximos-passos)
12. [Contato](#contato)

---

## Conceito visual

A identidade do portfólio foi pensada a partir do ambiente de trabalho de um desenvolvedor. Em vez de usar um layout genérico de currículo, cada parte da página faz referência a algo que um programador vê no dia a dia: uma janela de terminal, um arquivo de log, um `package.json`, uma pasta de repositórios e um arquivo `.env`.

Essa escolha tem dois propósitos. O primeiro é comunicar, logo no primeiro olhar, a área de atuação do autor (backend e automação, trabalhos muito ligados ao terminal e a arquivos de configuração). O segundo é dar personalidade à página sem depender de imagens pesadas ou animações complexas.

A paleta de cores segue a mesma lógica:

| Papel | Cor | Uso |
|---|---|---|
| Fundo principal | `#0F1620` (azul-grafite) | base de toda a página, lembrando um editor em tema escuro |
| Superfícies | `#161F2C` e `#1C2734` | cards, barra do terminal e blocos de conteúdo |
| Texto principal | `#EDEAE3` | títulos e informações de destaque |
| Texto secundário | `#8B93A1` | descrições, metadados e rótulos |
| Destaque primário | `#E8A33D` (âmbar) | marcadores de seção, links de projeto e botão de contato |
| Destaque secundário | `#4FD1AE` (verde-água) | prompt do terminal, status "online", tags de tecnologia e foco |

As fontes também foram escolhidas com intenção: a **JetBrains Mono**, uma fonte monoespaçada criada para programação, é usada em títulos, menus, tags e em tudo que deve parecer "código"; a **Inter**, uma fonte sem serifa de alta legibilidade, é usada nos textos corridos, para que parágrafos longos continuem confortáveis de ler.

---

## Seções da página

### Cabeçalho e navegação

No topo da página existe uma barra de navegação fixa. Ela acompanha a rolagem, então o visitante consegue pular para qualquer seção a qualquer momento. À esquerda fica o logotipo `cauã.dev`, acompanhado de um pequeno ponto verde com brilho, que funciona como um indicador de "online". À direita ficam os links para as seções de experiência, projetos, stack e contato.

A barra tem fundo semitransparente com desfoque (`backdrop-filter: blur`), o que cria um efeito de vidro fosco: o conteúdo que passa por baixo continua levemente visível, mas não atrapalha a leitura dos links.

### Hero (apresentação)

É a primeira coisa que o visitante vê. Contém:

- uma linha de contexto em letras pequenas indicando a área de atuação (backend e automação);
- o nome em destaque, com tamanho que se adapta à largura da tela;
- um parágrafo curto resumindo o perfil profissional, com as tecnologias principais destacadas em âmbar;
- uma linha de "chips" com os meios de contato (e-mail, telefone, LinkedIn e GitHub), cada um com seu ícone em SVG.

Logo abaixo aparece uma **janela de terminal simulada**. Ela reproduz a aparência de um terminal real, com os três botões coloridos no canto superior e o caminho `~/cauacozz — zsh`. Dentro dela, uma sequência de comandos fictícios apresenta o autor de forma criativa:

- `whoami` mostra o nome e o cargo atual;
- `status --disponibilidade` indica que ele está aberto a novas oportunidades;
- `cat stack.json` lista as tecnologias principais;
- uma requisição `curl` com token retorna `200 OK`, fazendo referência ao trabalho com autenticação JWT.

Ao final da última linha há um cursor piscando, feito apenas com CSS, que reforça a sensação de um terminal ativo.

### Experiência profissional (`career.log`)

Apresenta a trajetória profissional em formato de linha do tempo vertical, como se fosse um arquivo de log. Cada entrada mostra o período, o cargo, a empresa e uma descrição das atividades.

As entradas recebem um selo de status:

- **online**, em verde, para a posição atual (Desenvolvedor Júnior na Simplifica+, desde maio de 2026);
- **arquivado**, em cinza, para posições anteriores (Estagiário Desenvolvedor RPA na Simplifica+, de julho de 2025 a abril de 2026).

O marcador circular da posição atual também ganha um anel de brilho verde, para destacar visualmente onde o autor está hoje.

### Projetos (`~/repos`)

Mostra os projetos em cards organizados em grade. Cada card imita a aparência de um repositório: tem um cabeçalho com o nome técnico do projeto e sua visibilidade (`public`), seguido do título, de uma descrição, das tecnologias usadas (em forma de tags) e de um link para o repositório no GitHub.

Os projetos apresentados são:

- **SaaS · Diário de Obra** — sistema para construtoras registrarem o andamento das obras por texto, imagem e áudio, com geração automática de relatórios em PDF. Feito com Next.js, React, TypeScript e PostgreSQL.
- **Dashboard em Python** — painel interativo para análise e visualização de dados.
- **API Clínica** — API REST em C# para gerenciamento de clínicas médicas, com foco em modelagem de dados e regras de negócio, incluindo autenticação por JWT, controle de acesso por token e proteção de rotas.

Ao passar o mouse sobre um card, ele sobe levemente e a borda muda para âmbar, indicando que é clicável.

### Stack e ferramentas (`package.json`)

Lista as tecnologias que o autor domina, agrupadas por categoria, como se fossem chaves de um arquivo JSON. As categorias são:

- **linguagens:** JavaScript, TypeScript, Python e C#;
- **backend e dados:** Node.js, APIs REST, SQL, NoSQL, tratamento de dados, análise de logs e estruturas de dados;
- **autenticação e autorização:** JWT, autorização por token, controle de acesso e proteção de rotas;
- **frontend:** React e Next.js;
- **automação:** Puppeteer e RPA;
- **ferramentas:** Git e GitHub, Docker, AWS (S3 e logs) e Insomnia.

Agrupar as tecnologias dessa forma ajuda quem está lendo a entender rapidamente em quais áreas o autor tem experiência, em vez de receber uma lista solta de nomes.

### Formação e idiomas (`profile.env`)

Dois cards lado a lado com informações complementares:

- **Formação acadêmica:** Bacharelado em Engenharia de Software pela Católica de Santa Catarina, em Jaraguá do Sul (SC), iniciado em fevereiro de 2025 e em andamento.
- **Idiomas:** português nativo e inglês intermediário, com ênfase em leitura técnica e documentação.

### Rodapé e contato

A página termina com uma chamada para ação escrita como um prompt de terminal, convidando o visitante a conversar sobre automações, APIs ou sistemas. Abaixo dela há um botão em âmbar que abre diretamente o cliente de e-mail, e uma linha com os links para GitHub, LinkedIn e telefone.

---

## Tecnologias utilizadas

- **HTML5:** responsável pela estrutura e pelo conteúdo. Foram usadas tags semânticas (`header`, `nav`, `main`, `section`, `footer`), que descrevem o papel de cada parte da página. Isso melhora a organização do código, a indexação por mecanismos de busca e a navegação por leitores de tela.
- **CSS3:** responsável por todo o visual, incluindo cores, tipografia, layout, efeitos de hover e animações.
- **Google Fonts:** fornece as fontes JetBrains Mono e Inter. A conexão com os servidores de fontes é iniciada antecipadamente com `preconnect`, o que reduz o tempo de carregamento.
- **SVG inline:** os ícones de contato são desenhados diretamente no HTML em SVG. Isso evita carregar uma biblioteca de ícones inteira para usar apenas quatro símbolos, e permite que os ícones herdem a cor do texto automaticamente (`stroke="currentColor"`).

O projeto não utiliza JavaScript. Todas as interações visíveis (hover, rolagem suave e cursor piscando) são resolvidas com CSS.

---

## Decisões técnicas de CSS

### Variáveis CSS (custom properties)

Todas as cores e fontes estão definidas uma única vez no seletor `:root` e reutilizadas no resto do arquivo por meio de `var(--nome)`. Na prática, isso significa que para trocar a cor de destaque do site inteiro basta alterar uma linha, em vez de procurar todas as ocorrências da cor no código.

### Grid e Flexbox

- **CSS Grid** é usado onde há distribuição em colunas, como a grade de projetos e os cards de formação. Na grade de projetos, a regra `repeat(auto-fit, minmax(240px, 1fr))` faz com que os cards se reorganizem sozinhos: em telas largas aparecem vários por linha e, em telas estreitas, eles vão para uma coluna, sem precisar de media query.
- **Flexbox** é usado para alinhamentos em uma única direção, como a barra de navegação, a linha de contatos, as tags de tecnologia e a barra superior do terminal.

### Tipografia fluida

O nome no topo da página usa `clamp(32px, 6vw, 52px)`. Essa função define um tamanho mínimo, um tamanho proporcional à largura da tela e um tamanho máximo. O resultado é um título que cresce e diminui suavemente conforme a tela, sem ficar pequeno demais no celular nem exagerado em monitores grandes.

### Pseudo-elementos para detalhes visuais

Vários detalhes decorativos são criados com `::before`, sem adicionar elementos extras no HTML. É o caso do quadradinho âmbar antes de cada título de seção e dos marcadores circulares da linha do tempo de experiência. Isso mantém o HTML limpo e focado no conteúdo.

### Animação do cursor

O cursor do terminal é um pequeno bloco retangular que pisca graças a uma animação `@keyframes` com a função `steps(1)`. Essa função faz a transição acontecer de forma instantânea, sem esmaecer, imitando exatamente o comportamento de um cursor real.

### Fundo com gradientes

O fundo da página tem dois gradientes radiais muito sutis, um âmbar e um verde-água, posicionados no topo. Eles criam profundidade sem usar imagens, e ficam fixos (`background-attachment: fixed`) enquanto o conteúdo rola.

### Rolagem suave

A regra `scroll-behavior: smooth` faz com que, ao clicar em um link do menu, a página deslize até a seção em vez de pular de forma brusca.

---

## Acessibilidade

Alguns cuidados foram tomados para que o portfólio possa ser usado por mais pessoas:

- **Foco visível:** ao navegar pelo teclado com a tecla Tab, o elemento selecionado recebe um contorno verde bem visível (`:focus-visible`). O contorno aparece só na navegação por teclado, sem poluir o visual para quem usa mouse.
- **Respeito à preferência por menos movimento:** usuários que configuraram o sistema operacional para reduzir animações (`prefers-reduced-motion: reduce`) não verão o cursor piscando.
- **Descrição do terminal:** como a janela de terminal é um elemento decorativo formado por vários textos soltos, ela recebe `role="img"` e um `aria-label` que resume seu conteúdo. Assim, o leitor de tela anuncia uma descrição clara em vez de ler cada linha fora de contexto.
- **Idioma declarado:** a tag `<html lang="pt-BR">` informa aos leitores de tela que o conteúdo está em português, garantindo a pronúncia correta.
- **Contraste:** o texto claro sobre o fundo escuro mantém boa legibilidade.
- **Links externos seguros:** os links que abrem em nova aba usam `rel="noopener"`, o que impede que a página aberta tenha acesso à página de origem.

---

## Responsividade

O site foi pensado para funcionar em celulares, tablets e computadores:

- O conteúdo principal fica limitado a uma largura máxima de 880px e centralizado, para que as linhas de texto não fiquem longas demais em telas grandes.
- Abaixo de **620px** de largura, os links do menu superior são ocultados para economizar espaço, e os cards de formação e idiomas passam a ficar um embaixo do outro.
- A grade de projetos se ajusta automaticamente ao espaço disponível, como explicado na seção de Grid.
- A linha de contatos usa `flex-wrap`, então os chips quebram para a linha de baixo quando não cabem lado a lado.
- A tag `meta viewport` garante que o navegador do celular exiba a página na largura correta, em vez de mostrar uma versão de desktop reduzida.

---

## Estrutura de arquivos

```
portfolio/
├── index.html    Estrutura, conteúdo e estilos da página
└── README.md     Documentação do projeto
```

Por ser uma página única e pequena, todo o CSS foi escrito dentro de uma tag `<style>` no próprio `index.html`. Isso simplifica a publicação, já que existe apenas um arquivo para enviar. Em uma evolução do projeto, o CSS pode ser movido para um arquivo `style.css` separado, o que facilita a manutenção.

---

## Como executar localmente

O projeto não tem dependências, então não é preciso instalar nada.

1. Clone o repositório:

   ```bash
   git clone https://github.com/cauacozz11/portfolio.git
   ```

2. Entre na pasta do projeto:

   ```bash
   cd portfolio
   ```

3. Abra o arquivo `index.html` em qualquer navegador moderno (Chrome, Firefox, Edge ou Safari). Basta dar dois cliques no arquivo.

Para quem for editar o código, uma opção prática é a extensão **Live Server** do VS Code. Ela abre o site em um servidor local e recarrega a página automaticamente sempre que um arquivo é salvo.

Observação: as fontes são carregadas do Google Fonts, então é preciso estar conectado à internet para que elas apareçam. Sem conexão, o navegador usa as fontes alternativas definidas no CSS (Courier New e a fonte padrão do sistema).

---

## Como publicar no GitHub Pages

O GitHub Pages hospeda sites estáticos gratuitamente a partir de um repositório.

1. Envie o projeto para um repositório público no GitHub.
2. No repositório, acesse **Settings** e depois **Pages**, no menu lateral.
3. Em **Source**, escolha **Deploy from a branch**.
4. Selecione a branch `main` e a pasta `/ (root)`, e clique em **Save**.
5. Aguarde alguns instantes. O endereço público aparecerá no topo da mesma página, no formato `https://cauacozz11.github.io/portfolio`.

É importante que o arquivo principal se chame exatamente `index.html`, pois é ele que o GitHub Pages abre por padrão.

---

## Como personalizar

### Alterar cores e fontes

Todas as cores e fontes ficam no início do CSS, dentro do `:root`:

```css
:root {
  --bg: #0F1620;          /* fundo principal */
  --surface: #161F2C;     /* fundo dos cards */
  --text: #EDEAE3;        /* texto principal */
  --text-muted: #8B93A1;  /* texto secundário */
  --amber: #E8A33D;       /* cor de destaque primária */
  --teal: #4FD1AE;        /* cor de destaque secundária */
  --mono: 'JetBrains Mono', 'Courier New', monospace;
  --sans: 'Inter', -apple-system, sans-serif;
}
```

Alterar um desses valores muda automaticamente todos os elementos que usam aquela variável.

### Adicionar um novo projeto

Dentro da seção `<section id="projetos">`, copie um bloco inteiro de `.proj-card` e altere as informações:

```html
<div class="proj-card">
  <div class="proj-head"><span>nome_tecnico</span><span>public</span></div>
  <div class="proj-body">
    <div class="proj-title">Nome do Projeto</div>
    <div class="proj-desc">Descrição curta do que o projeto faz.</div>
    <div class="proj-stack">
      <span class="tag">Tecnologia 1</span><span class="tag">Tecnologia 2</span>
    </div>
    <a class="proj-link" href="https://github.com/usuario/repositorio" target="_blank" rel="noopener">
      ver repositório →
    </a>
  </div>
</div>
```

A grade se reorganiza sozinha para acomodar o novo card.

### Adicionar uma nova experiência

Dentro da `<div class="log">`, na seção de experiência, adicione um novo bloco `.log-entry`. Para marcar como posição atual, use a classe `log-entry active` e o selo `status-pill online`; para posições anteriores, use apenas `log-entry` e o selo `status-pill archived`.

### Adicionar uma tecnologia

Na seção de stack, localize o grupo desejado e adicione mais um `<span class="pill">Nome</span>` dentro da `.pill-row` correspondente.

---
## Contato

- **E-mail:** [cauacozz@gmail.com](mailto:cauacozz@gmail.com)
- **LinkedIn:** [linkedin.com/in/caua-cozzarin](https://linkedin.com/in/caua-cozzarin)
- **GitHub:** [github.com/cauacozz11](https://github.com/cauacozz11)
