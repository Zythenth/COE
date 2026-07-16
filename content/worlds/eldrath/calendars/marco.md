---
schema_version: "1.0.0"
id: "calendar.marco"
name: "Calendário do Marco"
content_status: in_review
tags: []
aliases: []
summary: >-
  Calendário civil e histórico de ciclo fixo, organizado em dez períodos,
  cinco estações e semanas de seis dias para registro e cálculo previsíveis.
references: []
art: []
notes: |-
  As divisões e os nomes são convenções cronológicas gerais. Não afirmam uma
  astronomia, um clima universal, uma religião, uma cultura, um reino ou um
  acontecimento histórico específico. Os nomes dos dias não impõem jornadas,
  cultos ou descansos. A data inicial do mundo, a adoção institucional e as
  correspondências climáticas locais permanecem reservadas às entidades e
  etapas futuras responsáveis.
epoch:
  name: "Marco da Contagem"
  description: >-
    Limite convencional que separa as duas eras e fornece um ponto zero para
    cálculo, sem criar um ano zero nem atribuir o marco a uma entidade ainda
    inexistente.
eras:
  - id: "era.antes_do_marco"
    name: "Antes do Marco"
    order: 1
  - id: "era.pos_marco"
    name: "Pós-Marco"
    order: 2
months:
  - id: "month.abertura"
    name: "Abertura"
    order: 1
    days: 36
    season_id: "season.alvor"
  - id: "month.semente"
    name: "Semente"
    order: 2
    days: 36
    season_id: "season.alvor"
  - id: "month.ascensao"
    name: "Ascensão"
    order: 3
    days: 36
    season_id: "season.elevacao"
  - id: "month.fulgor"
    name: "Fulgor"
    order: 4
    days: 36
    season_id: "season.elevacao"
  - id: "month.coroa"
    name: "Coroa"
    order: 5
    days: 36
    season_id: "season.plenitude"
  - id: "month.maturacao"
    name: "Maturação"
    order: 6
    days: 36
    season_id: "season.plenitude"
  - id: "month.virada"
    name: "Virada"
    order: 7
    days: 36
    season_id: "season.declinio"
  - id: "month.ocaso"
    name: "Ocaso"
    order: 8
    days: 36
    season_id: "season.declinio"
  - id: "month.bruma"
    name: "Bruma"
    order: 9
    days: 36
    season_id: "season.resguardo"
  - id: "month.guarda"
    name: "Guarda"
    order: 10
    days: 36
    season_id: "season.resguardo"
weekdays:
  - id: "weekday.alva"
    name: "Alva"
    order: 1
  - id: "weekday.lume"
    name: "Lume"
    order: 2
  - id: "weekday.brasa"
    name: "Brasa"
    order: 3
  - id: "weekday.nexo"
    name: "Nexo"
    order: 4
  - id: "weekday.veu"
    name: "Véu"
    order: 5
  - id: "weekday.ancora"
    name: "Âncora"
    order: 6
seasons:
  - id: "season.alvor"
    name: "Alvor"
    order: 1
  - id: "season.elevacao"
    name: "Elevação"
    order: 2
  - id: "season.plenitude"
    name: "Plenitude"
    order: 3
  - id: "season.declinio"
    name: "Declínio"
    order: 4
  - id: "season.resguardo"
    name: "Resguardo"
    order: 5
year_rules:
  common_year: >-
    Dez períodos consecutivos de 36 dias totalizam 360 dias. Cada dia contém
    24 horas numeradas de 0 a 23, e cada semana contém seis dias em ciclo
    contínuo. Cada período equivale a seis semanas e cada ano a sessenta.
  exceptional_year: null
  day_count_method: >-
    O ordinal anual, iniciado em zero, é calculado por (ordem do período - 1)
    vezes 36 mais (dia - 1). Na era Pós-Marco, o índice absoluto é (ano - 1)
    vezes 360 mais o ordinal anual. Na era Antes do Marco, o índice absoluto é
    o negativo de (ano vezes 360 menos o ordinal anual). O índice zero é o
    primeiro dia do primeiro ano Pós-Marco.
date_format: >-
  sigla da era, hífen, ano com no mínimo quatro dígitos, hífen, ordem do
  período com dois dígitos, hífen e dia com dois dígitos
abbreviations:
  "era.antes_do_marco": "AM"
  "era.pos_marco": "PM"
  "month.abertura": "Abe"
  "month.semente": "Sem"
  "month.ascensao": "Asc"
  "month.fulgor": "Ful"
  "month.coroa": "Cor"
  "month.maturacao": "Mat"
  "month.virada": "Vir"
  "month.ocaso": "Oca"
  "month.bruma": "Bru"
  "month.guarda": "Gua"
  "weekday.alva": "Alv"
  "weekday.lume": "Lum"
  "weekday.brasa": "Bra"
  "weekday.nexo": "Nex"
  "weekday.veu": "Veu"
  "weekday.ancora": "Anc"
recurring_events: []
---

# Funcionamento

O Calendário do Marco usa somente unidades inteiras e ciclos fixos. Um dia tem
24 horas; uma semana tem seis dias; cada período tem 36 dias, ou seis semanas;
cada estação reúne dois períodos; e o ano tem dez períodos, cinco estações,
sessenta semanas e 360 dias. Não existe dia intercalar, ano excepcional ou
regra astronômica necessária ao cálculo.

O primeiro dia de cada período e de cada ano é Alva. Depois de Âncora, a semana
retorna a Alva. Depois do dia 36, começa o período seguinte; depois do dia 36 de
Guarda, começa o ano seguinte. Na era Antes do Marco, o avanço cronológico faz
os anos diminuírem até `AM-0001-10-36`; o dia seguinte é `PM-0001-01-01`.
Não existe ano zero.

Para comparação, duração, agendamento, checkpoints e replay, a data completa é
convertida no índice absoluto definido em `year_rules.day_count_method`. A hora
é acrescentada como um valor de 0 a 23; por isso, um instante pode ser ordenado
por `índice absoluto do dia × 24 + hora`. Avançar uma semana equivale sempre a
seis dias, e qualquer velocidade de simulação percorre a mesma sequência de
horas e dias.

Datas incompletas omitem somente componentes finais: `PM-0142` identifica um
ano e `PM-0142-03` identifica um período. Zero nunca representa componente
desconhecido. Para ordenar registros incompletos, cada data é tratada como o
intervalo fechado entre seu primeiro e seu último dia possíveis; a ordenação
usa primeiro o limite inferior, depois o limite superior e, se necessário, o
ID estável do registro como desempate. Duração exata exige duas datas completas;
uma data incompleta produz somente um intervalo de duração possível.

## Uso cultural

O calendário oferece uma base comum para registros civis, crônicas, idades,
rotinas, contratos, períodos administrativos, recorrências e história. As cinco
estações são divisões cronológicas estáveis para planejamento e economia
sazonal; elas não afirmam que todas as regiões futuras compartilham o mesmo
clima. Culturas, instituições e lugares poderão relacionar seus próprios usos a
essas divisões quando forem criados, sem alterar a contagem central.

## Observações editoriais

O marco é uma convenção de contagem, não um acontecimento histórico já criado.
A origem social de sua adoção, a data inicial do cenário, calendários locais,
festivais, feriados e correspondências com fenômenos astronômicos, mágicos ou
climáticos permanecem fora desta entidade. A lista `recurring_events` está vazia
porque nenhum evento recorrente canônico foi estabelecido nesta etapa.
