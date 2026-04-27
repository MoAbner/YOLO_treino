# Detecção de Buracos com YOLO

Este projeto reúne um notebook para treinar um modelo YOLO voltado à detecção de buracos em vias. O fluxo cobre desde o download do dataset no Roboflow até a exportação do melhor modelo para `ONNX`, além de testes com imagem e vídeo.

## Arquivo principal

- `treino_buracos_yolo.ipynb`: notebook com todo o pipeline de treino, exportação e inferência.

## O que o notebook faz

1. Instala as bibliotecas necessárias.
2. Configura acesso ao projeto no Roboflow.
3. Baixa o dataset no formato YOLOv8.
4. Treina um modelo base `yolov8n.pt`.
5. Localiza o melhor peso gerado (`best.pt`).
6. Exporta o modelo treinado para `ONNX`.
7. Testa o modelo em imagem.
8. Testa o modelo em vídeo.

## Tecnologias utilizadas

- Python
- Jupyter Notebook
- Ultralytics YOLOv8
- Roboflow
- ONNX

## Requisitos

O notebook foi estruturado para um ambiente semelhante ao Google Colab, já que usa caminhos como `/content/...` e instalação via `%pip`.

Bibliotecas usadas no fluxo:

- `ultralytics`
- `roboflow`
- `onnx`
- `onnxsim`

## Como executar

1. Abra o arquivo `treino_buracos_yolo.ipynb` no Jupyter ou, preferencialmente, no Google Colab.
2. Instale as dependências executando a célula inicial.
3. Configure:
   - chave da API do Roboflow
   - workspace
   - nome do projeto
   - versão do dataset
4. Execute as células na ordem do notebook.
5. Ao final, confira os arquivos exportados e os resultados de predição.

## Saídas esperadas

Durante a execução, o notebook gera artefatos como:

- pesos do treinamento em `runs/buracos/weights/`
- melhor modelo em `best.pt`
- modelo exportado em `export/best.onnx`
- predições salvas para imagem e vídeo em subpastas de `runs/`

## Parâmetros de treino atuais

Pelos valores definidos no notebook:

- modelo base: `yolov8n.pt`
- épocas: `50`
- tamanho da imagem: `640`
- batch size: `16`
- nome da execução: `buracos`

## Observações

- O notebook depende de acesso ao Roboflow para baixar o dataset.
- É recomendável substituir credenciais fixas por variáveis de ambiente ou células sem valores sensíveis antes de compartilhar o projeto.
- Os caminhos de teste de imagem e vídeo podem precisar de ajuste conforme o ambiente de execução.

## Objetivo do projeto

O objetivo é treinar e validar um detector de buracos que possa ser posteriormente integrado a aplicações de análise de imagens, vídeos ou monitoramento de vias.
