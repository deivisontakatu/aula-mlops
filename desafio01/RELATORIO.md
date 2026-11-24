# Desafio 1: relatório

**Aluno(a):** Deivison Shindi Takatu

## 1. Versões dos dados

Rode o comando abaixo e complete a tabela com os 8 primeiros caracteres de cada md5:

```bash
for tag in dados-v1 dados-v2 dados-v3; do
  echo "$tag $(git show $tag:data/raw/bike.csv.dvc | awk '/md5/{print $3}')"
done
```

| Tag | md5 (8 primeiros caracteres) | Período |
|---|---|---|
| `dados-v1` | `fc7d423a` | 01/01/2011 a 31/12/2011 |
| `dados-v2` | **Preencher após consultar Git** | 01/01/2011 a 30/06/2012 |
| `dados-v3` | **Preencher após executar dvc add** | 01/01/2011 a 31/12/2012 |

## 2. Comparação no mesmo teste

Copie os números de `reports/comparacao.json` após executar o pipeline.

**Período do teste:** **Preencher após execução**

| Alias | Versão | RMSE | MAE | R² |
|---|---:|---:|---:|---:|
| `@champion` | — | — | — | — |
| `@challenger` | — | — | — | — |

## 3. Decisão

**Promovido ou rejeitado?** A definir após comparar os resultados reais.

**Justificativa (2 a 3 frases):** A decisão deve considerar a comparação dos dois modelos no mesmo conjunto de teste. O Challenger somente deve substituir o Champion se apresentar RMSE estritamente menor; caso contrário, o Champion atual deve ser mantido.

## 4. O que cada ferramenta fez nesse projeto?

**Pergunta 01:**
Com suas palavras, quais os dois usos do DVC nesse projeto?

O DVC foi utilizado para versionar os dados, permitindo identificar e recuperar diferentes versões do conjunto de dados. Também foi utilizado para definir e executar o pipeline de preparação, separação, treinamento, avaliação, geração de gráfico e comparação dos modelos, garantindo a reprodutibilidade das etapas.

**Pergunta 02:**
Com suas palavras, para que serve o MLflow nesse projeto?

O MLflow registra e organiza os experimentos de treinamento, armazenando parâmetros, métricas, informações e artefatos dos modelos. Seu Model Registry mantém as versões dos modelos e permite utilizar aliases como Champion e Challenger para controlar qual versão está aprovada para uso.
