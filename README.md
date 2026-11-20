# EBAC – Backend Python – Exercício Módulo 4 (Threads e Processos)

Web scraper do catálogo de filmes do professor (https://havokkmorands.github.io/movie-catalog/), que substituiu o IMDb por causa dos bloqueios do site.

Para cada filme pega **título, lançamento, nota e sinopse** e grava em `movies.csv`.

## Comparativo

A mesma extração roda de 3 jeitos e o script mostra o tempo de cada um:

| Modo | Como funciona |
|---|---|
| Sequencial | 1 thread, um filme por vez |
| Threads | `ThreadPoolExecutor` com `min(MAX_THREADS, nº de filmes)` threads |
| Processos | `ProcessPoolExecutor` com `min(MAX_THREADS, nº de filmes)` processos |

Como o trabalho é quase todo espera de rede (I/O), threads e processos ficam bem mais rápidos que o sequencial.

## Como rodar

```bash
pip install -r requirements.txt
python multithreading.py        # MAX_THREADS = 10
python multithreading.py 5      # testa com 5 threads
python multithreading.py 20     # testa com 20 threads
```
