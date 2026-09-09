# tratamento_seama

Unificação e normalização das planilhas de desempenho do **SEAMA** — Sistema de Avaliação da Aprendizagem do Maranhão. Trabalho feito para consolidar avaliações que chegam fragmentadas em dezenas de arquivos.

## O problema

Os resultados do SEAMA são exportados em uma planilha por escola, por turma e por município, espalhadas em pastas separadas por recorte (`HABILIDADE_DESEMPENHO_ESCOLA_2_A_9`, `HABILIDADE_DESEMPENHO_TURMA_1_A_9`, e assim por diante). Além do volume, os nomes das escolas não são padronizados entre arquivos — a mesma escola aparece como `ESCOLA MUNICIPAL DE TEMPO INTEGRAL NEGRO COSME` e `ESCOLA MUNICIPAL TEMPO INTEGRAL NEGRO COSME`, o que quebra qualquer agregação por instituição.

## O que o notebook faz

`unificar_bases.ipynb`:

1. varre cada pasta de recorte e concatena todos os `.xlsx` num único dataframe
2. aplica um dicionário de substituições para reconciliar as variações de nome de escola
3. prefixa as colunas por origem (`Escola_`, `Municipio_`) para permitir o join entre recortes
4. exporta as bases unificadas

## Dados

As planilhas de origem não estão versionadas — só o código de tratamento.

## Licença

[MIT](LICENSE)
