Fundamentos de Processamento de Imagens

Notebook desenvolvido para a atividade **"Fundamentos de Processamento de Imagens"** da disciplina de Visão Computacional. O projeto explora, de forma prática, como escolhas de representação e armazenamento influenciam a informação visual disponível em um pequeno conjunto de imagens.

> **Escopo:** este repositório apresenta análise e transformações de imagens. Ele **não treina nem avalia um modelo de classificação**.

## Objetivo

Construir e analisar um mini dataset próprio com duas classes de objetos do cotidiano — **notebook** e **carregador** — aplicando transformações fundamentais de processamento digital de imagens:

- variação de resolução;
- conversão entre espaços de cor RGB, HSV e escala de cinza;
- quantização em níveis de cinza;
- comparação entre os formatos JPEG e PNG.

## Dataset

O dataset foi registrado com a câmera traseira de um **Motorola Moto G24** e possui 10 imagens:

| Classe | Objeto | Quantidade |
| --- | --- | ---: |
| `classe_A` | Notebook | 5 |
| `classe_B` | Carregador | 5 |

As imagens incluem diferentes condições de iluminação, distâncias e ângulos. O notebook registra que algumas fotos têm leve desfoque de movimento, condizente com a captura manual.

## Tecnologias utilizadas

- Python
- OpenCV (`cv2`)
- NumPy
- Matplotlib
- Pillow (PIL)
- Jupyter Notebook / Google Colab

## O que o notebook faz

O arquivo `atividade_visao_computacional_v2_corrigido_(1).ipynb`:

1. descompacta o dataset e lista suas pastas;
2. exibe as 10 imagens organizadas pelas duas classes;
3. usa uma imagem de cada classe como exemplo (`img001` e `img006`);
4. compara as resoluções original, 50% e 20%;
5. apresenta RGB, os canais H/S/V do HSV e escala de cinza;
6. gera versões quantizadas em 256, 64, 32 e 2 níveis;
7. salva as imagens de exemplo como JPEG (qualidade 70) e PNG e compara seus tamanhos;
8. cria `mini_dataset_final.zip` com o dataset e as transformações produzidas.

## Resultados e observações

As conclusões registradas no notebook são observações visuais sobre as imagens utilizadas, não métricas de desempenho de um modelo:

- reduzir a resolução para 20% preserva a forma geral dos objetos, mas compromete detalhes como texto, logotipos e ícones;
- como as classes são predominantemente escuras e se distinguem principalmente por forma e textura, a escala de cinza preserva a informação visual relevante para essa análise;
- a quantização em 64 níveis mantém aparência semelhante à de 256 níveis, enquanto 2 níveis remove boa parte da textura;
- nos exemplos testados, JPEG com qualidade 70 gerou arquivos cerca de 10 vezes menores que PNG, sem diferença visual perceptível relatada no notebook.

## Como executar

### Opção 1 — Google Colab

1. Abra o notebook `atividade_visao_computacional_v2_corrigido_(1).ipynb` no Google Colab.
2. Faça upload do arquivo `mini_dataset_visao_computacional (2).zip` para a área de arquivos do Colab.
3. Renomeie o arquivo enviado para `mini_dataset_visao_computacional.zip`.
   - O código do notebook procura exatamente esse nome, enquanto o arquivo versionado no repositório possui o sufixo ` (2)`.
4. Execute as células em ordem, começando pelo setup.
5. Ao final, o notebook gera `mini_dataset_final.zip` no ambiente de execução.

### Opção 2 — Ambiente local com Jupyter

Instale as dependências:

```bash
pip install opencv-python numpy matplotlib pillow jupyter
```

Em seguida:

1. Mantenha o notebook e o arquivo ZIP na mesma pasta.
2. Renomeie `mini_dataset_visao_computacional (2).zip` para `mini_dataset_visao_computacional.zip`.
3. Inicie o Jupyter Notebook:

```bash
jupyter notebook
```

4. Abra o notebook e execute as células sequencialmente.

## Estrutura do projeto

```text
.
├── atividade_visao_computacional_v2_corrigido_(1).ipynb
└── mini_dataset_visao_computacional (2).zip
    ├── dataset/
    │   ├── classe_A/  # 5 imagens de notebook
    │   └── classe_B/  # 5 imagens de carregador
    └── transformacoes/
        ├── versões de resolução
        ├── imagens RGB, HSV e em escala de cinza
        ├── imagens quantizadas
        └── comparações JPEG e PNG
```

## Possíveis evoluções

Como continuidade, o projeto pode receber uma etapa de divisão de dados, treinamento e avaliação de um classificador. Essa etapa não faz parte da implementação atual.

---

Projeto acadêmico de Visão Computacional — análise de transformações de imagens em um mini dataset próprio.
