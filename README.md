# Projeto 2 - Segmentação de imagens por cor (RGB → HSV)

Projeto da disciplina Computação Visual (Prof. André Kishimoto), do curso de
Ciência da Computação da Faculdade de Computação e Informática, Universidade
Presbiteriana Mackenzie, 2026.2.

## Grupo

| Nome completo | RA |
|---|---|
| João Guilherme Messias de Oliveira Santos | 10426110 |
| Luis Felipe Cunha | 10419514 |

## Sobre o projeto

Escolhemos a Opção 2 do enunciado, um tutorial de teoria e prática, feito em
notebook Jupyter.

O tema é segmentação de imagens por cor. O notebook converte a imagem de RGB
para HSV com as fórmulas implementadas no próprio código, sem funções prontas,
e isola os objetos por uma faixa de matiz (H), com limites mínimos de
saturação (S) e valor (V). Depois tentamos fazer a mesma separação direto em
RGB, para comparar como cada modelo se comporta quando a iluminação muda.

## Estado da entrega

Entrega 2 concluída em 20/10/2026.

- [x] Entrega 1: definição da opção e do tema ([PDF](entrega1/entrega1.pdf))
- [x] Estrutura do repositório e do notebook
- [x] Motivação com imagem sintética de teste (com gabarito)
- [x] Teoria e prática do modelo RGB
- [x] Conversão RGB → HSV implementada e validada contra `colorsys` e OpenCV,
      em cerca de 250 mil cores
- [x] Segmentação por faixa de matiz (imagem sintética e duas fotos)
- [x] Comparação RGB × HSV (imagem sintética, duas fotos e experimento de
      iluminação)
- [x] Limitações, conclusão, e referências
- [x] Reescrita dos textos do notebook
- [x] Revisão final dos textos pelo grupo
- [x] Vídeo-pitch ([YouTube](https://www.youtube.com/watch?v=3PfPy9WShUE))

Arquivos:

- [Tutorial (notebook)](tutorial_segmentacao_cor.ipynb)
- [Vídeo-pitch (YouTube)](https://www.youtube.com/watch?v=3PfPy9WShUE)
- [Entrega 1 (definição do tema)](entrega1/entrega1.pdf)
- [Imagens de teste e fontes](imagens/README.md)

## Resultados

| Teste | RGB (caixa de limiares) | HSV (faixa de matiz) |
|---|---|---|
| Imagem sintética, parte na sombra encontrada | 0% | 99% a 100% |
| Parede amarela, parte na sombra encontrada | 0% | 100% |
| Foto com metade da luz (IoU com a máscara original) | 0 (máscara vazia) | 0,997 |
| Parede vermelha: parede / chão marcados | 99,8% / 99,9% (pega o chão junto) | 97,5% / 1,3% |

Na sombra, os três canais RGB caem juntos e a caixa de limiares perde o
objeto. No HSV a sombra muda só o V, e a matiz continua dentro da faixa.

## Uso de IA
Apenas utilizado na entrega 2

O código do notebook foi implementado com o auxílio do Claude (Anthropic),
pelo Claude Code. Os textos também foram redigidos com o auxílio do Claude, a
partir desse código e dos resultados, e revisados pelo grupo. O Gemini
(Google) foi usado só para pesquisar fotos com licença livre. A seção 9 do
notebook detalha o uso e como o resultado foi verificado.

## Como executar

Requer Python 3.10 ou mais recente.

```
pip install -r requirements.txt
jupyter notebook tutorial_segmentacao_cor.ipynb
```

O OpenCV está no `requirements.txt` só para conferir a nossa conversão. A
conversão e a segmentação do tutorial usam apenas NumPy.

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
