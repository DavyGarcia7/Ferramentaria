# Relatório de Insights e Diagnóstico — Ferramentaria

Este documento consolida os resultados obtidos a partir das análises de dados, destacando os gargalos identificados no fluxo de empréstimos, furos de estoque e as recomendações práticas para mitigação de perdas.

---

## 1. Resumo Executivo
*Breve síntese do estado atual da ferramentaria com base na análise dos dados.*

* **Status Geral do Acervo:** [Ex: 15% do inventário está ocioso / R$ 50.000 em ativos parados]
* **Principais Gargalos:** [Ex: Alto volume de retenção sem baixa por mais de 60 dias no setor X]
* **Nível de Acuracidade do Estoque:** [Ex: Divergência de 8% entre o sistema e o estoque físico]

---

## 2. Diagnóstico de Uso e Ociosidade
*Resultados das consultas sobre a utilização das ferramentas.*

* **Ferramentas Inativas:** [Listar categorias/itens sem movimentação nos últimos 6 a 12 meses]
* **Impacto Financeiro:** Valor total imobilizado em ferramentas sem uso registrado.
* **Superalocação:** [Listar colaboradores ou setores com acúmulo desproporcional de itens]

---

## 3. Gargalos em Empréstimos e Devoluções
*Análise do cumprimento dos prazos e retenção indevida.*

* **Taxa de Atraso Atual:** [Ex: X% dos empréstimos ativos estão com prazo vencido]
* **Setores com Maior Inadimplência:** [Identificação dos setores/equipes mais críticos]
* **Casos Críticos (Empréstimos Antigos):** Ferramentas não devolvidas há mais de 90 dias ou vinculadas a desligamentos.

---

## 4. Perdas e Divergências Identificadas (Furos de Estoque)
*Diferenças entre os registros do sistema e a realidade física.*

* **Furos de Inventário:** Itens que constam como "disponíveis" no sistema, mas não estão na prateleira.
* **Baixas Não Notificadas:** Estimativa de ferramentas danificadas/descartadas sem registro oficial.
* **Custo Total de Perdas:** Prejuízo acumulado com reposição de itens extraviados.

---

## 5. Plano de Ação e Recomendações

| Problema Identificado | Causa Raiz | Ação Corretiva Propagada |
| :--- | :--- | :--- |
| **Ferramentas paradas há 60+ dias** | Falta de limite de tempo por OS | Estabelecer devolução obrigatória semanal/mensal |
| **Divergência sistema x físico** | Empréstimos informais sem registro | Trava de retirada sem check-in no sistema |
| **Alta perda de itens portáteis** | Falta de responsabilização | Controle individualizado via código de barras/RFID |

---

## 6. Próximos Passos
* [ ] Apresentar diagnóstico para a gestão operacional.
* [ ] Automatizar alertas de atraso via consulta SQL/Dashboard.
* [ ] Programar próxima auditoria física de inventário.