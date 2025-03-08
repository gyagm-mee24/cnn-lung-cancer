# Classificação de Câncer de Pulmão com VGG16 e ResNet152V2

## Descrição do Projeto

Este projeto tem como objetivo a **classificação de imagens de tomografia computadorizada (CT) para a detecção do câncer de pulmão**, utilizando as arquiteturas **VGG16** e **ResNet152V2**. O experimento é baseado no conjunto de dados **IQ-OTH/NCCD - Lung Cancer Dataset**, que contém imagens organizadas em três classes: **normal, benigno e maligno**. Para mitigar o desbalanceamento utilizamos um dataset derivado, onde foram aplicadas **técnicas de aumento de dados (augmentation)**, incluindo **flip, rotação, ajuste de contraste e equalização de histograma**.

O treinamento dos modelos foi realizado por **50 épocas**, utilizando uma **taxa de aprendizado de 0.0001** e validação cruzada para avaliar o desempenho dos classificadores.

---

## Dataset

O conjunto de dados utilizado neste projeto é o **IQ-OTH/NCCD - Lung Cancer Dataset** disponível no Kaggle:

- Link: [IQ-OTH/NCCD - Lung Cancer Dataset Augmented](https://www.kaggle.com/datasets/subhajeetdas/iq-othnccd-lung-cancer-dataset-augmented)
- Contém **1.190 imagens de tomografia computadorizada**
- Classes:
  - **Normal**: 55 casos
  - **Benigno**: 15 casos
  - **Maligno**: 40 casos

Para baixar automaticamente o dataset, utilizamos a biblioteca **kagglehub** para facilitar a integração com a API do Kaggle.

---

## Instalação das Dependências

Antes de rodar o experimento, instale as bibliotecas necessárias executando o seguinte comando:

```bash
pip install numpy pandas plotly matplotlib opencv-python tensorflow kagglehub
```

Caso utilize o **Jupyter Notebook**, verifique se todas as dependências estão corretamente instaladas para evitar erros durante a execução.

---

## Como Executar o Experimento

1. **Baixar o dataset**

   - O dataset será automaticamente baixado e salvo localmente utilizando **kagglehub**.
   - Alternativamente, o caminho pode ser configurado manualmente.

2. **Carregar e organizar as imagens**

   - As imagens são organizadas em três classes: **Normal, Benigno e Maligno**.
   - As imagens são carregadas e armazenadas em um dataframe para facilitar a manipulação e visualização.

3. **Pré-processamento e Augmentation**

   - As imagens passam por um processo de normalização.

4. **Treinamento dos Modelos**

   - O experimento utiliza **VGG16 e ResNet152V2**.
   - Ambas as redes são ajustadas para realizar classificação em três classes.
   - O treinamento é realizado por **50 épocas**, utilizando **Adam optimizer** e validação cruzada.

5. **Avaliação dos Modelos**
   - O desempenho é avaliado utilizando **acurácia e F1-score**.
   - Os resultados finais são apresentados em gráficos de **curva de loss** e **acurácia**.

---

## Resultados

Os modelos apresentaram os seguintes desempenhos:

- **ResNet152V2**: 96,68% de acurácia | 96,67% de F1-score
- **VGG16**: 89,89% de acurácia | 89,83% de F1-score

Esses resultados demonstram a eficácia da **ResNet152V2** na extração de padrões complexos, enquanto a **VGG16** apresenta uma alternativa computacionalmente mais leve.

---

## Sugestões para Trabalhos Futuros

Para melhorias e extensões do projeto, algumas abordagens podem ser exploradas:

- Utilização de **arquiteturas mais profundas**, como **Inception-v4 ou EfficientNet**.
- Implementação de uma abordagem **híbrida**, combinando **CNNs para extração de características e SVM para classificação final**.

---

## Contato

Caso tenha dúvidas ou sugestões, entre em contato!
