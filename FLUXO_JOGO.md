# Fluxo do Jogo — As Crônicas de Arandell

> Documento gerado a partir de `arandell-rpg.html` (SCENES_DATA + ENDINGS_DATA). Reflete o estado atual do jogo.

## Sistema Narrativo

- **Eixos de identidade**: Compaixão (C) · Ambição (A) · Vínculo (V) — 0–5 cada, por jogador
- **Mundo sistêmico**: Calor 🌡️ · Esperança ✨ · Controle da Rainha 👁 — 0–5 cada, com inércia
- **Caminho irreversível**: definido uma vez em `cena_s4_010` (Resistência/Equilíbrio/Corrupção)
- **Perdas irreversíveis** (flags críticas, máx 3): `finn_morto`, `aldeia_destruida`, `beron_inimigo`
- **Flags emergentes** (derivadas de tags): `egoista_cronico`, `propenso_ao_sacrificio`, `manipulou_ambos_lados`, `ancora_do_grupo`, `abandonou_conflito`, `perdeu_todos_aliados`, `dominou_serafina`
- **Virtude/Tentação**: mantidos apenas como recurso gastável (rerolls/bônus), não medem mais identidade
- **9 finais** organizados por caminho (3 por caminho), com prioridade numérica e fallback

---

## Totais

| Sessão | Cenas | Decisões | Narrativas |
|---|---|---|---|
| Eventos | 3 | 0 | 3 |
| 1 | 6 | 2 | 4 |
| 2 | 8 | 3 | 5 |
| 3 | 9 | 2 | 7 |
| 4 | 9 | 4 | 5 |
| 5 | 7 | 3 | 4 |
| 6 | 7 | 1 | 6 |
| 7 | 7 | 2 | 5 |
| 8 | 11 | 1 | 10 |

**Totais:** 67 cenas · 18 decisões.

---

## Finais

| ID | Título | Caminho | Prioridade | Flag obrigatória | Eixos | Mundo |
|---|---|---|---|---|---|---|
| `cena_final_01` | A Redenção | resistencia | 10 | fortaleza_interior, salvou_finn, perdoou_beron | compaixao≥4, vinculo≥3 | calor≥3, esperanca≥3 |
| `cena_final_09` | Domínio Frio | corrupcao | 10 | marcado_corrupcao, beron_inimigo?, finn_morto? | ambicao≥5 | controle_rainha≥5 |
| `cena_final_07` | Traição Silenciosa | equilibrio | 9 | manipulou_ambos_lados | ambicao≥2 | controle_rainha≥3 |
| `cena_final_02` | A Corrupção | corrupcao | 8 | aceita_convite_rainha, dominou_serafina | ambicao≥4 | controle_rainha≥4 |
| `cena_final_06` | Vitória Frágil | resistencia | 8 | fortaleza_interior, finn_morto?, aldeia_destruida? | compaixao≥3 | — |
| `cena_final_08` | Fuga Estratégica | equilibrio | 7 | abandonou_conflito | vinculo≤2 | — |
| `cena_final_03` | O Sacrifício | resistencia | 6 | fez_sacrificio | vinculo≥3 | — |
| `cena_final_04` | O Equilíbrio | equilibrio | 5 | dividido | compaixao≥2, compaixao≤3, ambicao≥2, ambicao≤3 | — |
| `cena_final_05` | O Fracasso | corrupcao | 5 | perdeu_todos_aliados?, egoista_cronico? | ambicao≥3, vinculo≤1 | — |

---

## Fluxo de Cenas (Decisões com impactos C/A/V/mundo)

### Sessão 1

- **cena_s1_002 · Além do Espelho** — 3 opções
  - Entrar pelo espelho → `cena_s1_003`
  - Sentir o que há além *[Espírito DC8]* → `cena_s1_004 / cena_s1_003`
  - Hesitar e recuar → `cena_s1_003`

- **cena_s1_005 · Primeiro Choque** — 3 opções
  - Explorar juntos [V+1] `[lealdade,coletivo]` → `cena_s1_006`
  - Esconder-se entre as árvores → `cena_s1_006`
  - Chamar por socorro *[Coração DC6]* → `cena_s1_006`

### Sessão 2

- **cena_s2_001 · O Fauno Ferido** — 2 opções
  - Ajudar Finn imediatamente [C+1, V+1] `[compaixao,lealdade]` mundo:e+1 npcs:finn → `cena_s2_002`
  - Ignorar e seguir a missão [C-1, A+1] `[egoismo,covardia]` mundo:e-1 npcs:finn → `cena_s2_003`

- **cena_s2_003 · Guardiões de Gelo** — 3 opções
  - Defender Finn *[Corpo DC9]* [C+1, V+1] `[coragem,lealdade]` npcs:finn → `cena_s2_005 / cena_s2_007`
  - Fugir sem Finn [C-1, A+1, V-1] `[egoismo,manipulacao]` mundo:e-1 npcs:finn → `cena_s2_007`
  - Criar distração *[Mente DC8]* `[esperteza,coletivo]` → `cena_s2_005 / cena_s2_007`

- **cena_s2_006 · A Oferta** — 2 opções
  - Aceitar a oferta [A+1] `[ambicao,pragmatismo]` mundo:c+1 → `cena_s2_008`
  - Recusar a oferta [A-1] `[resistencia,integridade]` mundo:c-1 → `cena_s2_008`

### Sessão 3

- **cena_s3_002 · Nessa, a Anciã** — 2 opções
  - Ouvir com atenção [C+1, A-1] `[compaixao,sabedoria]` mundo:e+1 npcs:nessa → `cena_s3_006`
  - Ignorar e seguir [C-1, A+1] `[egoismo,covardia]` mundo:e-1 npcs:nessa → `cena_s3_003`

- **cena_s3_007 · O Convite** — 2 opções
  - Aceitar o convite [A+1] `[ambicao,pragmatismo]` mundo:c+1 → `cena_s3_008`
  - Recusar o convite [A-1] `[resistencia,integridade]` mundo:c-1 → `cena_s3_009`

### Sessão 4

- **cena_s4_002 · Os Jardins de Pedra** — 3 opções
  - Parar e lamentar [C+1] `[compaixao]` → `cena_s4_003`
  - Continuar sem olhar [C-1, A+1] `[egoismo,covardia]` mundo:e-1 → `cena_s4_003`
  - Tentar tocar uma estátua *[Espírito DC8]* → `cena_s4_003`

### Sessão 5

- **cena_s5_002 · Beron, o Arrependido** — 2 opções
  - Perdoar Beron [C+1] `[perdao,compaixao]` mundo:e+1 npcs:beron → `cena_s5_003`
  - Rejeitar Beron [C-1, V-1] `[dureza,pragmatismo]` npcs:beron 🔔 → `cena_s5_004`

- **cena_s5_005 · Ponto do Degelo** — 3 opções
  - Nutrir com Espírito *[Espírito DC8]* → `cena_s5_006`
  - Estudar com Mente *[Mente DC7]* → `cena_s5_006`
  - Continuar [A+1] `[ambicao,pragmatismo]` mundo:c+1 → `cena_s5_006`

- **cena_s5_006 · Um ou Todos** — 3 opções
  - Salvar Finn [C+1, V+1] `[compaixao,lealdade]` mundo:e+1 npcs:finn 🔔 → `cena_s5_007`
  - Ajudar a aldeia [C+1, V+1] `[compaixao,lealdade]` mundo:e+1 🔔 → `cena_s5_007`
  - Tentar salvar ambos [C+1, A+1] `[hybris,compaixao]` mundo:e-1 → `cena_s5_007`

### Sessão 6

- **cena_s6_002 · Três Provas** — 3 opções
  - Prova do Sacrifício Simbólico **{resistencia}** [C+1, A-1, V+1] `[sacrificio,fortaleza,coragem]` mundo:e+1 → `cena_s6_003`
  - Prova da Escolha Dupla **{equilibrio}** [A+1, V+1] `[dualidade,pragmatismo,dividido]` mundo: → `cena_s6_003`
  - Prova do Sacrifício de Outro **{corrupcao}** [C-1, A+2, V-1] `[ambicao,dominacao,sacrificio_alheio]` mundo:c+1 🔔 → `cena_s6_003`

### Sessão 7

- **cena_s7_002 · Momento de Escolha** — 2 opções
  - Entrar com coração puro → `cena_s7_003v`
  - Entrar com determinação → `cena_s7_004`

- **cena_s7_004 · Redenção** — 2 opções
  - Realizar o sacrifício [C+2, V+2] `[sacrificio,compaixao]` mundo:e+1 → `cena_s7_005`
  - Recusar o sacrifício [C-1, A+1, V-1] `[covardia,preservacao]` mundo:e-1 → `cena_s7_005`

### Sessão 8

- **cena_s8_002 · Decisão Derradeira** — 5 opções
  - Oferecer perdão [C+2, V+2] `[compaixao,lealdade]` mundo:e+2,c-2 npcs:nessa → `cena_final_01`
  - Destruir fonte de poder [C+1] `[compaixao]` → `cena_final_03`
  - Aceitar poder dela [A+2] `[ambicao,poder]` mundo:c+1 🔔 → `cena_final_02`
  - Fugir com libertados [C+1, V+1] `[fuga,compaixao]` mundo:e+1 → `cena_final_05`
  - Oferecer fuga a Serafina [C+2, V+2] `[coragem,lealdade]` → `cena_final_04`

### Sessão 4

- **cena_s4_003 · A Rainha Serafina** — 2 opções
  - Confrontar diretamente [C+1] `[compaixao]` → `cena_s4_007`
  - Fingir confiar [A+1] `[ambicao,pragmatismo]` mundo:c+1 → `cena_s4_008`

- **cena_s4_005 · O Presente da Rainha** — 2 opções
  - Aceitar o presente [A+1] `[ambicao,poder]` mundo:c+1 → `cena_s4_009`
  - Recusar o presente [A-1] `[resistencia,integridade]` mundo:c-1 → `cena_s4_006`

- **cena_s4_007 · Prisioneiros no Gelo** — 2 opções
  - Usar Espírito para resistir *[Espírito DC9]* → `cena_s4_006 / cena_s4_009`
  - Enganar guarda *[Mente DC8]* → `cena_s4_006 / cena_s4_009`

### Eventos Sistêmicos (injetados dinamicamente)

### Sessão 8

