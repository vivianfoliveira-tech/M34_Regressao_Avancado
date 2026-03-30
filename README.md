# Relatório de Projeto: Regressão Avançada para Precificação de Aluguéis

* Visão Geral
Este projeto consistiu em um estudo exploratório para prever o Valor do Aluguel com base nas características físicas dos imóveis. O objetivo central foi testar diferentes níveis de complexidade matemática — desde modelos polinomiais simples até técnicas de regularização (Ridge e Lasso) — para identificar o equilíbrio ideal entre precisão e estabilidade.

* Metodologia e Dados
Trabalhamos com o dataset ALUGUEL_MOD12, focando em variáveis como Metragem, Quartos, Banheiros, Suítes e Vagas.

Restrição: Conforme solicitado, o valor do condomínio foi excluído dos preditores.

Processamento: Realizamos a limpeza de dados (NAs e coerção numérica), escalonamento das variáveis e aplicamos transformações polinomiais de graus 2 e 4.

Validação: Utilizamos K-Fold Cross-Validation (k=5) para garantir que as métricas de performance (R², RMSE e MAE) fossem consistentes e não fruto de meras coincidências no treino.

* Principais Descobertas
Limite da Complexidade: O aumento do grau polinomial para 4 (mesmo com regularização Ridge/Lasso) não trouxe ganhos reais. Com risco de overfitting.

Força do Multivariado: A estratégia mais eficaz não foi complicar o cálculo, mas sim enriquecer os dados. O modelo multivariado de grau 2 superou todos os outros cenários na validação cruzada.

Desempenho Base: No cenário univariado (apenas metragem), o modelo explicou cerca de 57% da variação dos preços (R² ≈ 0.57). Esse número sobe significativamente ao incluirmos as demais características do imóvel.
