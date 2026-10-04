# Projeto 2 - Segmentação de imagens por cor (RGB → HSV)

Projeto da disciplina de **Computação Visual** (Prof. André Kishimoto),
Ciência da Computação, Faculdade de Computação e Informática, Universidade
Presbiteriana Mackenzie, 2026.2.

## Grupo

| Nome completo | RA |
|---|---|
| João Guilherme Messias de Oliveira Santos | 10426110 |
| Luis Felipe Cunha | 10419514 |

## O que é o projeto

**Opção 2 do enunciado: tutorial de teoria e prática**, feito em um notebook
Jupyter.

Tema: segmentação de imagens por cor. Convertemos a imagem de RGB para HSV,
implementando as fórmulas nós mesmos, e isolamos objetos pela faixa de matiz
(H), com limites mínimos de saturação (S) e valor (V). Em seguida aplicamos a
mesma tentativa de isolamento diretamente em RGB, para mostrar por que o HSV
é mais robusto a variações de iluminação.

## Estado atual

**Entrega 2 em andamento** (prazo: 20/10/2026, 23:59).

- [x] Entrega 1: definição da opção e do tema ([PDF](entrega1/entrega1.pdf))
- [x] Estrutura do repositório e do notebook
- [ ] Teoria e prática do modelo RGB
- [ ] Conversão RGB → HSV implementada e validada
- [ ] Segmentação por faixa de matiz
- [ ] Comparação RGB × HSV
- [ ] Limitações, conclusão e referências
- [ ] Vídeo-pitch (até 5 min)

Documentos:

- [Entrega 1 (definição do tema)](entrega1/entrega1.pdf)
- [Tutorial (notebook)](tutorial_segmentacao_cor.ipynb)

## Como executar

Requisitos: Python 3.10 ou mais recente.

```
pip install -r requirements.txt
jupyter notebook tutorial_segmentacao_cor.ipynb
```

O OpenCV aparece no `requirements.txt` só para conferir o resultado da nossa
conversão. A conversão e a segmentação usadas no tutorial são implementadas
no próprio notebook com NumPy.

## Ambiente de desenvolvimento

| Item | Versão |
|---|---|
| Sistema operacional | Windows 11 Pro 10.0.26200 |
| Python | 3.13.3 |
| NumPy | 2.2.6 |
| Matplotlib | 3.10.3 |
| Pillow | 11.2.1 |
| OpenCV (somente validação) | 4.13.0 |
| Jupyter Notebook | 7.6.2 |
