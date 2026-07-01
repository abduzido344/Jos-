# Pesquisa de Mercado — Framework de Avatar de IA com Voz Clonada (PT-BR)

## ⚠️ Aviso de execução (leia antes da tabela)

- **Apify indisponível neste ambiente:** o proxy de rede desta sessão bloqueou (403/CONNECT rejeitado) qualquer conexão com `api.apify.com`. É uma política de rede do ambiente, não um problema de token — portanto os Actors `apify/website-content-crawler` e `clockworks/tiktok-scraper` **não puderam ser executados**, mesmo com um `APIFY_API_TOKEN` válido em mãos. Não tentei contornar o bloqueio, conforme instruído.
- **Segurança:** um token da Apify foi colado em texto puro no chat durante esta sessão. Ele **não foi reimpresso** em nenhum momento, mas já ficou registrado no histórico da conversa — recomendo **revogar/rotacionar esse token na sua conta Apify agora**.
- **Dados de pricing (tarefa 1):** como alternativa, coletei os dados via busca web (WebSearch), com fontes citadas. São confiáveis, mas não é scraping estruturado das páginas oficiais via Apify — trate como pesquisa de mercado, não como extração garantida em tempo real.
- **Dados de TikTok (tarefa 2):** **não foram coletados**. Métricas de vídeos individuais (views, duração, formato de narração, hashtags #booktok/#narração/#curiosidades/#historia filtradas por BR) exigem um scraper de verdade — não é algo que dá para obter de forma confiável via busca web genérica, e não tentei simular números. Se quiser esses dados, a Apify precisa estar acessível (ou você roda localmente com o token, fora deste ambiente restrito).

---

## 1. Comparativo de ferramentas (voz + avatar)

| Ferramenta | Preço/unidade | Free tier | PT-BR | API | Self-host |
|---|---|---|---|---|---|
| **Fish Audio (S2 / S2.1 Pro)** | ~$15/milhão de bytes UTF-8 (s2-pro); Flash/turbo mais barato. ~12h de fala por 1M bytes em inglês | 7 min + 8K créditos/mês (uso não-comercial); `s2.1-pro-free` sem hard cap, sujeito a fair use | Sim (pt, tier 2 no S1.5; S2/S2.1-Pro cobre 80-83 idiomas) | Sim (REST API) | **Sim** — fish-speech é open-source (GitHub), rodável localmente com WebUI Gradio |
| **ElevenLabs** | $0,10/1.000 caracteres (Multilingual v2/v3); $0,05/1.000 (Flash/Turbo). Custo real por minuto: ~$0,10–$0,50 | 10.000 créditos/mês (~10 min), sem licença comercial, exige atribuição | Sim (32+ idiomas, inclui PT) | Sim (planos de API próprios, separados do UI) | Não (SaaS fechado) |
| **HeyGen** | Pay-as-you-go desde $5; ~$1/min vídeo padrão 720p/1080p; Avatar IV ~6 créditos/min (~$4/min em 1080p) | **Removido em fev/2026** — não há mais créditos de API grátis | Sim (175+ idiomas com voice cloning, PT-BR e PT-PT nativos) | Sim | Não (SaaS fechado) |
| **Hedra (Character-3)** | Créditos por segundo: ~6 créditos/seg a 720p (≈360 créditos/min); planos de $15 a $75/mês | Sim — 100 créditos grátis, com marca d'água | Sim (140+ idiomas, lip-sync adaptado a fonemas) | Sim (Platform API lançada fev/2026, api.hedra.com) | Não (SaaS fechado) |

### Custo estimado por vídeo de 60s (narração + avatar, PT-BR)

| Ferramenta | Papel no pipeline | Custo estimado / vídeo 60s |
|---|---|---|
| Fish Audio S2/S2.1 Pro | Voz (TTS + emoção) | ~$0,15–$0,30 (pago) ou **$0 self-host / free API** |
| ElevenLabs | Voz (voice cloning) | ~$0,10–$0,50 (dependendo do plano/modelo) |
| HeyGen | Avatar + lip sync | ~$1,00–$4,00 (padrão vs. Avatar IV 1080p) |
| Hedra Character-3 | Avatar (imagem única) | ~360 créditos ≈ **$5–$6** no plano Basic, caindo para ~$4/min em planos maiores |

| Ferramenta | Custo est. / vídeo 60s | Emoção controlável | Português nativo | API disponível | Self-host possível |
|---|---|---|---|---|---|
| Fish Audio S2 Pro | $0–$0,30 | **Sim** (tags livres tipo `[whisper]`, `[laughing]`, 15.000+ tags) | Sim | Sim | **Sim** |
| ElevenLabs | $0,10–$0,50 | Parcial (estilo/estabilidade, sem tags emocionais livres) | Sim | Sim | Não |
| HeyGen | $1–$4 | Parcial (expressões do avatar via presets, não granular) | Sim | Sim | Não |
| Hedra Character-3 | $4–$6 | **Sim** (micro-expressões geradas por análise de áudio: piscar, olhar, cabeça) | Sim | Sim | Não |

---

## 2. Recomendação de stack

- **Voz:** priorize **Fish Audio S2/S2.1 Pro** — é a única opção com self-host real (fish-speech open source), controle emocional granular via tags, cobertura de PT-BR e um tier gratuito generoso (inclusive um modelo "free" via API). Isso resolve custo marginal ~$0 se você auto-hospedar.
- **Avatar:** **Hedra Character-3** parece o melhor equilíbrio custo/expressividade para avatar de imagem única — as micro-expressões (piscar, olhar, inclinação de cabeça) derivadas do áudio combinam bem com uma voz emocionalmente expressiva vinda do Fish Audio, criando avatar+voz coerentes.
- **Alternativa mais barata de avatar:** se o custo por segundo do Hedra/HeyGen pesar no orçamento (ambos ficam na faixa de $1–$6 por vídeo de 60s, ordens de magnitude acima da voz), avalie manter avatar "estático com pequenas animações" via Hedra no plano free/Basic para os primeiros testes, migrando para HeyGen apenas se precisar de lip-sync mais realista em vídeos de maior orçamento.
- **Evite ElevenLabs como peça central:** custo comparável ao Fish Audio, mas sem self-host e sem controle emocional por tags — só faz sentido se a qualidade de clonagem de voz específica for comprovadamente superior no seu teste A/B.
- **Pipeline sugerido:** n8n orquestrando (1) geração de imagem já resolvida → (2) Fish Audio self-hosted (Docker) para roteiro com emoção → (3) Hedra API para lip-sync/avatar → (4) Supabase para armazenar assets/roteiros → Notion para board editorial. Isso mantém a parte mais cara (avatar) como único custo variável por vídeo, com voz praticamente gratuita.
- **Dado pendente:** a validação de formato viral (TikTok, #booktok etc.) fica em aberto — sem esse dado, a recomendação acima é baseada em custo/controle técnico, não em benchmarking de o que já viraliza no nicho BR. Vale rodar o `tiktok-scraper` fora deste ambiente restrito antes de fechar o formato final (voz só vs. avatar falando).
