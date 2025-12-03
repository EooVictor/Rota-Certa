# 🚛 Rota Certa - Sistema de Logística com IA

> **Trabalho de Machine Learning / Desenvolvimento Web**

## 📋 Sobre o Projeto

O **Rota Certa** é uma aplicação web interativa que simula o uso de Inteligência Artificial para otimização logística. O sistema calcula rotas de transporte de carga entre grandes capitais brasileiras, oferecendo estimativas de custo, tempo e risco baseadas em um modelo de aprendizado de máquina treinado com dados históricos.

A aplicação demonstra como algoritmos podem auxiliar na tomada de decisão, comparando rotas "Inteligentes" (sugeridas pela IA) contra rotas convencionais (mais rápidas ou mais curtas).

## ✨ Funcionalidades

  * **Simulação de Treinamento de Modelo:** Interface que demonstra o status de "treinamento" do algoritmo com base em um dataset histórico de viagens.
  * **Cálculo de Rotas:** Seleção de origem e destino entre capitais (SP, RJ, BH, Curitiba, Brasília, Salvador).
  * **Parâmetros de Carga:** Ajuste de peso e tipo de carga (Geral, Frigorífica, Perigosa, Granel), influenciando o custo final.
  * **Visualização de Mapa:** Um mapa do Brasil interativo (SVG) que desenha a rota animada entre as cidades selecionadas.
  * **Comparativo de Cenários:**
      * 🔵 **Rota Rápida:** Foco em tempo (Pedágios/Vias Expressas).
      * 🟡 **Rota Inteligente (ML):** Otimizada pelo algoritmo para custo-benefício.
      * 🔴 **Menor Distância:** Caminho mais curto, porém com maior risco/tempo.
  * **Dashboard de Dados:** Gráficos comparativos de custo e indicadores de economia gerada pela IA.

## 🛠️ Tecnologias Utilizadas

O projeto foi desenvolvido como uma **Single Page Application (SPA)** contida em um único arquivo HTML, utilizando bibliotecas modernas via CDN (Content Delivery Network):

  * **React.js (v18):** Para construção da interface e gerenciamento de estado.
  * **Tailwind CSS:** Para estilização responsiva e animações modernas.
  * **Babel Standalone:** Para compilar o código JSX/React diretamente no navegador.
  * **Recharts:** Para geração dos gráficos de barras comparativos.
  * **Lucide React:** Para ícones vetoriais.

## 🧠 Como funciona a "IA" (Lógica do Código)

O sistema implementa uma simulação de **Regressão Linear**:

1.  **Base de Dados:** Possui um array `HISTORICO_VIAGENS` com dados de viagens passadas (distância, peso, custo real).
2.  **Treinamento (`trainModel`):** Ao iniciar, o sistema percorre o histórico para calcular coeficientes médios:
      * `w_distancia`: Custo médio por Km.
      * `w_peso`: Custo médio por Kg.
3.  **Predição:** Ao calcular uma nova rota, ele aplica a fórmula:
    $$CustoBase = (Distância \times w\_distancia) + (Peso \times w\_peso) + Viés$$
4.  **Refinamento:** O resultado é ajustado por fatores multiplicadores dependendo do tipo de carga (ex: Carga Perigosa custa 1.8x mais).

## 🚀 Como Executar

Este projeto foi desenhado para ser extremamente simples de rodar, sem necessidade de instalação de dependências (Node.js, npm, etc).

1.  **Requisito:** Você precisa de uma conexão ativa com a internet (para carregar o React e o Tailwind via CDN).
2.  **Passo a passo:**
      * Baixe o arquivo `TrabalhoML.html`.
      * Abra o arquivo dando um clique duplo (ele abrirá no seu navegador padrão, como Chrome, Edge ou Firefox).
      * O sistema iniciará automaticamente.

## 📂 Estrutura de Arquivos

```
/
└── TrabalhoML.html  # Código completo (HTML + CSS + JS/React)
```

## 📸 Demonstração

O sistema apresenta um mapa interativo onde as rotas são traçadas dinamicamente usando SVG e curvas de Bézier quadráticas para simular o trajeto entre as coordenadas das cidades.

-----

*Desenvolvido para fins acadêmicos.*
