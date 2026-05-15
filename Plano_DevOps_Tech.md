# Plano de Implementação DevOps - Tech

Este documento detalha o plano estratégico para a adoção de práticas DevOps na empresa fictícia **Tech**, visando otimizar a entrega de software, reduzir falhas e promover uma cultura de colaboração.

---

## 1. Diagnóstico Cultural (C de CALMS)

O principal gargalo da Tech reside no **isolamento (silos)** entre as equipes de Desenvolvimento e Operações, refletido em processos manuais e falta de visibilidade.

* **Processo Atual:** O código é entregue como um "pacote" e o deploy é feito manualmente (2 dias de espera).
* **Pontos de Atrito:**
    * **Medo do Erro:** 20% de taxa de falha nos deploys gera desconfiança entre os times.
    * **Gargalo de Conhecimento:** Dependência única de um profissional para o sistema legado (Delphi).
    * **Testes Tardios:** Testes manuais ocorrem apenas após o deploy em produção, aumentando o impacto de bugs.

## 2. Automação (A de CALMS)

**Solução Proposta:** Implementação de uma esteira de **CI/CD (Integração e Entrega Contínua)** inicial para a Plataforma de E-commerce.

* **Plano de Implementação:**
    1.  **Padronização:** Utilizar Docker para garantir que o ambiente de Dev seja idêntico ao de Produção.
    2.  **Automação de Build:** Automatizar a geração de artefatos a cada commit.
    3.  **Pipeline de Testes:** Inserir testes unitários e de integração automáticos na esteira.
* **Mitigação de Resistência:** Realizar treinamentos práticos (Dojos) e envolver a equipe de Operações na criação dos scripts de automação, transformando "infraestrutura em código" (IaC).

## 3. Mensuração e Compartilhamento (M e S de CALMS)

### Métricas Relevantes (M)
* **Deployment Frequency:** Aumentar a frequência de deploys.
* **Change Failure Rate:** Reduzir a taxa de erro de 20% para menos de 5%.
* **MTTR (Mean Time To Recovery):** Reduzir o tempo médio de recuperação de 4 horas para minutos através de rollbacks automáticos.

### Compartilhamento (S)
* **Post-Mortems Sem Culpa:** Documentar falhas focando no processo, não na pessoa.
* **Documentação Viva:** Criar uma Wiki centralizada para o sistema legado e novos processos de automação.

## 4. As Três Maneiras

### Primeira Maneira: Acelerar o Fluxo
Simplificar o handoff entre Dev e Ops através da automação. O desenvolvedor não "envia um pacote", ele faz um "merge request" que, se aprovado e testado automaticamente, segue para o deploy.

### Segunda Maneira: Ampliar o Feedback
Implementar ferramentas de **Observabilidade** (como Prometheus e Grafana). Em vez de olhar logs manuais, o time terá dashboards em tempo real e alertas automáticos no Slack/Teams antes que o cliente reporte o problema.

### Terceira Maneira: Experimentar e Aprender
Criar janelas de tempo (ex: 10% do tempo semanal) para experimentação tecnológica. Erros no ambiente de staging serão celebrados como aprendizado para não ocorrerem em produção.

---
*Projeto desenvolvido como parte do desafio DevOps da Rocketseat.*
