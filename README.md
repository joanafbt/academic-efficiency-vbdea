# 📊 Análise de Eficiência Académica com Value-Based DEA

## Objetivo
Avaliar a eficiência académica de estudantes através do método
Value-Based Data Envelopment Analysis (VBDEA), incorporando preferências
do decisor em funções de valor não-lineares. O estudo identifica quais os
estudantes que obtêm melhores resultados dado o conjunto de recursos
utilizados, e quantifica as melhorias necessárias para atingir a fronteira
eficiente.

## Ferramentas e tecnologias
- Python (pandas) — preparação e transformação dos dados
- Aplicação web VBDEA (migs.shinyapps.io) — análise de eficiência
- Dataset: Student Performance Factors (Kaggle) — 200 DMUs selecionadas

## Variáveis do modelo
| Papel   | Variável           | Descrição                        |
|---------|--------------------|----------------------------------|
| Input   | Hours_Studied      | Horas de estudo semanais         |
| Input   | Attendance         | Taxa de presença nas aulas       |
| Input   | Tutoring_Sessions  | Sessões de tutoria               |
| Input   | Sleep_Hours        | Horas de sono por noite          |
| Output  | Exam_Score         | Nota no exame                    |

## Metodologia
- Modelo BCC com retornos variáveis à escala
- Funções de valor lineares por partes, normalizadas em [0,1]
- Regra Min-Max Regret para cálculo dos scores de eficiência
- Dois cenários comparados: sem e com restrições nos pesos

## Resultados

### Cenário 1 — Sem restrições nos pesos
- 60,5% dos estudantes são eficientes ou super-eficientes
- Estudante mais super-eficiente: DMU95 (d* = -0,457) — nota 100 com
  recursos moderados
- Critérios com maior potencial de melhoria: sono (slack 0,330) e
  tutoria (slack 0,199)
- Existem múltiplos caminhos para a eficiência académica

### Cenário 2 — Com restrições nos pesos (sono como critério prioritário)
- Apenas 1 estudante super-eficiente: DMU114 (d* = -0,023)
- 116 estudantes perderam o estatuto de eficientes face ao Cenário 1
- Critério com maior ineficiência: presença (slack médio 0,436)

## Principais insights
- Tutoria e sono podem ser substitutos parciais do estudo individual
- Dormir adequadamente (7-9h) é condição quase necessária para
  eficiência quando valorizado como critério prioritário
- Existem perfis distintos de eficiência: esforço elevado vs. sono +
  tutoria como estratégia alternativa

## Aplicação prática
- Apoio a decisores pedagógicos na identificação de estudantes em risco
- Orientação de intervenções: programas de tutoria e sensibilização
  para hábitos de sono
- Base para análise de sensibilidade com diferentes preferências do
  decisor

## Autores
Projeto desenvolvido em grupo no âmbito do Mestrado em Análise de Dados.
- Joana Tomé
- Gonçalo Conceição
