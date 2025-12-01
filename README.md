# 🦝 Raccoon Instance Segmentation (YOLOv8-Seg)

Projeto de **Segmentação por Instância** para detecção de guaxinins utilizando **YOLOv8-Seg**. 

O diferencial deste projeto é um pipeline de pré-processamento que **converte automaticamente datasets de Detecção (Caixas) para Segmentação (Polígonos)**.

## ✨ Funcionalidades
* **Auto-Labeling:** Script de ETL que transforma anotações de Bounding Box (`x,y,w,h`) em Máscaras de Segmentação dinamicamente.
* **Correção de Segurança:** Patch automático para o erro `weights_only=False` nas versões recentes do PyTorch.

## 📂 Estrutura do Dataset
O script organiza o dataset [ndb796/YOLO-Datasets](https://github.com/ndb796/YOLO-Datasets) automaticamente:

```text
/content/raccoon_segmentation/
├── images/     # Imagens originais
├── labels/     # Labels convertidos (Caixa -> Polígono)
└── data.yaml   # Configuração gerada pelo script

## 🚀 Como Executar

**Pré-requisitos:** Python 3.8+ e GPU (recomendado Google Colab).

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/SEU_USUARIO/Raccoon-Segmentation-YOLO.git](https://github.com/SEU_USUARIO/Raccoon-Segmentation-YOLO.git)
    ```

2.  **Instale a biblioteca:**
    ```
    pip install ultralytics
    ```

3.  **Execute:**
    Rode o Notebook (`.ipynb`). O script é totalmente automático: ele baixa os dados, converte os labels (caixa → polígono) e inicia o treino.

## 📈 Resultados
Após o treino, os arquivos são salvos em `runs/segment/train/`:

* **`weights/best.pt`**: Modelo final para inferência.
* **`val_batch0_pred.jpg`**: Exemplo visual das máscaras geradas.

---
*Projeto desenvolvido para a disciplina de Visão Computacional. Baseado na arquitetura Ultralytics YOLOv8.*
