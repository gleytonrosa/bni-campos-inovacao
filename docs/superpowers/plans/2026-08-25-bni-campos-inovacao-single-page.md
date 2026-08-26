# BNI Campos Inovação Single Page Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Construir e publicar uma Single Page responsiva da BNI Campos Inovação, fiel à identidade visual oficial BNI e orientada à conversão de visitantes para o WhatsApp.

**Architecture:** Site estático sem framework e sem etapa de build, composto por `index.html`, `assets/css/styles.css`, `assets/js/main.js` e assets locais. O projeto será compatível com GitHub Pages, mobile-first, acessível e sem dependências externas obrigatórias.

**Tech Stack:** HTML5 semântico, CSS3, JavaScript vanilla, GitHub Pages.

**Spec:** `docs/superpowers/specs/2026-08-25-bni-campos-inovacao-single-page-design.md`

## Global Constraints

- Cor primária BNI Red: `#CF2030`.
- True White: `#FFFFFF`.
- Power Black: `#000000`.
- Sterling Grey: `#C8C8C8`.
- Granite Grey: `#64666A`.
- Sterling Light Grey: `#F2F2F2`.
- Não usar dourado, azul, verde ou qualquer paleta paralela como elemento estrutural.
- Logo BNI sem distorção, recoloração, sombra, contorno ou alteração de proporção.
- Tipografia: Helvetica Neue com fallback Arial, sans-serif.
- CTA principal: `QUERO VISITAR UMA REUNIÃO`.
- WhatsApp: `https://wa.me/5522925500775`.
- Mensagem pré-preenchida: `Olá! Conheci a BNI Campos Inovação pelo site e gostaria de saber como participar de uma reunião como visitante.`
- Não exibir membros individualmente.
- Não exibir números ou métricas da equipe.
- Não prometer resultados financeiros garantidos.
- Não usar imagens genéricas que representem incorretamente Campos dos Goytacazes.
- Responsividade obrigatória em 360, 390, 768, 1024 e 1440 px.

---

### Task 1: Base estrutural e metadados

**Files:**
- Create: `index.html`
- Create: `assets/css/styles.css`
- Create: `assets/js/main.js`

**Interfaces:**
- Consumes: requisitos do design aprovado.
- Produces: estrutura semântica completa da página, IDs de navegação e ponto de entrada para estilos e comportamento.

- [ ] **Step 1: Criar teste estrutural manual de aceitação**

Critérios: `index.html` deve conter `header`, `main`, `footer`, as seções `quem-somos`, `como-funciona`, `beneficios`, `conexoes`, `regiao`, `faq`, e ao menos três links com destino para o WhatsApp oficial.

- [ ] **Step 2: Criar HTML semântico mínimo**

Incluir `lang="pt-BR"`, `viewport`, title `BNI Campos Inovação | Networking Empresarial em Campos dos Goytacazes`, meta description aprovada, navegação por âncoras e estrutura completa das seções.

- [ ] **Step 3: Conectar CSS e JavaScript**

Usar caminhos relativos `assets/css/styles.css` e `assets/js/main.js`, compatíveis com GitHub Pages em subdiretório.

- [ ] **Step 4: Validar estrutura**

Verificar ausência de links quebrados internos e ausência de conteúdo proibido pela especificação.

- [ ] **Step 5: Commit**

```bash
git add index.html assets/css/styles.css assets/js/main.js
git commit -m "feat: scaffold BNI Campos Inovação single page"
```

### Task 2: Sistema visual BNI e responsividade

**Files:**
- Modify: `assets/css/styles.css`

**Interfaces:**
- Consumes: classes e IDs definidos em `index.html`.
- Produces: tokens visuais, grid, tipografia, header, hero, cards, FAQ, CTAs e comportamento responsivo.

- [ ] **Step 1: Definir tokens de design**

Criar `:root` com `--bni-red:#CF2030`, `--white:#FFFFFF`, `--black:#000000`, `--sterling:#C8C8C8`, `--granite:#64666A`, `--light-grey:#F2F2F2`, além de escalas de espaçamento, radius e largura máxima sem introduzir novas cores estruturais.

- [ ] **Step 2: Implementar layout mobile-first**

Base para 360–390 px com navegação compacta, botões sem overflow e seções com espaçamento consistente.

- [ ] **Step 3: Implementar breakpoints**

Adicionar ajustes em 768 px, 1024 px e 1440 px para grids, hero, tipografia e navegação horizontal.

- [ ] **Step 4: Implementar acessibilidade visual**

Adicionar foco visível, contraste adequado, `:focus-visible`, áreas de toque confortáveis e `@media (prefers-reduced-motion: reduce)`.

- [ ] **Step 5: Commit**

```bash
git add assets/css/styles.css
git commit -m "feat: implement official BNI visual system"
```

### Task 3: Conteúdo institucional e fluxo de conversão

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: estrutura visual de Task 2.
- Produces: copy final das seções e CTAs orientados à visita.

- [ ] **Step 1: Implementar Hero**

Headline `BNI CAMPOS INOVAÇÃO`, mensagem `Conexões que geram negócios. Relacionamentos que constroem resultados.` e CTA primário para WhatsApp.

- [ ] **Step 2: Implementar Quem Somos e Por que Campos Inovação**

Texto institucional focado em relacionamento, confiança, networking recorrente, oportunidades e desenvolvimento profissional, sem métricas ou promessas financeiras.

- [ ] **Step 3: Implementar Como Funciona e Benefícios**

Fluxo em quatro passos e seis benefícios: Relacionamentos, Indicações qualificadas, Desenvolvimento, Visibilidade empresarial, Comunidade e Oportunidades.

- [ ] **Step 4: Implementar Conexões e Região**

Seção `Negócios que se conectam. Oportunidades que circulam.` e narrativa regional sem estatísticas inventadas.

- [ ] **Step 5: Implementar FAQ, CTA final e footer**

Incluir cinco perguntas aprovadas, CTA `QUERO CONHECER A BNI CAMPOS INOVAÇÃO`, localização `Campos dos Goytacazes — RJ` e WhatsApp `(22) 92550-0775`.

- [ ] **Step 6: Commit**

```bash
git add index.html
git commit -m "feat: add institutional content and conversion flow"
```

### Task 4: Interações leves e WhatsApp

**Files:**
- Modify: `assets/js/main.js`
- Modify: `index.html`

**Interfaces:**
- Consumes: IDs do menu e links CTA.
- Produces: menu mobile, FAQ acessível e links de WhatsApp consistentes.

- [ ] **Step 1: Centralizar URL do WhatsApp**

Definir em JavaScript a constante `WHATSAPP_URL` com número `5522925500775` e a mensagem aprovada usando `encodeURIComponent`.

- [ ] **Step 2: Aplicar URL a todos os CTAs**

Selecionar elementos `[data-whatsapp]` e atribuir o mesmo destino, evitando divergência entre botões.

- [ ] **Step 3: Implementar menu mobile**

Alternar `aria-expanded`, abrir/fechar navegação e fechar após clique em âncora.

- [ ] **Step 4: Implementar FAQ acessível**

Usar `details/summary` preferencialmente, evitando JavaScript desnecessário; se houver JS, preservar teclado e ARIA.

- [ ] **Step 5: Commit**

```bash
git add index.html assets/js/main.js
git commit -m "feat: add WhatsApp and mobile interactions"
```

### Task 5: Assets e tratamento de marca

**Files:**
- Create: `assets/img/README.md`
- Modify: `index.html`
- Modify: `assets/css/styles.css`

**Interfaces:**
- Consumes: arquivos oficiais de logo/fotografia quando fornecidos ou adicionados ao repositório.
- Produces: slots de imagem com proporção, alt text e fallback visual consistente com a paleta BNI.

- [ ] **Step 1: Documentar regras de assets**

Registrar nomes esperados para `bni-logo-red.*`, `bni-logo-white.*` e imagem regional, deixando explícito que apenas arquivos oficiais/aprovados devem ser usados.

- [ ] **Step 2: Preparar placeholders neutros sem falsificar Campos**

Enquanto não houver fotografia regional aprovada, usar composição gráfica abstrata apenas com cores BNI; não usar skyline genérico.

- [ ] **Step 3: Preparar logo por contexto**

Estrutura para logo vermelho sobre fundo claro e branco reverso sobre fundo vermelho/escuro, sem filtros CSS que alterem a marca.

- [ ] **Step 4: Commit**

```bash
git add assets/img/README.md index.html assets/css/styles.css
git commit -m "feat: prepare compliant BNI brand assets"
```

### Task 6: SEO, QA e publicação no GitHub Pages

**Files:**
- Modify: `index.html`
- Create: `.nojekyll`
- Modify: `README.md`

**Interfaces:**
- Consumes: site final de Tasks 1–5.
- Produces: versão pronta para publicação estática.

- [ ] **Step 1: Revisar SEO on-page**

Validar title, meta description, hierarquia única de `h1`, headings sequenciais, textos de link claros e `alt` descritivo.

- [ ] **Step 2: Revisar responsividade**

Testar visualmente em larguras 360, 390, 768, 1024 e 1440 px; nenhum CTA pode ter overflow horizontal ou ficar inacessível.

- [ ] **Step 3: Revisar acessibilidade**

Validar navegação por teclado, foco, contraste, `aria-label` do menu, `details/summary` do FAQ e preferência de movimento reduzido.

- [ ] **Step 4: Revisar todos os CTAs**

Confirmar que todos apontam para `5522925500775` com a mesma mensagem pré-preenchida.

- [ ] **Step 5: Criar `.nojekyll` e atualizar README**

Documentar estrutura, URL de publicação e regras de atualização sem incluir credenciais.

- [ ] **Step 6: Commit**

```bash
git add index.html .nojekyll README.md
git commit -m "chore: prepare BNI site for GitHub Pages"
```

- [ ] **Step 7: Publicar**

Configurar GitHub Pages para servir a branch `main` a partir da raiz e validar a URL pública resultante.
