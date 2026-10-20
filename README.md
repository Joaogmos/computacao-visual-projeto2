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
- [x] Motivação com imagem sintética de teste (com gabarito)
- [x] Teoria e prática do modelo RGB
- [x] Conversão RGB → HSV implementada e validada (contra `colorsys` e
      OpenCV, em cerca de 250 mil cores)
- [x] Segmentação por faixa de matiz (imagem sintética e duas fotos)
- [x] Comparação RGB × HSV (imagem sintética, duas fotos e experimento de iluminação)
- [x] Limitações, conclusão, declaração de uso de IA e referências
- [x] Reescrita dos textos do notebook
- [ ] Revisão final dos textos pelo grupo
- [ ] Vídeo-pitch (até 5 min)

Documentos:

- [Entrega 1 (definição do tema)](entrega1/entrega1.pdf)
- [Tutorial (notebook)](tutorial_segmentacao_cor.ipynb)
- [Imagens de teste e fontes](imagens/README.md)

## Principais resultados

| Teste | RGB (caixa de limiares) | HSV (faixa de matiz) |
|---|---|---|
| Imagem sintética, parte na sombra encontrada | 0% | 99% a 100% |
| Parede amarela, parte na sombra encontrada | 0% | 100% |
| Foto com metade da luz (IoU com a máscara original) | 0 (máscara vazia) | 0,997 |
| Parede vermelha: parede / chão marcados | 99,8% / 99,9% (pega o chão junto) | 97,5% / 1,3% |

## Uso de IA

O código do notebook foi implementado com o auxílio do Claude (Anthropic),
pelo Claude Code. Os textos também foram redigidos com o auxílio do Claude, a
partir desse código e dos resultados, e revisados pelo grupo.
Usamos o Gemini (Google) só para pesquisar fotos com licença livre. Os detalhes
e a forma de verificação estão na seção 9 do notebook.

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
