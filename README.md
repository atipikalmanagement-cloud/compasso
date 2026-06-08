# Localizador de Propostas — Mais Consultores Compasso

Ferramenta interna para a equipa de consultores. O consultor marca as características do proprietário que tem em mãos e a aplicação recomenda a proposta irresistível mais adequada, entregando a apresentação (para o cliente) e o brief de marketing (interno) em PDF. Inclui uma contagem da procura por tipo de proposta.

## O que faz

- **Formulário de perfil** com checkboxes agrupados (objetivo, urgência, contexto pessoal, receios).
- **Motor de recomendação** que pontua as 4 propostas e indica a de melhor encaixe, com explicação e alternativas.
- **Download em PDF** da proposta e do respetivo brief de marketing.
- **Estatísticas de procura** (percentagem e contagem por proposta), guardadas localmente no navegador.

As 4 propostas: Casa Vendida em 90, Sem Arrependimentos, Património a Render, Mudança Sincronizada.

## Estrutura

```
.
├── index.html                 # aplicação completa (HTML + CSS + JS, sem build)
├── vercel.json                # configuração de deploy
└── public/
    ├── logo.png               # logótipo Compasso
    └── propostas/             # os 8 PDFs (4 propostas + 4 briefs)
```

## Como alojar no GitHub e fazer deploy no Vercel

1. Cria um repositório novo no GitHub (ex.: `compasso-localizador-propostas`).
2. Coloca lá todo o conteúdo desta pasta (incluindo a pasta `public/`).
   ```bash
   git init
   git add .
   git commit -m "Localizador de propostas Compasso"
   git branch -M main
   git remote add origin https://github.com/<o-teu-utilizador>/compasso-localizador-propostas.git
   git push -u origin main
   ```
3. Em [vercel.com](https://vercel.com), faz **Add New → Project**, importa o repositório do GitHub.
4. Não é preciso configurar build: é um site estático. Faz **Deploy**.
5. Em segundos tens um URL público (ex.: `compasso-localizador-propostas.vercel.app`) para partilhar com a equipa.

## Notas

- A **contagem de downloads é local a cada navegador** (não é partilhada entre consultores nem entre dispositivos). Para um total partilhado por toda a equipa, seria necessário acrescentar um backend (ex.: Supabase) — pode ser um passo futuro.
- Os PDFs são servidos diretamente do repositório. Para atualizar uma proposta, substitui o ficheiro em `public/propostas/` e faz novo commit.
