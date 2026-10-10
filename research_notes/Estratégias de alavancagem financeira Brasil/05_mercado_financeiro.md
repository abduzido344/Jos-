# Alavancagem e "dívida para investir" no mercado financeiro brasileiro (varejo) — Fase 1 (descoberta)

Data de referência: 10/out/2026. Dados oficiais do Banco Central (SGS, API api.bcb.gov.br) e do Tesouro Transparente foram consultados diretamente nesta data; as demais fontes são imprensa, reguladores e papers, com ressalvas indicadas.

Convenção de fontes: [BCB-SGS NNN] = série do Sistema Gerenciador de Séries Temporais do Banco Central, consultada via https://api.bcb.gov.br/dados/serie/bcdata.sgs.NNN/dados?formato=json (nome da série confirmado no catálogo https://dadosabertos.bcb.gov.br). Taxas ao ano convertidas por mim a partir de taxas ao mês estão marcadas como "(calc.)".

---

## 1. Cenário de juros hoje (Selic, CDI, inflação, Tesouro) e custo do crédito por modalidade

### Takeaway
Selic em 13,75% a.a. desde 17/09/2026 (CDI 13,65% em 08/10/2026), com juro real ex-post de ~8,7% a.a. O crédito de varejo custa de 24% a.a. (consignado INSS, o mais barato sem garantia de imóvel) a mais de 400% a.a. (rotativo). Quase nenhuma dívida de varejo custa menos do que a renda fixa líquida (~11,6% a 12,3% a.a.), então o "carry" simples não existe para o varejo.

### Cited Findings
**Selic / CDI / inflação**
- Selic meta: 15,00% no início de 2026; 14,75% (19/03), 14,50% (30/04), 14,25% (18/06), 14,00% (06/08) e 13,75% a partir de 17/09/2026 — [BCB-SGS 432](https://api.bcb.gov.br/dados/serie/bcdata.sgs.432/dados?formato=json&dataInicial=01/01/2026)
- Copom cortou 0,25 p.p. em 16/09/2026, decisão unânime, sem guidance explícito; Focus mediano via InfoMoney aponta Selic em 13,75% até o fim de 2026, com cortes só em 2027; XP projeta 13,25% e Oby Capital 13,50% no fim do ano — [InfoMoney](https://www.infomoney.com.br/economia/taxa-selic-copom-corta-juros-13-75-set-2026/)
- CDI anualizado: 13,65% a.a. em 07 e 08/10/2026 — [BCB-SGS 4389](https://api.bcb.gov.br/dados/serie/bcdata.sgs.4389/dados/ultimos/2?formato=json)
- IPCA: +0,82% em set/2026 (mensal) e 4,58% acumulado em 12 meses (ago: 4,22%; jul: 4,44%) — [BCB-SGS 433](https://api.bcb.gov.br/dados/serie/bcdata.sgs.433/dados/ultimos/14?formato=json), [BCB-SGS 13522](https://api.bcb.gov.br/dados/serie/bcdata.sgs.13522/dados/ultimos/3?formato=json)
- Há uma próxima reunião do Copom em novembro/2026 (não há reunião em outubro); a data exata (3-4/nov) vem de uma única fonte de blog — [Renova Invest](https://renovainvest.com.br/?p=106745); o InfoMoney confirma apenas "reunião de novembro, após a eleição presidencial".

**Rendimento de referência (o que a "dívida" precisa superar)**
- Tesouro Transparente, taxas indicativas de 09/10/2026 (manhã): Tesouro Selic com ágio/deságio ~0,05% a 0,10% sobre a Selic; Prefixado 2027 13,28%-13,40% a.a., Prefixado 2029 12,30%-12,42%, Prefixado 2031 12,45%-12,57%; IPCA+ 2029 ~6,62%-6,74%, IPCA+ 2032 ~6,65%-6,77%, IPCA+ 2035 ~6,66%-6,78%, IPCA+ 2045 ~6,49%-6,61% — [Tesouro Transparente, PrecoTaxaTesouroDireto.csv](https://www.tesourotransparente.gov.br/ckan/dataset/df56aa42-484a-4a59-8184-7676580c81e3/resource/796d2059-14e9-44e3-80c9-2d9e30b405c1/download/PrecoTaxaTesouroDireto.csv)
- Tabela regressiva do IR em renda fixa (CDB etc.): 22,5% até 180 dias, 20% de 181 a 360, 17,5% de 361 a 720 e 15% acima de 720 dias; LCI/LCA seguem isentas para pessoa física — [Blog Finanças (resumo de mercado, não a lei)](https://www.adrianofreire.com.br/blog/cdi-real-liquido-inflacao-ir-quanto-sobra-2026); a MP 1303/2025, que propunha tributar LCI/LCA/CRI/CRA, perdeu a validade em out/2025 — [Nord Investimentos](https://www.nordinvestimentos.com.br/blog/mp-1303-tributacao-lci-lca-cri-cra-fii-fiagro/) (a fonte fala em relator e proposta; a caducidade vem do resumo de busca, confirmar na Câmara/Planalto).

**Taxas médias de crédito PF (Banco Central, agosto/2026, recursos livres)**
- Total PF recursos livres: 61,74% a.a. (4,09% a.m.); a imprensa reporta 61,7% a.a. com +1,4 p.p. no mês — [BCB-SGS 20740](https://api.bcb.gov.br/dados/serie/bcdata.sgs.20740/dados/ultimos/1?formato=json), [BCB-SGS 25462](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25462/dados/ultimos/1?formato=json), [Agência Brasil](https://agenciabrasil.ebc.com.br/economia/noticia/2026-09/juros-para-familias-sobem-em-agosto-e-inadimplencia-chega-6)
- Cartão rotativo: 15,18% a.m. = ~445% a.a. (calc.); cartão parcelado 9,34% a.m. = ~192% a.a. (calc.) — [BCB-SGS 25477](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25477/dados/ultimos/2?formato=json), [BCB-SGS 25478](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25478/dados/ultimos/2?formato=json)
- Cheque especial: 7,43% a.m.; 136,41% a.a. — [BCB-SGS 25463](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25463/dados/ultimos/2?formato=json), [BCB-SGS 20741](https://api.bcb.gov.br/dados/serie/bcdata.sgs.20741/dados/ultimos/2?formato=json)
- Crédito pessoal não consignado: 6,39% a.m.; 110,22% a.a. — [BCB-SGS 25464](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25464/dados/ultimos/1?formato=json), [BCB-SGS 20742](https://api.bcb.gov.br/dados/serie/bcdata.sgs.20742/dados/ultimos/1?formato=json)
- Pessoal não consignado com garantias reais: 2,09% a.m. (=~28,2% a.a., calc.); sem garantias reais 7,13% a.m. — [BCB-SGS 29976](https://api.bcb.gov.br/dados/serie/bcdata.sgs.29976/dados/ultimos/2?formato=json), [BCB-SGS 29977](https://api.bcb.gov.br/dados/serie/bcdata.sgs.29977/dados/ultimos/2?formato=json)
- Consignado INSS: 1,82% a.m.; 24,12% a.a. — [BCB-SGS 25468](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25468/dados/ultimos/1?formato=json), [BCB-SGS 20746](https://api.bcb.gov.br/dados/serie/bcdata.sgs.20746/dados/ultimos/1?formato=json)
- Consignado setor público: 1,82% a.m.; 24,14% a.a. — [BCB-SGS 25467](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25467/dados/ultimos/1?formato=json), [BCB-SGS 20745](https://api.bcb.gov.br/dados/serie/bcdata.sgs.20745/dados/ultimos/1?formato=json)
- Consignado setor privado (CLT / Crédito do Trabalhador): 3,79% a.m.; 56,34% a.a. — [BCB-SGS 25466](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25466/dados/ultimos/1?formato=json), [BCB-SGS 20744](https://api.bcb.gov.br/dados/serie/bcdata.sgs.20744/dados/ultimos/1?formato=json)
- Consignado total: 2,14% a.m.; 29,00% a.a. — [BCB-SGS 25469](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25469/dados/ultimos/1?formato=json), [BCB-SGS 20747](https://api.bcb.gov.br/dados/serie/bcdata.sgs.20747/dados/ultimos/1?formato=json)
- Crédito pessoal vinculado a composição de dívidas: 2,89% a.m.; 40,69% a.a. — [BCB-SGS 25465](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25465/dados/ultimos/1?formato=json), [BCB-SGS 20743](https://api.bcb.gov.br/dados/serie/bcdata.sgs.20743/dados/ultimos/1?formato=json)
- Financiamento imobiliário (recursos direcionados, PF): taxa média total 11,28% a.a. (0,89% a.m.); "taxas de mercado" 14,24% a.a. — [BCB-SGS 20774](https://api.bcb.gov.br/dados/serie/bcdata.sgs.20774/dados/ultimos/2?formato=json), [BCB-SGS 25499](https://api.bcb.gov.br/dados/serie/bcdata.sgs.25499/dados/ultimos/2?formato=json), [BCB-SGS 20772](https://api.bcb.gov.br/dados/serie/bcdata.sgs.20772/dados/ultimos/2?formato=json)
- Home equity (crédito com garantia de imóvel): os cinco maiores bancos praticam 1,12% a 1,80% a.m. (=~14,3% a 23,9% a.a., calc.); prazo médio 159 meses em março e liberação de 32,2% do valor do imóvel (Abecip); R$ 3,166 bilhões no 1º tri/2026 (+25,83% a/a) — [Portas (resumo de pesquisa, não confirmado em fonte primária)](https://portas.com.br/mercado-imobiliario/home-equity-como-levantar-recursos-com-seu-imovel/), [busca consolidada](https://portas.com.br/noticias/home-equity-cresce-25-no-1-tri-e-bate-recorde/)
- Inadimplência PF: 6% em agosto/2026 (+1,1 p.p. em 12 meses); endividamento das famílias 49,9% da renda anual; comprometimento 28,7% da renda — [Agência Brasil](https://agenciabrasil.ebc.com.br/economia/noticia/2026-09/juros-para-familias-sobem-em-agosto-e-inadimplencia-chega-6)
- Tetos/médias do consignado: teto do INSS apontado em 1,85% a.m. e média de 1,79% a.m. na semana de 3-7/ago/2026; consignado privado 3,42% a.m. (Procon-MG, ago/2026) e série recorde de 59,4% a.a. em fev/2026; as fontes divergem sobre datas e sobre a existência de teto para o CLT — [Procon JF/MG monitoramento](https://www.pjf.mg.gov.br/administracao_indireta/procon/observatorio/arquivos/Monitoramento-Taxa-de-Juros-agosto-2026.pdf) (PDF não aberto diretamente; trechos via busca), [LetsMoney](https://www.letsmoney.com.br/noticias/consignado-privado-juros-recorde-59-por-cento/)
- IOF em crédito PF: alíquota adicional fixa de 0,38% mais 0,0082% ao dia (limitado a 365 dias), o que dá ~3,37% sobre o principal em 1 ano (calc.); a alta de 2025 foi derrubada pelo Congresso segundo fontes de mercado — [InvestNews](https://investnews.com.br/?p=526021), [Decreto 12.499/2025 (texto)](https://www.juruadocs.com/legislacao/art/dec_00124992025); a alíquota diária e o teto de 3% anuais não foram confirmados em fonte oficial.
- Saque-aniversário / antecipação do FGTS: regras do Conselho Curador aprovadas em 07/10/2025 com vigência 01/11/2025 — parcelas de R$ 100 a R$ 500, até 5 parcelas, uma operação por ano, carência de 90 dias; a partir de nov/2026 o limite cai para 3 parcelas; quem adere perde o saque do saldo na demissão sem justa causa (fica só a multa de 40%); nenhuma fonte trouxe o teto de juros — [Jornal Contábil](https://jornalcontabil.com.br/noticia/conselho-aprova-mudancas-no-saque-aniversario-o-que-muda-e-o-que-e-preciso-para-aderir/), [UAI](https://www.uai.com.br/noticias/2026/07/08/adeus-ao-saque-aniversario-mudanca-no-fgts-deve-afetar-milhoes-de-trabalhadores-em-2026/)
- Imposto sobre renda variável (inalterado em 2026 segundo fontes de mercado): 15% sobre swing trade, 20% sobre day trade, isenção de vendas de ações até R$ 20 mil/mês só para operações comuns; prejuízo de day trade só compensa com day trade — [Nord Investimentos](https://www.nordinvestimentos.com.br/blog/imposto-renda-venda-de-acoes/) (blog de corretora; conferir Lei 11.033/2004 e IN RFB 1.585/2015).

### Inferences
- (Cálculos meus) Retorno líquido de referência: CDB 100% CDI = 11,60% a.a. (acima de 720 dias; 10,6% a 11,3% em prazos menores); LCA a 90% do CDI = 12,29% isento; Selic líquida de 15% = ~11,7%; IPCA+ 6,77% com IPCA 4,58% = ~11,7% bruto e ~9,9% líquido.
- Spread (carry) contra o CDB líquido de 11,6%: consignado INSS -12,5 p.p./ano; consignado CLT ~-44 p.p.; pessoal não consignado ~-99 p.p.; home equity de 14,3% a.a. (melhor caso) -2,7 p.p.; home equity de 23,9% a.a. -12,3 p.p. Mesmo o melhor caso, antes de IOF (~3,4% no 1º ano) e custos de cartório/avaliação, é negativo.
- Única exceção aproximada: financiamento imobiliário médio de 11,28% a.a. contra LCA a 90% do CDI de 12,29% (+1,0 p.p.) e contra CDB líquido (+0,3 p.p.). É spread praticamente zero, não é "arbitragem": o crédito imobiliário é destinado à compra do imóvel, tem TR/indexação, garantia fiduciária e parte do spread some com risco de crédito/liquidez do emissor da aplicação (LCA tem FGC limitado, o que não foi pesquisado aqui).
- Em um ambiente de juro real ~8,7% a.a., o "hurdle" para qualquer ativo alavancado é muito alto; com dívida a 24% a.a. (INSS) o retorno do ativo precisaria superar 24% a.a. só para empatar.
- Fórmula do retorno alavancado (minha): ROE = r + L x (r - c), onde L = dívida/capital próprio. Com r = 11,6% e c = 24,1%, L = 1 dá -0,9% e L = 2 dá -13,4% ao ano. Com c = 14,3% (home equity barato), L = 1 dá 8,9% (pior do que sem dívida).
- Efeito de perda: com L = 1 (dívida igual ao capital), uma queda de 50% do ativo zera o capital; com L = 4, uma queda de 20%; com L = 9, queda de 10%.

### Gaps
- Não obtive a taxa média de home equity do BCB (série específica) nem spread sobre CDI; só a faixa dos bancos, vinda de resumo de pesquisa.
- Não confirmei a alíquota diária de IOF e o teto anual em fonte oficial (Receita/Decreto 6.306 consolidado).
- Não encontrei o teto de juros da antecipação do saque-aniversário nem a taxa média praticada em 2026.
- Taxas médias do BCB são médias de mercado; a taxa efetiva do usuário depende de perfil de risco; não coletei CET.
- A data exata do Copom de novembro/2026 precisa de checagem no calendário oficial do BC.

---

## 2. Evidência de resultados: day trade, mini-índice/mini-dólar, varejo em geral

### Takeaway
Os estudos de Chague, De-Losso e Giovannetti (FGV EESP, com dados da CVM) são a melhor evidência: entre day traders PF de mini-índice que persistem por mais de 300 pregões, 91% (versão 2019) a 97% (versão 2020) perderam dinheiro, e só 0,4% a 0,8% ganharam mais do que um salário de bancário ou R$ 300/dia. Um estudo de 2025 estima R$ 9,9 bilhões de perdas de ~968 mil PFs no day trade na pandemia. O número "97%" é real, mas vale para um recorte específico (sobreviventes de 300 dias em mini-índice).

### Cited Findings
- Working paper "Day Trading for a Living?" (Chague, De-Losso, Giovannetti), FGV EESP, Texto para Discussão 525, 2020: estudo de todos os indivíduos que começaram a fazer day trade em futuros de índice no Brasil entre 2013 e 2015 e persistiram ao menos 300 dias; cerca de 97% perderam dinheiro, só 0,4% ganhou mais do que um caixa de banco (~US$ 54/dia) e o melhor ganhou ~US$ 310/dia com muito risco; sem evidência de aprendizado — [IDEAS/RePEc](https://ideas.repec.org/p/fgv/eesptd/525.html); mesmo trabalho em [EconPapers](https://econpapers.repec.org/RePEc:fgv:eesptd:525)
- Versão de 2019 ("É possível viver de day trading?", estudo em convênio com a CVM, base completa de 2012-2017): 19.696 pessoas começaram a fazer day trade em mini-índice entre 2013 e 2015; 92,1% desistiram antes de 300 pregões; só 1.558 (7,9%) persistiram; dessas, 91% tiveram prejuízo, ~8% tiveram lucro médio diário até R$ 300 e só 0,8% (13 pessoas) acima de R$ 300/dia (~R$ 6.000/mês). Mini-dólar: 14.748 iniciantes, 92,3% desistiram, 1.131 (7,7%) persistiram — [Caderno CVM nº 15 – Day Trade](https://www.gov.br/investidor/pt-br/educacional/publicacoes-educacionais/cadernos/caderno-cvm-15-day_trade.pdf/@@display-file/file) (texto extraído do PDF oficial)
- Cobertura de 2020: amostra de 1.551 PFs com contratos de Ibovespa; 1,1% teve retorno líquido médio acima do salário mínimo e ~0,5% acima do salário de bancário em 300 pregões; os autores concluem que é "virtualmente impossível para pessoas físicas ganharem a vida como day traders" — [Money Times/Bloomberg](https://www.moneytimes.com.br/ganho-no-day-trade-nao-bate-salario-minimo-no-brasil/) (fonte secundária; a amostra de 1.551 e a de 1.558 do Caderno CVM diferem ligeiramente)
- Estudo de 2025 (Chague e Giovannetti, Revista Brasileira de Finanças, com dados da CVM): 968.512 PFs fizeram day trade entre o início da pandemia (2020) e dez/2023 e perderam R$ 9,9 bilhões (média R$ 10,2 mil por pessoa, antes de corretagem, taxas, cursos e plataformas); até 100 mil pessoas operavam por dia; dias com perda de 95,8% (antes da pandemia) e 96,4% (após março/2020) — [Monitor do Mercado](https://monitordomercado.com.br/noticias/307926-brasileiros-perderam-quase-r-10-bilhoes-com-day-trade-na-pandemia-diz-estudo-da-fgv/); [Monitor Mercantil](https://monitormercantil.com.br/brasileiros-perderam-r-99-bi-com-day-trade-durante-a-covid-19/). A reportagem não separa futuros de ações. O PDF primário da FGV retornou 503 e não foi lido.
- Perda média por ocupação (mesmo estudo, via imprensa): tabeliões R$ 86 mil; médicos R$ 34,9 mil; aposentados R$ 16,5 mil; estudantes R$ 3,6 mil — [Monitor do Mercado](https://monitordomercado.com.br/noticias/307926-brasileiros-perderam-quase-r-10-bilhoes-com-day-trade-na-pandemia-diz-estudo-da-fgv/)
- Investimento "comum" em ações por PFs (sem day trade): retorno médio anual ~8 p.p. abaixo do Ibovespa (ordens de 2012-2015 na B3, dados da CVM, FGV liderada por Giovannetti); causas: custos e vieses (excesso de confiança, efeito disposição) — [Gazeta do Povo](https://www.gazetadopovo.com.br/economia/retorno-medio-na-bolsa-brasileira-fica-abaixo-da-media-e-o-problema-nao-e-a-bolsa-0uzyizf2tvspv129wijfd70vm)
- Contraponto: Porcher Junior (2019, TCC de especialização PUCRS, advogado) argumenta que as evidências não demonstram que o day trade como profissão seja economicamente inviável nem que não haja evolução ao longo do tempo — [arXiv 1912.04274](https://arxiv.org/pdf/1912.04274). É texto não revisado por pares e de autor não-economista; serve como crítica metodológica, não como evidência contrária.
- Mecânica de alavancagem em futuros segundo o Caderno CVM: corretora exige "margem operacional" (exemplo de R$ 25 por minicontrato com R$ 1.000 em conta permite 40 contratos, nocional ~R$ 800 mil, "alavancagem de 800 vezes" com Ibovespa a 100.000 pontos); o investidor pode escolher alavancar menos (1 contrato = 20x). Margem de garantia da B3 pode ser dinheiro, títulos públicos e privados, cartas de fiança — [Caderno CVM nº 15](https://www.gov.br/investidor/pt-br/educacional/publicacoes-educacionais/cadernos/caderno-cvm-15-day_trade.pdf/@@display-file/file)
- CVM, Perfil e Comportamento do Investidor 2023: documento de 66 páginas contendo, na tabela de produtos, "derivativos" com 0,90% de uso (ver gap sobre interpretação); outras linhas mostram 1,45%, 7,56% e 24,17% para contratos derivativos em diferentes recortes que não consegui contextualizar — [CVM](https://www.gov.br/cvm/pt-br/centrais-de-conteudo/publicacoes/pesquisas/relatorio-perfil-e-comportamento-do-investidor-2023-serie-historica)
- Número "94% dos day traders perdem" (2026) circula em site de educação de trading; é material de marketing, não fonte primária. Não foi usado como evidência.

### Inferences
- O "97%" não é "97% de todos os day traders perdem": é 97% dos que sobreviveram 300 dias (a ~8% do total que começa). Contando quem desistiu antes (92% dos iniciantes), a taxa de insucesso do total que tentou é ainda maior, embora desistir cedo possa limitar a perda absoluta.
- Convergência de duas versões (91% em 2019, 97% em 2020) com metodologias distintas sugere que o resultado é robusto à especificação; o estudo de 2025 reforça com amostra muito maior e período diferente.
- Se a mediana PF perde ~R$ 10 mil e custo total (cursos, plataformas, corretagem) não está incluído, o resultado líquido real é pior que o reportado.
- Como o day trade tem 20% de IR sobre ganho sem compensação com outras operações, a barreira para lucro líquido é ainda maior.

### Gaps
- Não achei estudo CVM/B3 específico com percentual de PFs lucrativas em opções (nem em mini-dólar fora do recorte de 2019); a busca retornou só dados descritivos (ex.: >246 mil PFs em opções no 2º tri/2023, de um paper acadêmico) e risco teórico do lançador.
- Não li o PDF primário da FGV de 2025 nem o working paper 525 completo (bloqueios 503/Anubis); números dependem do abstract e de imprensa. Os números "98.378 iniciaram em 2013-2016 e só 554 persistiram >300 dias" apareceram em resumo de busca sem fonte verificável e não foram usados.
- Não coletei dados B3 recentes (2025-2026) sobre número de CPFs em futuros e participação de PFs.

---

## 3. Estratégias de alavancagem em bolsa e mercado de capitais (mecânica, custo e plausibilidade)

### Takeaway
No mercado de capitais, a alavancagem é embutida em produtos (futuros com margem, termo, opções, aluguel de ações, fundos alavancados, FIIs com dívida) e não exige empréstimo bancário; o risco é perda superior ao capital em alguns casos (venda a descoberto, lançamento de opções, fundos alavancados). Nenhuma delas é "carry grátis": o custo é o CDI implícito mais risco de preço.

### Cited Findings
- Aluguel de ações (BTC, B3): B3 é contraparte central; garantia de 100% do valor mais margem por papel; doador recebe a taxa e mantém proventos; taxa típica citada de 2% a 5% a.a. do valor, de 0,03% a 5% (ações líquidas) e podendo passar de 50% a.a. em papéis muito procurados; taxa de registro B3 de 0,25% a.a. (mínimo R$ 10), segundo uma fonte; o tomador perde se a ação subir (venda a descoberto) — [Forbes Brasil](https://forbes.com.br/forbes-money/2022/03/aluguel-de-acoes-entenda-o-que-e-e-como-funciona/), [Nord Investimentos](https://www.nordinvestimentos.com.br/blog/aluguel-de-acoes/). Valores de taxa e IR variam por fonte e data.
- Mercado a termo de ações (B3): compra com preço fixado e liquidação futura sem ajuste diário, exige margem de garantia; o preço a termo = preço à vista + juros negociados para o prazo (juro implícito), e não se confunde automaticamente com a Selic — [Bora Investir/B3](https://borainvestir.b3.com.br/glossario/mercado-a-termo/), [Renova Invest](https://renovainvest.com.br/blog/termo-de-acoes-o-que-e-e-como-funciona-esse-mercado/)
- Empréstimo com garantia de investimentos: a XP oferece "crédito colateralizado"; o LTV e o custo dependem da liquidez, duration e volatilidade do ativo dado em garantia; não foram divulgadas taxas CDI+ — [XP, material do produto](https://portal-rs.xpi.com.br/arquivos/BXP/Credito_colateralizado_CF.pdf) (PDF retornou 403; informação vem de resumo de busca)
- Conta de margem para ações com financiamento ao varejo: não encontrei fonte primária que descreva um produto padrão de margem de corretora para PF no Brasil (ver gap). Regulação consultada trata de fundos, não de corretoras: Ofício-Circular CVM/SIN 1/2026 esclarece "exposição a risco de capital com finalidade de alavancagem" na Resolução CVM 175 só para fundos dedicados ao público em geral; fundos long & short têm exceção ao limite de margem bruta do art. 73 — [CVM Ofício-Circular SIN 06/2023](https://conteudo.cvm.gov.br/cvm_institucional/export/sites/cvm/legislacao/oficios-circulares/sin/anexos/oc-sin-0623.pdf), [Legismap](https://legismap.com.br/conteudos/artigos-e-noticias/noticias-cvm-em-19-01-2026)
- Fundos multimercado alavancados: exemplo do fundo Versa Long Biased, que chegou a exposição bruta de 548% do patrimônio, com regulamento permitindo até 120% do patrimônio em garantias de margem e, em tese, chamada de capital a cotistas; outro fundo da mesma gestora (Versa Tracker) tinha exposição bruta de 1.147,5% — [NeoFeed](https://neofeed.com.br/negocios/o-que-explica-a-queda-da-gestora-versa/). Há registro de fundos multimercado com patrimônio líquido negativo (Pedra Dourada -R$ 65,66 mi, Conquest -R$ 13,55 mi, Eco Hedge -R$ 4,19 mi; o primeiro atribuído a reavaliação contábil de imóvel e não a perdas de mercado) — [Mais Retorno](https://maisretorno.com/portal/patrimonio-liquido-negativo-o-que-acontece-com-o-fundo-conheca-3-deles)
- FIIs com alavancagem: pela Instrução CVM 472 era proibida; a Lei 14.430/2022 e a Resolução CVM 200/2024 permitiram alavancagem moderada, inclusive em FIIs de varejo, e uso de ativos/imóveis como garantia; risco de chamada de capital em obrigações não relacionadas a projetos imobiliários, segundo interpretação da CVM — [Nord Investimentos](https://www.nordinvestimentos.com.br/blog/alavancagem-em-fundos-imobiliarios/), [Machado Meyer](https://machadomeyer.com.br/en/recent-publications/publications/investment-funds/fii-cvm-guidelines-on-limitation-of-liability-of-shareholders). Não confirmei o limite numérico vigente em 2026.
- COE (Certificado de Operações Estruturadas): em out/2025, investidores em COEs atrelados à dívida da Ambipar perderam até 93% do capital e os da Braskem 63%; COEs sem capital protegido não têm FGC; ~R$ 101,6 bilhões de PFs em COEs em out/2025 (Anbima), contra R$ 31,2 bilhões cinco anos antes; ~80% da carteira é de alta renda; vendidos majoritariamente por assessores com comissão paga integralmente na venda — [Bloomberg Línea](https://www.bloomberglinea.com.br/mercados/mercado-de-r-100-bi-perdas-com-crise-de-credito-expoem-riscos-e-conflitos-de-coes/)
- Tributação do day trade em ações e futuros: 20% (ver seção 1).

### Inferences
- Para operar futuros/opções/termo com R$ 1.000 a R$ 10.000, o "custo da alavancagem" não é cobrado como juro mas aparece como (i) CDI implícito no termo, (ii) taxa de aluguel no short, (iii) custo de oportunidade da margem em Tesouro Selic. Como o CDI está em ~13,65%, o termo carrega esse custo no preço: a ação precisa subir mais que ~13,65% a.a. (menos dividendos) só para empatar com renda fixa.
- Estratégias com payoff "ganho pequeno e perda grande" (lançamento coberto/descoberto de opções, COE com barreira, fundos alavancados) parecem renda fixa até o evento de cauda. Os COEs de 2025 são o exemplo concreto de varejo.
- Estratégias de "doador" no aluguel de ações (receber taxa por ações que já se tem) são alavancagem zero e têm retorno baixo (taxa de 0,03% a 5% a.a.), servindo mais como renda adicional que como estratégia de alavancagem.

### Gaps
- Sem dados sobre margens exigidas de mini-índice/mini-dólar hoje (B3/corretoras) e sem dados do custo efetivo de corretagem (muitas corretoras zeraram); só o exemplo de R$ 25 por minicontrato do Caderno CVM (2020).
- Não achei produto de "margem de corretora para compra de ações" no varejo brasileiro (diferente dos EUA); a pesquisa retornou fundos e Res. CVM 35/2021 não foi lida.
- Sem taxas CDI+ do crédito colateralizado (XP, BTG, etc.) ou do home equity pós-fixado.
- Debêntures incentivadas, CRI/CRA para PF alavancada: apenas o contexto tributário foi levantado; não pesquisei rendimentos, nem se há combinação "dívida cara + CRI isento" que supere o custo.
- Não investiguei opções (cobertas, travas) além dos riscos teóricos.

---

## 4. Cripto: futuros, perpétuos e empréstimo

### Takeaway
Para cripto, a evidência confiável de resultado de varejo no Brasil é escassa nesta rodada; o dado forte é o da maior liquidação da história (10/out/2025), que mostra o mecanismo de liquidação em cascata. A regulação do BC (Res. 519-521, em vigor desde fev/2026) endurece o ambiente de corretoras brasileiras.

### Cited Findings
- 10/out/2025: ~US$ 19 bilhões em posições alavancadas liquidadas após anúncio de tarifas de 100% dos EUA sobre a China, maior evento do tipo; Coinglass sugere que o valor nocional real pode ser maior (US$ 30-40 bilhões); houve falhas de precificação (oracle) na Binance, com reembolso de US$ 283 milhões — [resumo de busca](https://bitpinas.com/learn-how-to-guides/largest-liquidation/) (fontes variam; recomendar verificação em Coinglass ou Reuters)
- A Binance atribuiu o evento a risco macro e à alta alavancagem; segundo seu post-mortem de 30/jan/2026, 75% das liquidações ocorreram antes de dois problemas técnicos menores — [HTX News](https://www.htx.com/zh-cn/news/binance-says-macro-shock-not-exchange-failure-drove-octobers-3r1HDSWw/); versão contestada por petição no Change.org (não verificada) — [Change.org](https://www.change.org/p/investigate-binance-over-the-10-october-2025-crypto-crash)
- Resoluções BCB 519, 520 e 521 (nov/2025), em vigor em fev/2026: SPSAVs (prestadoras de serviços de ativos virtuais) precisam de sede no Brasil, capital mínimo (uma fonte cita R$ 10,8 milhões) e identificação de carteiras de autocustódia; as prestadoras existentes devem pedir autorização ao BC até 20/out/2026; uma fonte diz que há proibição de oferta de crédito por corretoras de cripto — [Pinheiro Guimarães](https://www.pinheiroguimaraes.com.br/banco-central-publica-novas-regras-para-criptoativos/), [Movimento Econômico](https://movimentoeconomico.com.br/opiniao/artigos/2025/11/12/regulamentacao-de-criptomoedas-pelo-bc-traz-um-novo-marco-para-o-setor/) (secundárias)
- CVM alertou sobre corretoras forex/CFD que listam derivativos de cripto sem autorização e suspendeu ofertas (XM Global, Albi, Infinox, Capitalia-Tradear); a CVM afirma que nenhuma instituição está autorizada a ofertar forex/CFD a varejo no Brasil e estendeu o alerta a influenciadores, com multa diária de R$ 1 mil — [Acionista](https://acionista.com.br/cvm-alerta-sobre-tres-corretoras-ofertando-derivativo-de-criptomoedas-no-brasil-sem-autorizacao/), [Okai](https://okai.com.br/noticia/2025-09-15/cfd-forex-um-alerta-para-proteger-investidores), [B3 Bora Investir](https://borainvestir.b3.com.br/tipos-de-investimentos/renda-variavel/day-trade/conheca-os-riscos-de-investir-em-mercados-nao-regulados-como-cfds-e-forex/)

### Inferences
- O regime de margem em perpétuos funciona como o dos futuros da B3 em termos de risco, mas sem circuit breakers e com oráculos de preço da própria exchange; um stop sob estresse pode ser acionado em preços piores.
- Dado que a CVM diz que forex/CFD a varejo não é autorizado no Brasil e a maioria das plataformas de perpétuos é offshore, o usuário perde recursos jurídicos locais (ressarcimento por MRP da B3 não se aplica).

### Gaps
- Nenhum estudo achado sobre a proporção de traders de varejo lucrativos em perpétuos (global ou brasileiro); a literatura (ex.: BIS, Bitget/Coinglass) não foi pesquisada.
- Não confirmei o texto das Res. BCB 519-521 sobre derivativos/alavancagem e crédito; as fontes são resumos jurídicos.
- Taxas de empréstimo cripto (Nexo, Binance Loans, DeFi) e liquidação de empréstimos colateralizados não foram pesquisadas.
- IR sobre cripto em 2026 não pesquisado.

---

## 5. Armadilhas de marketing e fraudes (gurus, mesas proprietárias, robôs, offshore, pirâmides)

### Takeaway
O padrão é prometer alavancagem alta, ganhos consistentes e "mesa própria" ou "robô" enquanto a evidência mostra perdas quase universais; a CVM e a PF têm casos de pirâmides disfarçadas de day trade e cripto. A pesquisa não localizou alertas específicos da CVM sobre "mesas proprietárias" em 2026.

### Cited Findings
- CVM/B3 mantêm a campanha #SeLigaNaCilada sobre armadilhas em redes sociais (2021) — [Okai](https://okai.com.br/noticia/2021-10-06/seliganacilada-campanha-da-cvm-e-b3-alerta-sobre-armadilhas-em-redes-sociais)
- Day trader com prejuízo de R$ 3,6 milhões a clientes recebeu restrição da CVM por 69 meses (até jul/2028) por exercer irregularmente a administração de carteiras/fundos (captava recursos de terceiros, atividade restrita a instituições autorizadas) — [Suno](https://www.suno.com.br/noticias/?p=312810), [Eu Quero Investir](https://euqueroinvestir.com/acoes/daytrader-banido-cvm-2028)
- PF: Operação "Traders" (grupo que se dizia de day traders e movimentou mais de R$ 200 milhões; o aplicado resultava em prejuízo); Operação "La Casa de Papel" (prejuízo estimado de R$ 4,1 bilhões, mais de 80 países); Operação Poyais (aluguel de criptoativos com promessa de até 20% a.m. e ~R$ 4 bilhões movimentados); Operação Kryptos (591 BTC apreendidos, ~R$ 150 milhões) — [BP Money](https://bpmoney.com.br/politica/policia-federal-investiga-piramide-financeira-de-day-traders/), [Money Times](https://www.moneytimes.com.br/pf-combate-organizacao-criminosa-suspeita-de-fraudes-bilionarias-com-criptomoedas-no-brasil-e-exterior/), [CNN Brasil](https://www.cnnbrasil.com.br/nacional/pf-faz-operacao-contra-fraudes-bilionarias-envolvendo-criptomoedas/) (datas e valores vêm de resumos de busca; verificar antes de citar no relatório)
- Prejuízo médio do day trade na pandemia (R$ 10,2 mil por PF) e o fato de que cursos/plataformas não entram na conta indicam que o negócio dos "gurus" é vender educação a uma população que perde (ver seção 2).

### Inferences
- Sinais de alerta práticos: promessa de retorno fixo mensal, "alavancagem ilimitada", captação de dinheiro de terceiros por PF, corretora fora da lista da CVM/BC, pagamento de bônus por indicação.
- Mesas proprietárias com avaliação paga (taxa para "passar no teste") são um modelo de negócio em que a receita da mesa vem de quem falha o teste, estrutura análoga ao da casa de apostas; isso é inferência minha, sem fonte nesta rodada.

### Gaps
- Sem fonte sólida sobre prop firms no Brasil (taxas de avaliação, taxa de aprovação, alertas CVM).
- Sem dados sobre "robôs" vendidos a varejo (desempenho, ações da CVM).
- Fórum Reddit (r/investimentos), Clube do Valor e comunidades de trading não foram pesquisados.

---

## 6. O que é plausível, o que é desenhado para perder, e o que seria alavancagem prudente

### Takeaway
Do ponto de vista matemático, alavancagem só faz sentido quando o custo da dívida é claramente menor que o retorno esperado e estável de um ativo com fluxo de caixa; no Brasil de 2026, com CDI 13,65%, quase nada de varejo atende a esse critério. Alavancar em instrumentos de resultado negativo comprovado (day trade, forex/CFD, opções vendidas) aumenta o risco sem ter retorno esperado positivo.

### Cited Findings
- Veja as seções 1 a 5; esta seção é síntese. Evidências usadas: custo do crédito (BCB), retorno de renda fixa (CDI, Tesouro), perda do day trade (FGV/CVM), COE (Bloomberg Línea).

### Inferences
Classificação preliminar (julgamento meu, baseado nas evidências acima):
- Carry negativo, não-viável: consignado INSS/CLT, pessoal, cheque especial, cartão, saque-aniversário (juro desconhecido, mas FGTS antecipado cobra juros e há perda do saque na demissão) para aplicar em renda fixa; a diferença de taxa vai de -12,5 p.p. (INSS) a -99 p.p. (pessoal).
- Carry quase nulo, com risco de ativo: financiamento imobiliário (11,28% a.a.) vs LCA 90% CDI (12,29%); home equity no melhor caso (14,3% a.a.) vs 11,6% líquido (CDB) ou 12,29% (LCA), -2,0 a -2,7 p.p.
- Desenhadas para perder (evidência empírica do varejo): day trade em mini-índice/mini-dólar (91%-97% de perdas entre persistentes); forex/CFD (não autorizado); mesas proprietárias e robôs sem registro; pirâmides.
- Plausível apenas com ativos de retorno esperado alto, risco controlado e prazo longo; alavancagem baixa e sem chamada de margem. Exemplo: recursos próprios em Tesouro IPCA+ (~6,7% real) com colateral e sem dívida a prazo curto; ou ativos com fluxo de caixa de longo prazo (imóvel alugado, empresa) em que o retorno do aluguel/dividendo exceda o custo da dívida de longo prazo. Esta é uma inferência: a pesquisa não encontrou uma estratégia de varejo com spread positivo documentado.
- Regra prática (minha): custo efetivo da dívida (incluindo IOF e tarifas) < retorno esperado líquido do ativo, com folga para quedas de preço (queda que zera o capital = 1/(1+L)), e dívida sem margin call.

### Gaps
- Não pesquisei o retorno esperado de ações/FIIs/imóveis (aluguel/valor) para comparar com o custo da dívida de longo prazo.
- Não pesquisei crédito para empresas/PJ (capital de giro) nem debêntures incentivadas como estratégia de alavancagem para PF.

---

## 7. O que merece aprofundamento na Fase 2

### Takeaway
Prioridade: (1) matemática de carry e break-even com custos reais (home equity, financiamento imobiliário vs ativos com fluxo de caixa); (2) evidência rigorosa de resultados de futuros/opções; (3) cripto leverage e armadilhas; (4) produtos estruturados.

### Cited Findings
- Veja seções anteriores.

### Inferences
Sugestão de sub-temas para Fase 2, em ordem de valor:
1. **Home equity e financiamento imobiliário vs ativos com yield**: obter cotações reais (CET, indexador, prazo, LTV, custos de cartório/ITBI/avaliação), comparar com aluguel líquido, FIIs de tijolo/papel, LCA/LCI, Tesouro IPCA+ e debêntures incentivadas; fazer cenários de estresse (Selic subindo, queda do ativo).
2. **Opções e futuros em bolsa**: obter o estudo de opções (CVM/B3/FGV) e dados de PFs em derivativos; entender quem lucra (market makers/HFT); margens atuais de mini-índice/dólar.
3. **Cripto**: perpétuos (BIS/Coinglass), empréstimos colateralizados, regulação do BC (texto oficial) e IR.
4. **Estruturados e fundos alavancados**: COE (regras, comissões, casos 2025), multimercados alavancados (chamada de capital), FIIs/Fiagro com dívida.
5. **Crédito com garantia de investimentos e margem de corretora**: taxas e LTV reais em XP/BTG/Itaú/Nu; margin call; IOF.
6. **Saque-aniversário e consignado como fonte de capital**: custo real (CET), regras do FGTS em nov/2026, riscos de perda de saque na demissão; comparar com alternativas.
7. **Golpes e prop firms**: lista de alertas CVM, casos de PF/MP, perfil de marketing.
8. **Comunidades**: Reddit r/investimentos, Clube do Valor, relatos de endividamento para investir, como complemento qualitativo.

### Gaps
- Esta fase não cobriu comunidades (Reddit, Clube do Valor), nem estudos acadêmicos internacionais sobre alavancagem de varejo (ex.: Barber/Odean, Heimer/Imas) e nem a experiência de empréstimos margin nos EUA.
