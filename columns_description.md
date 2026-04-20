# Descrição das Colunas — Dataset FBRef 2020/21

Todas as métricas de jogo são calculadas **por 90 minutos** (sufixo `/90`), exceto onde indicado. Isso permite comparar jogadores com diferentes volumes de minutos jogados.

---

## Identificação

| Coluna | Descrição |
|---|---|
| `Player` | Nome do jogador |
| `Nation` | Nacionalidade |
| `Pos` | Posição principal (GK, DF, MF, FW e combinações) |
| `Squad` | Time |
| `Comp` | Liga |
| `Age` | Idade na temporada |
| `Born` | Ano de nascimento |
| `MP` | Partidas disputadas |
| `Starts` | Partidas como titular |
| `Min` | Minutos jogados na temporada |
| `90s` | Equivalente em partidas completas (Min ÷ 90) |

---

## Ataque e Finalização

| Coluna | Descrição |
|---|---|
| `Ast/90` | Assistências por 90 min |
| `npG/90` | Gols sem pênaltis por 90 min — medida pura de produção ofensiva |
| `npG+A/90` | Gols + assistências sem pênaltis por 90 min |
| `xA/90` | Expected assists — qualidade esperada das bolas-passe que geraram chutes |
| `npxG/90` | Non-penalty expected goals — qualidade das chances de gol recebidas |
| `npxG+xA/90` | Soma de npxG e xA — contribuição ofensiva esperada total |
| `Shots/90` | Total de chutes por 90 min |
| `SoTs/90` | Chutes no alvo por 90 min |
| `SoT%` | Percentual de chutes no alvo |
| `Gls/Shot` | Gols por chute (taxa de conversão bruta) |
| `Gls/SoT` | Gols por chute no alvo (eficiência de finalização) |
| `AvgShotDist` | Distância média dos chutes (em jardas) — indicador de qualidade posicional |
| `FKSht/90` | Chutes de falta por 90 min |
| `npxG/Shot` | xG médio por chute — qualidade das posições de finalização |
| `np:G-xG` | Gols sem pênaltis menos xG — indica se o jogador supera (`+`) ou decepciona (`-`) o esperado |

---

## Passes — Volume e Precisão

| Coluna | Descrição |
|---|---|
| `PassCmp/90` | Passes completados por 90 min |
| `PassAtt/90` | Passes tentados por 90 min |
| `PassCmp%` | Percentual de acerto de passe |
| `TotDistPass/90` | Distância total percorrida pelos passes por 90 min |
| `PrgDistPass/90` | Distância progressiva percorrida pelos passes — quanto a bola avançou em direção ao gol |

---

## Passes — Por Comprimento

| Coluna | Descrição |
|---|---|
| `ShortCmp/90` | Passes curtos completados por 90 min (< 5 jardas) |
| `ShortAtt/90` | Passes curtos tentados por 90 min |
| `ShortCmp%` | Precisão em passes curtos |
| `MedCmp/90` | Passes médios completados por 90 min (5–25 jardas) |
| `MedAtt/90` | Passes médios tentados por 90 min |
| `MedCmp%` | Precisão em passes médios |
| `LongCmp/90` | Passes longos completados por 90 min (> 25 jardas) |
| `LongAtt/90` | Passes longos tentados por 90 min |
| `LongCmp%` | Precisão em passes longos — relevante para goleiros e zagueiros |

---

## Passes — Qualidade e Destino

| Coluna | Descrição |
|---|---|
| `KeyPass/90` | Passes-chave por 90 min — passes que resultam diretamente em chute |
| `PassIntoThird/90` | Passes completados para o terço final por 90 min |
| `PassIntoBox/90` | Passes completados dentro da grande área por 90 min (excluindo cruzamentos) |
| `CrossIntoBox/90` | Cruzamentos completados dentro da grande área por 90 min |
| `ProgPass/90` | Passes progressivos — avançam a bola ≥ 10 jardas em direção ao gol adversário |
| `TBCmp/90` | Through balls completados — passes que rompem a última linha defensiva |
| `PassUnderPress/90` | Passes executados enquanto sofria pressão defensiva — resistência sob marcação |
| `Switches/90` | Mudanças de flanco (passes longos transversais) por 90 min |
| `Crosses/90` | Cruzamentos totais por 90 min |

---

## Passes — Tipo de Bola

| Coluna | Descrição |
|---|---|
| `LivePassAtt/90` | Passes em jogo corrido tentados por 90 min |
| `DeadPassAtt/90` | Passes em bola parada tentados por 90 min |
| `FKPassAtt/90` | Passes em falta tentados por 90 min |
| `GroundPass/90` | Passes rasos tentados por 90 min |
| `LowPass/90` | Passes baixos (abaixo da cintura) tentados por 90 min |
| `HighPass/90` | Passes altos (acima da cintura) tentados por 90 min |
| `LeftPass/90` | Passes com pé esquerdo tentados por 90 min |
| `RightPass/90` | Passes com pé direito tentados por 90 min |
| `HeadPass/90` | Passes de cabeça tentados por 90 min |
| `ThrowPass/90` | Lançamentos de arremesso tentados por 90 min |
| `OtherPartPass/90` | Passes com outras partes do corpo por 90 min |

---

## Passes — Resultados Negativos

| Coluna | Descrição |
|---|---|
| `OffsidePass/90` | Passes para jogadores em posição de impedimento por 90 min |
| `OutOBPass/90` | Passes que saíram pela linha por 90 min |
| `PassesInt/90` | Passes interceptados pelo adversário por 90 min |
| `PassesBlk/90` | Passes bloqueados pelo adversário por 90 min |

---

## Criação de Oportunidades (SCA / GCA)

Ações que precedem diretamente um chute (SCA) ou um gol (GCA), contando os dois últimos eventos antes da finalização.

| Coluna | Descrição |
|---|---|
| `SCA/90` | Shot-creating actions — ações que resultam em chute por 90 min |
| `PassLiveSCA/90` | Passes em jogo corrido que levaram a chute |
| `PassDeadSCA/90` | Passes em bola parada que levaram a chute |
| `DribSCA/90` | Dribles que levaram a chute |
| `ShSCA/90` | Chutes que geraram chute rebatido |
| `FoulSCA/90` | Faltas sofridas que geraram oportunidade de chute |
| `DefSCA/90` | Ações defensivas que iniciaram contra-ataque com chute |
| `GCA/90` | Goal-creating actions — ações que resultam em gol por 90 min |
| `PassLiveGCA/90` | Passes em jogo corrido que levaram a gol |
| `PassDeadGCA/90` | Passes em bola parada que levaram a gol |
| `DribGCA/90` | Dribles que levaram a gol |
| `ShGCA/90` | Chutes que geraram gol rebatido |
| `FoulGCA/90` | Faltas sofridas que geraram gol |
| `DefGCA/90` | Ações defensivas que iniciaram contra-ataque com gol |

---

## Defesa — Desarmes

| Coluna | Descrição |
|---|---|
| `TklAtt/90` | Tentativas de desarme por 90 min |
| `TklW/90` | Desarmes bem-sucedidos por 90 min |
| `Def 3rdTkl/90` | Desarmes no terço defensivo por 90 min |
| `Mid 3rdTkl/90` | Desarmes no meio-campo por 90 min |
| `Att 3rdTkl/90` | Desarmes no terço ofensivo por 90 min |
| `TklvDribW/90` | Desarmes vencidos contra dribles por 90 min |
| `TklvDribAtt/90` | Tentativas de desarme contra dribles por 90 min |
| `Tkl%vDrib` | Taxa de sucesso em duelos de drible (%) |
| `DribPast/90` | Vezes que o jogador foi dribládoo por 90 min |

---

## Defesa — Pressão

| Coluna | Descrição |
|---|---|
| `PressAtt/90` | Pressões tentadas sobre adversário com bola por 90 min |
| `SuccPress/90` | Pressões que resultaram em posse de bola por 90 min |
| `PressSucc%` | Taxa de sucesso na pressão defensiva (%) |
| `Def 3rdPress/90` | Pressões no terço defensivo por 90 min |
| `Mid 3rdPress/90` | Pressões no meio-campo por 90 min |
| `Att 3rdPress/90` | Pressões no terço ofensivo por 90 min — indicador de pressing alto |

---

## Defesa — Bloqueios e Intervenções

| Coluna | Descrição |
|---|---|
| `Blocks/90` | Total de bloqueios por 90 min |
| `ShotBlocks/90` | Bloqueios de finalização por 90 min |
| `PassBlk/90` | Bloqueios de passe por 90 min |
| `Interceptions/90` | Interceptações por 90 min — leitura de jogo e antecipação |
| `Clearances/90` | Cortes por 90 min — alívio defensivo sob pressão |
| `ErrToShot/90` | Erros individuais que geraram chute ao adversário por 90 min |

---

## Toques e Zonas de Atuação

| Coluna | Descrição |
|---|---|
| `Touches/90` | Total de toques na bola por 90 min |
| `Def PenTchs/90` | Toques na área defensiva própria por 90 min |
| `Def 3rdTchs/90` | Toques no terço defensivo por 90 min |
| `Mid 3rdTchs/90` | Toques no meio-campo por 90 min |
| `Att 3rdTchs/90` | Toques no terço ofensivo por 90 min |
| `Att PenTchs/90` | Toques na área adversária por 90 min — presença na zona de finalização |
| `%TchsDefPen` | % dos toques na área defensiva — valores baixos indicam goleiro avançado |
| `%TchsDefThrd` | % dos toques no terço defensivo |
| `%TchsMidThrd` | % dos toques no meio-campo |
| `%TchsAttThrd` | % dos toques no terço ofensivo |
| `%TchsAttPen` | % dos toques na área adversária — indica perfil de atacante de área |
| `LiveTchs/90` | Toques em bola em jogo corrido por 90 min |

---

## Condução de Bola (Carries)

| Coluna | Descrição |
|---|---|
| `Carries/90` | Conduções de bola por 90 min |
| `TotDistCarry/90` | Distância total percorrida com a bola por 90 min |
| `PrgDistCarry/90` | Distância progressiva percorrida com a bola — quanto avançou em direção ao gol |
| `ProgCarry/90` | Conduções progressivas — avançam a bola ≥ 10 jardas em direção ao gol |
| `CarryIntoThird/90` | Conduções que entram no terço final por 90 min |
| `CarryIntoBox/90` | Conduções que entram na grande área por 90 min |
| `Miscontrol/90` | Erros de controle por 90 min — perda de domínio da bola |
| `Dispossessed/90` | Vezes desapossado por adversário por 90 min |

---

## Dribles

| Coluna | Descrição |
|---|---|
| `SuccDrib/90` | Dribles bem-sucedidos por 90 min |
| `AttDrib/90` | Dribles tentados por 90 min |
| `DribSucc%` | Taxa de sucesso nos dribles (%) |
| `PlayersDribPast/90` | Jogadores adversários ultrapassados por ribble por 90 min |
| `Megs/90` | Canetas (nutmegs) por 90 min |

---

## Recepção de Passes

| Coluna | Descrição |
|---|---|
| `PassTarget/90` | Vezes que o jogador foi alvo de passe por 90 min |
| `PassesReceived/90` | Passes efetivamente recebidos por 90 min |
| `PassRec%` | Percentual de passes-alvo recebidos com sucesso |
| `ProgPassReceived/90` | Passes progressivos recebidos por 90 min — indicador de movimentação e mobilidade |
