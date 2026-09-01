# Dicionário e Tratamento de Dados 

Este documento detalha a estrutura da base de dados utilizada neste projeto após a extração via SQL, bem como os processos de limpeza e tratamento aplicados aos dados antes da importação para o Power BI.

## 1. Fonte dos Dados
* **Origem:** Extração direta do sistema de gestão via consulta Oracle SQL.
* **Formato de Saída:** Arquivo XLSX (`.xlsx`).
* **Período dos Dados:** Janeiro de 2025 a Agosto de 2026.

## 2. Dicionário de Dados
Abaixo estão detalhadas as colunas mantidas na base final (`base_limpa.xlsx`), utilizada no dashboard:

| Nome da Coluna | Tipo de Dado | Descrição |
| :--- | :--- | :--- |
| `ID_FERRAMENTA` | Alfanumérico | Código identificador único do equipamento no sistema (definido pelo usuário; sem padrão rígido entre setores). |
| `ID_MATERIAL` | Numérico | Código identificador do material/ferramenta. |
| `DESC_MATERIAL` | Texto | Nome/descrição do material. |
| `SITUACAO` | Texto | Status atual da ferramenta (ex.: EM USO, DEVOLVIDA). |
| `PERMANENTE` | Texto | Indica se o uso é permanente ou temporário (com previsão de devolução). |
| `DATA_inicio` | Data | Data de cadastro/criação do registro da ferramenta no sistema. |
| `ID_ALMOXARIFADO` | Numérico | Código identificador do almoxarifado/setor responsável. |
| `ALMOXARIFADO` | Texto | Nome/descrição do almoxarifado ou setor. |
| `ID_MARCA` | Numérico | Código identificador da marca da ferramenta. |
| `MARCA` | Texto | Nome/descrição da marca. |
| `ID_MODELO` | Numérico | Código identificador do modelo da ferramenta. |
| `MODELO` | Texto | Nome/descrição do modelo. |
| `ID_TIPO` | Numérico | Código identificador do tipo de ferramenta. |
| `TIPO` | Texto | Nome/descrição do tipo de ferramenta. |
| `DATA_entrega` | Data | Data da última entrega da ferramenta ao portador. |
| `DATA_prevista_devolucao` | Data | Data prevista para devolução da ferramenta. |
| `DATA_devolucao` | Data | Data da última devolução da ferramenta. |
| `ID_PORTADOR` | Numérico | Código identificador do portador (colaborador que recebeu a ferramenta). |
| `ID_EMISSOR` | Numérico | Código identificador do emissor (colaborador que entregou a ferramenta). |
| `OBSERVACAO` | Texto | Detalhes e observações vinculados à ferramenta. |
| `ID_UNIDADE` | Texto | Unidade de medida ou identificador da unidade da ferramenta. |

## 3. Log de Limpeza e Tratamento (Data Quality)
Para garantir a integridade das análises no Power BI, a base bruta passou pelas seguintes etapas de tratamento:

* **Tratamento de Valores Nulos:** 
  * Linhas sem o preenchimento de `ID_FERRAMENTA` e `ID_MATERIAL` e com menos de 4 caracteres foram removidas, pois indicavam falhas no registro de injeção de dados.
  * Todas as datas que apresentavam valores nulos foram preenchidas por `"NULL"`.
  * Valores ausentes na coluna `OBSERVACAO`, `ID_EMISSOR`, `EMISSOR` e `SETOR` foram preenchidos com `"Sem observação"`,`"Não informado"`,`"Não informado"` e `"Não informado"` para evitar inconsistências em visualizações do Power BI.
* **Desduplicação:**
  * Remoção de 45 linhas duplicadas decorrentes de falhas na extração do histórico de movimentação. A regra aplicada manteve apenas o registro com a data de atualização/movimentação mais recente.
* **Padronização e Formatação:**
  * As colunas de texto (como `MARCA`, `MODELO` e `TIPO`) tiveram seus valores convertidos para letras maiúsculas e os espaços sobressalentes removidos (função *Trim*).
  * Padronização dos tipos de dados de data (`DATA_inicio`, `DATA_entrega`, `DATA_prevista_devolucao` e `DATA_devolucao`) para o formato padrão do Power BI (`DD/MM/AAAA`).

## 4. Estrutura de Arquivos
* `dados_brutos_amostra.csv`: Amostra dos dados originais (com dados sensíveis anonimizados).
* `base_limpa.xlsx`: Arquivo final tratado e conectado ao Power BI.