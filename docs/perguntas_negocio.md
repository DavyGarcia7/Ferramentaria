# Perguntas de Negócio — Análise de Ferramentaria

Este documento reúne as perguntas direcionadoras para a análise de dados da ferramentaria, organizadas por objetivo estratégico. O foco principal é identificar falhas no fluxo de empréstimos, ociosidade de ativos e perdas/extravios não notificados.

---

## 1. Ociosidade e Uso Efetivo
*Objetivo: Identificar se o acervo de ferramentas está sendo subutilizado ou concentrado indevidamente.*

* **Quais ferramentas não registraram nenhum empréstimo nos últimos 3, 6 e 12 meses?**
* **Qual é o valor financeiro total imobilizado nessas ferramentas ociosas?**
* **Existem ferramentas com alta taxa de retenção por um mesmo colaborador/setor sem movimentação contínua?**
* **Qual é o tempo médio que uma ferramenta permanece emprestada comparado ao tempo estimado da Ordem de Serviço (OS)?**

---

## 2. Falhas no Fluxo de Empréstimo e Retenção
*Objetivo: Mapear gargalos operacionais e descumprimento de prazos de devolução.*

* **Qual é o percentual atual de empréstimos em atraso em relação ao total de itens em posse de colaboradores?**
* **Quais colaboradores ou setores concentram o maior número de pendências de devolução?**
* **Existem ferramentas registradas como "emprestadas" há mais de 30, 60 ou 90 dias?**
* **Quantos empréstimos constam em aberto para colaboradores que já foram desligados ou mudaram de setor?**

---

## 3. Perdas, Extravios e Divergências de Estoque
*Objetivo: Encontrar perdas silenciosas e furos no inventário físico.*

* **Qual é a taxa de divergência entre o saldo físico auditado e o saldo registrado no sistema?**
* **Existem itens cadastrados como "disponíveis" que não foram localizados no inventário físico?**
* **Quais categorias de ferramentas possuem o maior índice de baixa por avaria ou extravio?**
* **Qual é o custo financeiro acumulado decorrente de perdas e reposição de ferramentas por setor?**

---

## 4. Matriz de Impacto e KPIs

| Indicador (KPI) | Pergunta Mapeada | Ação Operacional |
| :--- | :--- | :--- |
| **Taxa de Ociosidade** | Quais itens estão sem uso há 6+ meses? | Remanejamento ou leilão de ativos. |
| **Índice de Inadimplência** | Quem retém itens além do prazo estipulado? | Bloqueio automático de novas retiradas. |
| **Acuracidade de Estoque** | Qual é o tamanho do furo no inventário? | Auditoria focada nas categorias divergentes. |