# Credit Risk Analysis — Project Portfolio

**Resumo curto:** análise exploratória e dashboard sobre risco de incumprimento usando `credit_risk_dataset` (Kaggle). Objetivo: identificar perfis de cliente com maior probabilidade de incumprimento e criar visualizações acionáveis.

## Pergunta central
Que perfil de cliente tem maior probabilidade de entrar em incumprimento?

## Questões secundárias
- A faixa etária tem influência?
- O nível de rendimento tem impacto?
- A finalidade do empréstimo altera o risco?
- A situação de habitação tem relação?
- O rácio empréstimo / rendimento é um fator?

## Dados
- Fonte: Kaggle — `credit_risk_dataset.csv` (transformado).  
- Registos finais: **22 296**.  
- Campos relevantes utilizados: `person_age`, `person_income`, `person_home_ownership`, `loan_amnt`, `loan_int_rate`, `loan_status`, `loan_intent_pt`, `loan_percent_income`, etc.

## Limpeza e tratamento
- Verificações de qualidade com Power Query: column profiling (valores nulos, outliers).  
- Regras aplicadas (exemplos):
  - Filtrar `person_age >= 100`.
  - Corrigir tipos (p. ex. `loan_int_rate` como decimal).
  - Substituir `null` e remover registos incompletos em colunas críticas.
  - Remover duplicados.
  - Criar colunas derivadas: `age_group`, `income_tier`, `loan_income_ratio`.

## Métodos / Ferramentas
- Power Query (Excel) — limpeza e preparação.  
- Excel (tabelas dinâmicas, fórmulas `SE.S()`, `PROCX()` e dashboards).  
- Visualização: gráficos dinâmicos no Excel com storytelling.

## Principais conclusões
- Taxa global de incumprimento: **23,11%**.  
- Rácio empréstimo/rendimento elevado (>33%) está fortemente associado a incumprimento (**73,37%**).  
- Clientes em arrendamento e com rendimentos baixos apresentam maior risco (ex.: RENT 32%, income_tier=Baixo 27,2%).  
- Finalidades com maior risco: Consolidação de Dívida (28,7%), Melhoria de Habitação (27,4%), Saúde (27,3%).

## Limitações
- Dataset público (Kaggle) — Muitos dos valores não representam a realidade portuguesa.
- Algumas categorias têm pequena amostra (e.g., Sénior).  
- Decisões de limpeza que afetam amostra descritas no `process_log.docx`.

## Próximos passos / melhorias
- Novo projeto integrando SQL e Excel.
- Migrar análise para Power BI.

## Ficheiros no repositório
- `credit_risk_dataset.csv` (original) — disponível no Kaggle  
- `credit_risk.xlsx` (versão transformada + dashboard)  
- `process_log.docx` (documentação do processo)  
- `README.md` (este ficheiro)

## Como reproduzir
1. Abrir `credit_risk.xlsx` para ver a transformação aplicada e o dashboard final.
