# Desafio 1: relatório

**Aluno(a):** Deivison Shindi Takatu

## 1. Versões dos dados

O histórico Git disponível no repositório original e no fork contém apenas a tag `dados-v3`. As tags `dados-v1` e `dados-v2` não foram localizadas como referências Git acessíveis; por isso, seus hashes não podem ser confirmados por meio do comando proposto.

| Tag | md5 (8 primeiros caracteres) | Período | Situação |
|---|---|---|---|
| `dados-v1` | `fc7d423a` | 01/01/2011 a 31/12/2011 | Hash indicado no modelo do relatório; tag não localizada no histórico acessível |
| `dados-v2` | Não disponível | 01/01/2011 a 30/06/2012 | Tag não localizada no histórico acessível |
| `dados-v3` | `7747b2ef` | 01/01/2011 a 31/12/2012 | Confirmada no repositório |

A versão `dados-v3` está registrada no commit `ab489681e18ef330ccbf21612fa6842c8831bb10`, por meio do arquivo `data/raw/bike.csv.dvc`.

## 2. Comparação no mesmo teste

**Período do teste:** 04/12/2012 a 31/12/2012 (670 linhas).

Na execução realizada, os aliases `@champion` e `@challenger` apontaram para a mesma versão registrada do modelo (versão 1). Portanto, os resultados abaixo comprovam a execução do fluxo de comparação, mas não representam uma disputa entre duas versões distintas.

| Alias | Versão | RMSE | MAE | R² |
|---|---:|---:|---:|---:|
| `@champion` | 1 | 62,894 | 41,506 | 0,848 |
| `@challenger` | 1 | 62,894 | 41,506 | 0,848 |

**Observação:** é necessário treinar e registrar uma segunda versão para realizar uma comparação efetiva entre Champion e Challenger.

## 3. Decisão

**Promovido ou rejeitado?** Não houve promoção.

**Justificativa (2 a 3 frases):** Na execução registrada, Champion e Challenger apontaram para a mesma versão (1), apresentando métricas idênticas. Assim, não há evidência de que uma nova versão tenha superado a atual; a comparação foi apenas uma validação do funcionamento do pipeline, e não um experimento válido de promoção entre modelos diferentes.

## 4. O que cada ferramenta fez nesse projeto?

**Pergunta 01:**  
Com suas palavras, quais os dois usos do DVC nesse projeto?

O DVC foi utilizado para versionar os dados, permitindo identificar e recuperar diferentes versões do conjunto de dados. Também foi utilizado para definir e executar o pipeline de preparação, separação, treinamento, avaliação, geração de gráfico e comparação dos modelos, garantindo a reprodutibilidade das etapas.

**Pergunta 02:**  
Com suas palavras, para que serve o MLflow nesse projeto?

O MLflow registra e organiza os experimentos de treinamento, armazenando parâmetros, métricas, informações e artefatos dos modelos. Seu Model Registry mantém as versões dos modelos e permite utilizar aliases como Champion e Challenger para controlar qual versão está aprovada para uso.
