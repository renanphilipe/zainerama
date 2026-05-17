# Zainerama

Site institucional para estúdio de branding e criação de logos, com painel administrativo integrado e banco de dados em nuvem via Supabase.

---

## Tecnologias

- **HTML/CSS/JS** puro — sem frameworks, sem dependências npm
- **Supabase** — banco de dados e storage de imagens na nuvem
- **Google Fonts** — Bebas Neue, Syne, Inter

---

## Funcionalidades

- Carrossel de portfólio infinito com grupos personalizáveis
- Painel admin protegido por senha
- Edição inline de imagens (hero, logo, avatares, portfólio)
- Link de contato (WhatsApp) configurável
- Lightbox para visualização de imagens
- Layout responsivo (mobile/desktop)
- Sessão admin persistente por aba (sessionStorage)

---

## Estrutura do Supabase

### Tabela — `zainerama_config`

Armazena todas as configurações do site como pares chave/valor.

### Chaves armazenadas

| Chave      | Tipo     | Descrição                                 |
|------------|----------|-------------------------------------------|
| `pw`       | string   | Senha do painel admin                     |
| `siteUrl`  | string   | Link dos botões "Fale Conosco"            |
| `heroImg`  | string   | URL da imagem principal (hero)            |
| `logoImg`  | string   | URL do logo da marca                      |
| `avatars`  | JSON     | Array com URLs dos 3 avatares             |
| `groups`   | JSON     | Array de grupos do portfólio com imagens  |

### Storage — bucket `portfolio`

Bucket público para hospedar as imagens do portfólio.

```
portfolio/
├── logos/
│   ├── logo-01.jpg
│   └── logo-02.jpg
├── branding/
│   ├── brand-01.jpg
│   └── brand-02.jpg
├── hero.jpg
└── logo-marca.png
```

> **Regras:** nomes sem espaços, use hífens. Formatos recomendados: WebP, JPG, PNG.  
> Proporção ideal para cards do portfólio: **2:3** (ex: 400×600px).

---

## Prioridade de dados

```
1. Supabase (tabela zainerama_config)  ← prioridade total
2. Supabase Storage (pastas do bucket) ← fallback para portfólio se grupos estiverem vazios
```

Não há localStorage. Todos os dados vivem na nuvem.

---

## Painel Admin

**Acesso:** clique no ícone ⚙ no canto inferior direito do site.



> Recomenda-se alterar a senha imediatamente após o primeiro acesso, pela aba **Senha** no painel.

### O que pode ser editado pelo painel

- **Links** — URL dos botões de contato
- **Portfólios** — criar/renomear/excluir grupos, adicionar/remover/reordenar imagens por URL
- **Supabase** — atualizar credenciais e testar conexão
- **Senha** — alterar a senha do painel admin

### Edição inline (modo admin ativo)

Com o admin logado, clique diretamente nos elementos visuais para editá-los:

- **Logo** — clique no logo no topo
- **Imagem hero** — clique na foto principal
- **Avatares** — clique nos círculos dos depoimentos
- **Fotos do portfólio** — clique em qualquer card

Em todos os casos, cole a URL pública da imagem (Supabase Storage, Cloudinary, etc.).

---

## Deploy

O site é um único arquivo `index.html`. Pode ser hospedado em:

- [Vercel](https://vercel.com) — arraste o arquivo ou conecte o repositório
- [Netlify](https://netlify.com) — drop do arquivo no painel
- [GitHub Pages](https://pages.github.com) — repositório público com o arquivo na raiz
- Qualquer hospedagem de arquivos estáticos

---

## Credenciais Supabase
 
## Licença

Uso privado — Zainerama. Todos os direitos reservados.