# Tekoha — Assets

Repositório público que hospeda os **áudios** e **imagens** usados pelo aplicativo Tekoha.

> Este repositório é **somente leitura para o app**. O aplicativo consome os arquivos diretamente pelas URLs públicas do GitHub (`raw.githubusercontent.com`).

---

## Estrutura de pastas

audios/
└── nheengatu/
├── cumprimentos/
├── natureza/
└── familia/images/
└── culture/
└── nheengatu/

- `audios/nheengatu/<modulo>/` — áudios dos exercícios de cada módulo.
- `images/culture/nheengatu/` — imagens da aba Cultura do app.

---

## Convenção de nomes dos arquivos de áudio

**Formato obrigatório:**

<modulo><ordem><palavra>.mp3

**Regras:**
- Tudo em **minúsculas**.
- **Sem acentos, sem cedilhas, sem espaços** (use `_` no lugar de espaço).
- A `<ordem>` sempre com **2 dígitos**: `01`, `02`, ..., `10`.
- `<palavra>` é a palavra/frase em Nheengatu daquele exercício (simplificada, sem acentos).

**Exemplos válidos:**
- `cumprimentos_01_selamai.mp3`
- `cumprimentos_02_maitei.mp3`
- `natureza_01_igarape.mp3`
- `familia_01_xeiru.mp3`

**Exemplos inválidos:**
- ❌ `Cumprimentos_1_Selamaí.mp3` (maiúsculas, acento, sem zero à esquerda)
- ❌ `cumprimentos-01-selamai.mp3` (traço em vez de underline)
- ❌ `cumprimentos 01 selamai.mp3` (espaços)

---

## Especificações técnicas dos áudios

| Item | Valor |
|---|---|
| Formato | MP3 |
| Bitrate | 192 kbps |
| Canais | Mono (preferencial) ou estéreo |
| Duração | Entre 1 e 5 segundos |

---

## Como subir um áudio novo

1. Acesse a pasta correta do módulo (ex: `audios/nheengatu/cumprimentos/`).
2. Clique em **Add file** → **Upload files**.
3. Arraste o arquivo `.mp3` (já com o nome no padrão da convenção acima).
4. Em **Commit changes**, escreva uma mensagem clara, ex:

feat: adiciona audio cumprimentos_01_selamai

5. Clique em **Commit changes**.

---

## Como pegar a URL pública para colar no Airtable

Depois de subir o arquivo, você precisa da URL **canônica** (formato `raw.githubusercontent.com`). Há duas formas:

### Forma 1 — Botão "Raw" (rápida)

1. Clique no nome do arquivo já subido.
2. Clique com o **botão direito** no botão **Raw** (canto superior direito).
3. Escolha **Copiar endereço do link**.
4. Se o link copiado começar com `https://github.com/...`, **converta para o formato canônico** (ver Forma 2).

### Forma 2 — Montar a URL manualmente (recomendado, sempre funciona)

A URL final segue **exatamente** este modelo:
https://raw.githubusercontent.com/Marcos-Codfy/tekoha-assets/main/<caminho-do-arquivo>

**Exemplo prático:**

Arquivo: `audios/nheengatu/cumprimentos/cumprimentos_01_selamai.mp3`

URL final:https://raw.githubusercontent.com/Marcos-Codfy/tekoha-assets/main/audios/nheengatu/cumprimentos/cumprimentos_01_selamai.mp3

Essa URL vai no campo `audio_url` da tabela `Exercises` do Airtable.

---

## Validação rápida

Para confirmar que um áudio está acessível publicamente:

1. Copie a URL canônica.
2. Cole numa aba **anônima** do navegador.
3. Se o navegador iniciar o download do arquivo automaticamente, **está correto** — o app Flutter consegue tocar normalmente.

---

## Imagens da Cultura

Mesma lógica dos áudios, dentro de `images/culture/nheengatu/`. Nomes esperados:

- `card_nheengatu.jpg` — imagem principal do card da Cultura
- `history.jpg`
- `cosmology.jpg`
- `habits.jpg`
- `curiosities.jpg`

Formato recomendado: **JPG** ou **WEBP**, máximo **500 KB** por arquivo.

---

## Importante

- **Nunca** apague arquivos sem avisar o time — URLs em uso no Airtable irão quebrar.
- **Nunca** renomeie um arquivo já em uso — URLs em uso no Airtable irão quebrar.
- Se precisar substituir um áudio, suba o novo com o **mesmo nome** do antigo (o Git versiona, mas a URL pública continua a mesma).
