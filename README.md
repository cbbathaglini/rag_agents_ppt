# Do dado à decisão — RAG, Agentes e Multi-Agente

Apresentação web imersiva e didática, em **português do Brasil**, para explicar
de forma simples, visual e tecnicamente correta **RAG, Agentes de IA e Sistemas
Multiagentes**.

Construída com React + TypeScript + Vite, com cenas dirigidas por passos,
animações em GSAP e laboratórios interativos (chunking, embeddings, trace) —
sem nenhuma chamada a LLM real. Tudo é determinístico e roda 100% no navegador.

## Descrição

A experiência começa sem IA nenhuma: três microsserviços simples executam um
workflow. A partir daí, cada conceito nasce de uma **necessidade real**:

- **RAG** — como a IA acessa conhecimento sem ler 50 mil documentos toda vez
  (docs → chunk → embedding → Vector DB → busca).
- **Agentes de IA** — "saber não é fazer": entender ≠ executar ≠ coordenar,
  ferramentas (tools) como ponte entre decisão e ação.
- **Sistemas multiagentes** — de um agente monolítico a especialistas que
  conversam, coordenam e delegam, com eventos (Kafka) transportando mensagens.

Metáfora central: **CONHECER · DECIDIR · AGIR · COORDENAR · EVENTOS**.

### Mecânica

- Cada cena avança por **passos** (tecla espaço/seta → nova revelação).
- Diagramas ocupam o palco inteiro em vez de empilhar informação.
- Labs interativos e determinísticos — sem API externa.

## Requisitos

- [Node.js](https://nodejs.org) 18+ (recomendado 20+)
- npm (incluso com o Node.js)

## Passo a passo para rodar

```bash
# 1. Clonar o repositório
git clone git@github.com:cbbathaglini/rag_agents_ppt.git
cd rag_agents_ppt

# 2. Instalar as dependências
npm install

# 3. Rodar em desenvolvimento (http://localhost:5173)
npm run dev
```

### Build e preview de produção

```bash
npm run build     # gera a pasta dist/ (typecheck + vite build)
npm run preview   # serve o build localmente para validar
```

### Verificações

```bash
npm run lint        # eslint (ts, tsx)
npm run typecheck   # typescript --noEmit
npm run check       # valida estrutura das cenas/dados
```

## Navegação e controles

| Tecla | Ação |
| --- | --- |
| `→` / `Espaço` | avança passo/cena |
| `←` | volta |
| `Home` / `End` | início / fim |
| `F` | tela cheia |
| `N` | notas do apresentador |
| `R` | reinicia a cena |

## Estrutura

```
src/
├── data/          # conteúdo: serviços, agents, tools, cenários, glosário, quiz
├── scenes/        # atos e cenas (act1–act7, actfin, registry)
├── presentation/  # contexto e tipos do palco
├── components/    # UI reutilizável
├── styles/        # CSS global
└── theme.ts       # cores e tokens (LLM/RAG/Agent/Tools/Kafka…)
```

## Commit e push

```bash
# 1. Ver o que mudou
git status
git diff

# 2. Adicionar os arquivos desejados (ou "git add .")
git add README.md

# 3. Criar o commit
git commit -m "docs: adiciona README com instruções de uso"

# 4. Enviar para o repositório remoto
git push origin main
```

> O projeto já vem com `.gitignore` cobrindo `node_modules/`, `.env*`,
> `dist/`, logs e arquivos do sistema (`node_modules/` nunca deve ir para o repo).
