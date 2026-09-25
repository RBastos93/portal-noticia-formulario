# Meu Portal de Notícias — Formulários

Ampliação do Portal de Notícias com a criação de **formulários HTML** e novas
páginas internas para as publicações. Nesta etapa os formulários têm finalidade
**visual e didática** — as informações enviadas ainda não são armazenadas, pois
não utilizamos JavaScript ou backend.

## Estrutura do projeto

```
portal-noticia-formulario/
├── index.html                  # Página inicial: filtro de notícias + publicações
├── hobbies.html                # Galeria + formulário de sugestão de temas
├── perfil.html                 # Página "Sobre Mim"
├── contato.html                # Formulário de contato completo
├── README.md
├── noticias/
│   ├── noticia-html.html        # Notícia completa + formulário de avaliação
│   └── noticia-banco-dados.html # Notícia completa + formulário de avaliação
├── css/
│   ├── reset.css               # Normalização entre navegadores
│   ├── global.css              # Variáveis, cabeçalho, menu, botões e base dos formulários
│   ├── styles.css              # Página inicial (filtro + cards)
│   ├── hobbies.css             # Página de hobbies e perfil
│   ├── contato.css             # Página de contato
│   └── noticia.css             # Páginas internas de notícia
└── img/
    ├── noticias/
    └── hobbies/
```

## O que foi implementado

### 1. Filtro de notícias (index.html)
- Campo de pesquisa `input type="search"`.
- Dois `select`: **categoria** e **tecnologia**.
- Botão `type="submit"` com o texto **Filtrar notícias**.
- Como é uma consulta, o formulário usa `method="get"`.
- Todos os campos possuem `label` associado por `for`/`id`.

### 2. Páginas completas das notícias (pasta `noticias/`)
Cada publicação da página inicial possui o link **Ler mais...** apontando para a
notícia correspondente. Cada página interna apresenta categoria, título,
subtítulo, data, imagem com texto alternativo, legenda, conteúdo completo, link
de volta à página inicial e um **formulário de avaliação** no rodapé com:
- Nome (`input type="text"`, `required`, `minlength`, `maxlength`);
- Nota de 1 a 5 estrelas com `radio` agrupados em `fieldset`/`legend`;
- Comentário em `textarea` (`required`, `minlength`, `maxlength`);
- Botão **Salvar avaliação**.

### 3. Formulário de sugestão (hobbies.html)
Nome, tema sugerido, seleção de assunto (`select`), interesses (`checkbox` de
múltipla escolha) e comentário (`textarea` com limite de caracteres).

### 4. Formulário de contato ampliado (contato.html)
Mantém nome, e-mail e mensagem e acrescenta novos tipos de campo:
`tel`, `url`, `date`, `number`, `color`, `range` (com `output`), `radio`
(forma de contato preferida), `checkbox` (assuntos) e `file` com o atributo
`accept=".png,.jpg,.jpeg,.pdf"`. Por conter envio de arquivo, o `form` usa
`enctype="multipart/form-data"`.

### 5. Requisitos comuns a todos os formulários
`form` com `action` e `method`, labels visíveis associados por `for`/`id`,
atributo `name` nos controles, tipos de campo adequados, botões com `type`,
validações nativas (`required`, `minlength`, `maxlength`, `pattern`, `min`,
`max`), estados de foco visíveis (`:focus-visible`) e layout responsivo.

### 6. Estilização
Identidade visual do portal organizada em variáveis CSS, Flexbox, `gap`,
medidas relativas, `max-width`, `margin: 0 auto`, `box-sizing`, media queries e
pseudoclasses `:hover`, `:focus` e `:focus-visible`.

### 7. Navegação
Menu presente em todas as páginas com os itens **Programação**, **Hobbies**,
**Sobre Mim** e **Contato**. O link da página atual usa `aria-current="page"`.
Nas páginas dentro de `noticias/`, os caminhos usam `../` para voltar à raiz.

## Como visualizar
Abra o arquivo `index.html` no navegador e navegue pelo menu. Teste os campos
dos formulários para observar o comportamento das validações nativas.
