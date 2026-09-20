# Programação Semanal de Obras · Baluarte Engenharia

> Empresa, obras, pessoas e dados **100% fictícios**, criados para portfólio.

## A dor

Em quase todo setor (obra, manutenção, facilities, produção) a programação da semana mora numa planilha que só quem a montou consegue ler. Fiscais, encarregados e gestores não enxergam o que está previsto para cada dia, quem faz o quê, nem o quanto do planejado foi de fato executado. O resultado: reunião de segunda sem visão comum, mão de obra ociosa sem ninguém perceber e apontamento atrasado.

## A solução

Um painel Power BI que lê as planilhas semanais como elas já são (uma por semana, uma aba por obra) e mostra, em uma tela:

- **Programado x realizado**: atividades, ordens de serviço (OS) e HH, com variação contra a semana anterior.
- **HH subutilizado** e % do programado, com mensagem de fechamento para a reunião.
- **Linhas aguardando apontamento** (atividades passadas sem EXECUÇÃO preenchida).
- **Calendário do mês aberto por semana**, uma linha por fiscal, com as atividades de cada dia.
- **Detalhe por atividade**, com saldo de HH, situação (Sobrou / Reforço / Conforme) e realocação de equipe.

## A empresa fictícia

**Baluarte Engenharia** toca duas obras:

| Obra (aba) | Escopo | Fiscal | Encarregados |
|---|---|---|---|
| Residencial Vila Serena | 2 torres residenciais: estrutura, alvenaria, instalações, acabamentos, áreas comuns | Duarte, Nogueira | Jorge Lima, Wesley Santos, Cleiton Rocha, Edson Barreto |
| Centro Logístico Rota 116 | Galpão logístico: terraplenagem, fundações, pré-moldados, drenagem, pavimentação | Prado | Adriano Melo, Ronaldo Freitas |

Semanas **35 a 39/2026**, com história para contar:

| Semana | O que acontece |
|---|---|
| 35 | Semana “limpa”: programado ≈ realizado |
| 36 | Chuva forte na quarta e quinta: frentes externas paradas, equipe remanejada para serviços internos (maior HH subutilizado) |
| 37 | Feriado de 7/set e atraso na entrega de aço |
| 38 | Entrega parcial de blocos, reforço na concretagem e apontamentos pendentes de sexta e sábado |
| 39 | Próxima semana, só programada |

## Como abrir

1. Abra `Programacao_Semanal.pbip` no Power BI Desktop.
2. Em **Transformar dados > Editar parâmetros**, troque `PastaProgramacao` (valor de exemplo: `C:\Projetos\Programacao_Semanal`) pelo caminho da pasta onde estão as planilhas `PROGRAMAÇÃO SEMANA nn.xlsx` no seu computador.
3. Atualize os dados.

O painel usa a medida oculta `Data Referência` (fixa em 20/09/2026) no lugar de `TODAY()`, para o retrato do portfólio não mudar com o tempo. Em uso real, troque por `TODAY()`.

## Estrutura

- `PROGRAMAÇÃO SEMANA 35…39.xlsx`: bases semanais (formato original: cabeçalho na linha 4, blocos por dia, colunas DUR / NUM / EXECUÇÃO).
- `Programacao_Semanal.SemanticModel`: modelo (fato de programação, dimensões, calendário, medidas).
- `Programacao_Semanal.Report`: relatório (capa, visão semanal, dica de ferramenta).
- `assets/`: logotipo fictício.

## Paleta

| Uso | Cor |
|---|---|
| Fundo | `#0D1420` |
| Superfícies | `#16202F` · `#1C2A3D` · `#293C56` |
| Azul aço (primária) | `#1F5FA8` · `#5CA4E6` |
| Laranja de segurança (destaque) | `#F28C28` |
| Positivo / negativo | `#4FC08D` / `#F0627A` |
| Texto | `#EEF2F8` · `#C5CCD8` · `#A4ACBA` |
