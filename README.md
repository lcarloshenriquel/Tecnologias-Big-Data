# Projeto de Limpeza e Transformação de Dados - pico_web.csv

## 📌 Objetivo
Este trabalho teve como objetivo realizar a leitura, análise inicial e tratamento de inconsistências no conjunto de dados `pico_web.csv`, com foco na coluna **Date**. O processo incluiu substituição de valores nulos, correção de formatos inválidos e remoção de registros incompletos.

---

## 🛠️ Etapas Realizadas

1. **Leitura do arquivo CSV**
   - Utilização do `pandas.read_csv()` com separador `;`.
   - Verificação da estrutura do dataset com `df.info()` e inspeção das primeiras e últimas linhas.

2. **Criação de cópia do dataset**
   - Foi criada a variável `df_copia` para preservar os dados originais e aplicar transformações apenas na cópia.

3. **Tratamento da coluna `Calories`**
   - Substituição de valores nulos por `0`.

4. **Tratamento da coluna `Date`**
   - Substituição inicial de valores nulos por `"1900/01/01"`.
   - Tentativa de conversão para `datetime` com formato `%Y/%m/%d`, resultando em erro (passo intencional para demonstrar inconsistência).
   - Substituição de `"1900/01/01"` por `NaN` e reconversão para `datetime`.
   - Identificação de outro erro causado pelo valor `"20201226"`.
   - Correção específica desse valor utilizando `replace` + `to_datetime` com formato `%Y%m%d`.
   - Reconversão final da coluna inteira para `datetime64`.

5. **Remoção de registros nulos**
   - Utilização de `dropna()` para eliminar linhas com valores ausentes.
   - Apenas a linha 22 foi removida, pois continha `NaT` na coluna `Date`.

---

## ✅ Resultado Final
- Dataset limpo e pronto para análises temporais.
- Coluna **Date** convertida corretamente para o tipo `datetime64`.
- Nenhum registro com valores nulos remanescentes.

---

## 📂 Estrutura do Código
O trabalho foi desenvolvido em células sequenciais no Jupyter Notebook, utilizando:
- `pandas` para manipulação dos dados.
- `numpy` para tratamento de valores nulos.
- `IPython.display` para melhor visualização dos resultados.

---

## 🚀 Próximos Passos
- Explorar análises temporais (ex.: filtragem por intervalos de datas).
- Criar visualizações gráficas para identificar padrões nos dados.
- Exportar o dataset final limpo para um novo arquivo CSV (`pico_web_limpo.csv`).

