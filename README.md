# Folder informativo sobre Hipertensão Arterial Sistêmica (HAS)

Folder educativo em **A4 paisagem, dobra em sanfona (Z)**, com 6 painéis de 99 mm, feito em HTML + CSS puro e exportado para PDF.

> **Aviso:** material informativo e educativo. Não substitui consulta, diagnóstico ou orientação de médico ou enfermeiro. Veja a seção [Conteúdo e validação](#conteúdo-e-validação) antes de distribuir.

---

## Sumário

1. [Objetivo](#objetivo)
2. [Estrutura do repositório](#estrutura-do-repositório)
3. [Estrutura do folder, painel a painel](#estrutura-do-folder-painel-a-painel)
4. [Por que foi produzido assim](#por-que-foi-produzido-assim)
5. [Como gerar o PDF](#como-gerar-o-pdf)
6. [Como imprimir e dobrar](#como-imprimir-e-dobrar)
7. [Conteúdo e validação](#conteúdo-e-validação)
8. [Limitações conhecidas](#limitações-conhecidas)
9. [Publicação na web (opcional)](#publicação-na-web-opcional)
10. [Licença](#licença)

---

## Objetivo

Informar o público leigo sobre a HAS de forma **objetiva e visual**: o que é, por que é perigosa, quem corre risco, como prevenir, como medir a pressão corretamente e quando procurar atendimento de urgência.

Critérios que guiaram o trabalho:

- Uma ideia principal por painel.
- Texto curto, em linguagem simples.
- Cores de alto impacto, porque a HAS é uma doença silenciosa e o material precisa chamar atenção.
- Pronto para imprimir em casa ou em gráfica, em uma única folha A4.

## Estrutura do repositório

```
.
├── README.md          Este documento
├── folder-has.html    Fonte do folder (HTML + CSS, sem dependências)
└── folder-has.pdf     Arquivo final, 2 páginas A4 paisagem (frente e verso)
```

| Arquivo | Função |
|---|---|
| `folder-has.html` | **Fonte única.** Todo o conteúdo, o layout e o estilo estão neste arquivo. Edite aqui e gere o PDF de novo. |
| `folder-has.pdf` | **Entregável.** É o arquivo que se imprime ou compartilha. É gerado a partir do HTML, nunca editado à mão. |

Não há `package.json`, bibliotecas nem fontes externas. O arquivo abre em qualquer navegador moderno.

### Estrutura interna do `folder-has.html`

1. `<style>`: variáveis de cor em `:root`, regras de página (`@page`), classes por tipo de componente (capa, cartão de estatística, tabela, chips, lista com ícone, caixa de emergência).
2. `<section class="page">` da **frente**, com 3 `div.panel`.
3. `<section class="page">` do **verso**, com 3 `div.panel`.

## Estrutura do folder, painel a painel

O folder tem duas páginas A4 paisagem, cada uma dividida em três colunas de 99 mm (297 mm ÷ 3). As dobras ficam em 99 mm e 198 mm.

### Frente

| Painel | Título | Conteúdo | Por que está aqui |
|---|---|---|---|
| 1 | **Capa** | Título, mostrador com "<120/80", linha de batimento cardíaco, chamada "Silenciosa, mas perigosa" | É o que a pessoa vê primeiro. Precisa dizer o assunto em segundos e criar urgência. |
| 2 | **O que é a HAS?** | Definição, limiar ≥140/90 mmHg, prevalência (1 em 3 adultos; mais de 60% entre idosos), tabela de classificação em cores | Dá a base do assunto e o parâmetro numérico que a pessoa pode comparar com a própria pressão. |
| 3 | **Perigo silencioso** | Aviso de que normalmente não há sintomas, sinais possíveis, 5 complicações (AVC, infarto e insuficiência cardíaca, rins, visão, artérias) | Responde ao "e daí?": mostra por que uma doença sem sintomas merece atenção. |

### Verso

| Painel | Título | Conteúdo | Por que está aqui |
|---|---|---|---|
| 4 | **Fatores de risco** | Fatores modificáveis e não modificáveis, mensagem sobre hereditariedade | Mostra o que a pessoa pode mudar e evita fatalismo em quem tem histórico familiar. |
| 5 | **7 atitudes que protegem** | Sal, alimentação, atividade física, peso, cigarro e álcool, sono e estresse, adesão ao remédio. Fundo escuro | É o painel de ação. O fundo escuro o destaca como o centro do folder. |
| 6 | **Como medir certo** | 4 passos de aferição, frequência de medida, caixa de emergência com **SAMU 192** | Termina com o que fazer na prática e o que fazer em uma emergência. |

A ordem segue uma narrativa: **o que é → por que importa → quem corre risco → como se proteger → como agir**.

## Por que foi produzido assim

### HTML + CSS em vez de Canva, Word ou editor gráfico

- **Medidas exatas.** Com `@page { size: 297mm 210mm; margin: 0 }` e painéis de `99mm`, as dobras caem no lugar certo. Em editores de texto a margem e a quebra de página variam com a impressora.
- **Versionável.** Um arquivo de texto funciona bem no Git: dá para ver o que mudou em cada revisão do conteúdo.
- **Reprodutível e gratuito.** Qualquer pessoa com um navegador gera o mesmo PDF, sem licença de software.
- **Fácil de adaptar.** Trocar uma cor é mudar uma variável. Trocar um dado é editar uma linha.
- **Sem dependências.** Nenhuma biblioteca nem CDN: o arquivo continua funcionando daqui a anos e imprime offline.

### Dobra em sanfona (Z)

Cada painel fica em uma face diferente quando dobrado, e o folder se lê em sequência ao abrir, sem precisar virar em duas direções. Também mantém o desenho em 3 colunas simples, que cabe em A4 sem desperdício.

### Paleta de cores

| Cor | Hex | Uso | Motivo |
|---|---|---|---|
| Vermelho | `#E11D48` | Destaques, títulos de seção, alertas | Associa-se a sangue, coração e urgência. Chama atenção para o risco. |
| Azul-marinho | `#0B1F3A` | Capa, painel de ação, cartões escuros | Transmite seriedade e dá contraste forte com o vermelho e o amarelo. |
| Amarelo | `#FFC83D` | Etiquetas, números grandes, caixas de aviso | Cor clássica de atenção, usada para guiar o olhar. |
| Branco | `#FFFFFF` | Fundo dos painéis de leitura | Descansa o olhar e economiza tinta. |

A **tabela de classificação** usa uma escala do verde (normal) ao vinho (estágio 3), para que o nível de gravidade seja entendido pela cor mesmo sem ler os números.

O contraste entre texto e fundo foi pensado visualmente, **mas a razão de contraste WCAG não foi medida**.

### Tipografia

Foi usada a pilha de fontes do sistema (`Segoe UI`, `Arial`, `Helvetica`). Não depende de internet nem de arquivos de fonte, e imprime igual em qualquer computador. Títulos em caixa alta e peso 900 para leitura a distância. O corpo do texto fica em torno de 10 a 10,5 pt, que é legível em papel para a maioria dos leitores, incluindo idosos, que são o público de maior risco.

### Escolhas de conteúdo

- **Poucas palavras por painel.** O folder é para despertar atenção e orientar a ação, não para ensinar fisiologia.
- **Números concretos** (5 g de sal, 150 min de atividade, 5 min de repouso) em vez de conselhos vagos.
- **Emergência com destaque visual** e telefone grande, porque é a informação que mais precisa ser achada rápido.
- **Aviso de que o diagnóstico é do profissional de saúde**, para não incentivar autodiagnóstico.

## Como gerar o PDF

Com o Microsoft Edge (Windows), sem instalar nada:

```powershell
& "C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" `
  --headless --disable-gpu --no-pdf-header-footer `
  --print-to-pdf="folder-has.pdf" "file:///CAMINHO/COMPLETO/folder-has.html"
```

Também funciona manualmente: abra o `.html` no Chrome ou no Edge, pressione `Ctrl+P`, escolha **Salvar como PDF**, papel **A4**, orientação **paisagem**, margens **Nenhuma**, e marque **Gráficos de segundo plano**.

Confira que o PDF tem **2 páginas**.

## Como imprimir e dobrar

1. Imprima em A4, **escala 100%** (não use "ajustar à página").
2. Impressão frente e verso, virando pela **borda curta**.
3. Dobre em Z nas linhas de 99 mm e 198 mm, com a capa voltada para fora.

## Conteúdo e validação

Os dados clínicos se baseiam na **Diretriz Brasileira de Hipertensão Arterial 2020** (SBC/SBH/SBN) e em recomendações da OMS (sal abaixo de 5 g por dia, 150 minutos semanais de atividade moderada).

**O texto foi redigido com auxílio de IA a partir de conhecimento prévio, sem consulta online à fonte durante a produção.** Por isso:

- Confira cada número e afirmação na diretriz antes de distribuir.
- Se o material for usado publicamente, tenha a revisão de um profissional de saúde.
- Diretrizes são atualizadas. Verifique se há versão mais recente.

## Limitações conhecidas

- **PDF em RGB, sem sangria nem marcas de corte.** Gráficas profissionais costumam exigir CMYK com sangria de 3 mm. Para esse caso, ajuste o arquivo em um editor gráfico antes de enviar.
- **Não é responsivo.** As páginas têm largura fixa (297 mm). No celular, prefira abrir o PDF em vez do HTML.
- **Ícones em emoji.** Dependem da fonte de emoji do sistema, que muda de aparência entre Windows, macOS e Android. No PDF, ficam fixos.
- **Testado apenas em visualização na tela e exportação para PDF.** Não houve teste de impressão em papel.
- Contraste de cores não medido (ver acima).

## Publicação na web (opcional)

É um site estático: basta publicar os arquivos em qualquer hospedagem estática (Vercel, GitHub Pages, Netlify). Como o HTML não é responsivo, o ideal é publicar uma página de abertura simples que aponte para o `folder-has.pdf`.

## Licença

Nenhuma licença foi definida ainda. Sem licença, o padrão legal é "todos os direitos reservados". Escolha uma antes de abrir o uso a terceiros (por exemplo, **CC BY 4.0** para o conteúdo, que exige apenas atribuição).
