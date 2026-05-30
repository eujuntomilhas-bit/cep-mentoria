# Fluxo de Publicação de Aulas — CEP Mentoria

## Visão Geral

Após cada aula, o objetivo é ter no dashboard:
- Gravação no YouTube (link ativo)
- Slides (já publicados antes da aula)
- Resumo da aula (gerado a partir da transcrição)

---

## Configuração Única (fazer uma vez só)

### Zoom — gravação local
1. Abrir o Zoom → **Configurações → Gravação**
2. Ativar **"Gravar no computador automaticamente"**
3. Ativar **"Transcrição de áudio"** (gera o arquivo `.vtt` junto com o vídeo)
4. Definir a pasta de destino das gravações

Após a aula, o Zoom salva automaticamente:
- `video.mp4` — o vídeo da aula
- `audio_transcript.vtt` — a transcrição completa

---

## Fluxo por Aula

### Passo 1 — Subir no YouTube
1. Abrir o YouTube Studio
2. Fazer upload do `video.mp4` gerado pelo Zoom
3. Título sugerido: `CEP Mentoria — Aula X — [Título da Aula]`
4. Visibilidade: **Não listado** (só quem tem o link acessa)
5. Copiar o link do vídeo publicado

### Passo 2 — Enviar para o Claude Code
Abrir o Claude Code e mandar:

```
Aula X — [Título]
YouTube: [colar o link]

[colar o conteúdo da transcrição do Zoom]
```

### Passo 3 — Claude faz o resto
A partir daí, automaticamente:
- Gera o resumo formatado a partir da transcrição
- Cria o `resumo-aula-X.html` no padrão do projeto
- Ativa o link da gravação no dashboard
- Ativa o link do resumo no dashboard
- Commita e sobe direto no `main`
- Deploy automático pelo GitHub Pages

### Passo 4 — Revisar
Acessar o dashboard e conferir se está tudo certo antes de avisar a aluna.

---

## Replicando para Novas Alunas

Cada aluna terá seu próprio repositório no GitHub com o mesmo template. O fluxo é idêntico — só muda o repositório de destino.

Ao iniciar uma nova mentoria:
1. Duplicar o repositório `cep-mentoria` como base
2. Atualizar o nome da aluna no `index.html`
3. Limpar os cards de aulas (deixar só Aula 1 ativa)
4. Ativar o GitHub Pages no novo repositório

---

## Estrutura de Arquivos

```
/
├── index.html                        # Dashboard principal
├── resumo-aula-1.html
├── resumo-aula-2.html
├── resumo-aula-3.html
├── checklist-briefing-viagem.html    # Material extra
├── guia-cadastro-programas-fidelidade.html
├── slides/
│   ├── aula-1-slides.html
│   ├── aula-2-slides.html
│   └── aula-3-slides.html
└── docs/
    └── fluxo-publicacao-aulas.md     # Este arquivo
```

---

## Checklist Rápido — Pós Aula

- [ ] Vídeo subido no YouTube (não listado)
- [ ] Link do YouTube copiado
- [ ] Transcrição do Zoom copiada
- [ ] Enviado para o Claude Code (link + transcrição)
- [ ] Resumo revisado no dashboard
- [ ] Aluna avisada que o material está disponível
