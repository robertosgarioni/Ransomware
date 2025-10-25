# Estudo de Caso: Simulação de Ransomware em Python

> ⚠️ **PROPÓSITO ESTRITAMENTE EDUCACIONAL**
>
> Este projeto foi criado com o único objetivo de estudar e demonstrar os mecanismos de cibersegurança por trás de um ataque de ransomware. Ele serve para entender as ameaças e, o mais importante, como construir defesas.
>
> **O uso deste código para qualquer atividade maliciosa é ilegal e antiético.** O autor não se responsabiliza pelo mau uso das informações aqui contidas.

## O que é este projeto?

Este repositório é um "laboratório" que simula o ciclo de vida básico de um ransomware. Ele contém dois scripts principais em Python: um para "sequestrar" (criptografar) arquivos e outro para "resgatar" (descriptografar) os mesmos arquivos.

O objetivo é visualizar na prática o poder da criptografia simétrica e entender por que a **proteção da chave de criptografia** é um dos pilares da segurança da informação.

## Os Componentes

O projeto é dividido em duas partes:

1.  **`ransoware.py` (O "Ataque")**
    * Este script é a simulação do malware. Ele varre o diretório em busca de arquivos de texto (`.txt`) para criptografar.
    * Se nenhuma chave existir, ele gera a `chave.key` (a chave-mestra para trancar e destrancar os arquivos).
    * Ele lê o conteúdo de cada arquivo `.txt`, o criptografa e salva o conteúdo cifrado de volta no arquivo original.
    * Por fim, ele cria uma "nota de resgate" (`LEIA-ME.txt`) para simular o ataque completo.

2.  **`descriptografar.py` (O "Resgate")**
    * Este script é a "ferramenta de recuperação".
    * Ele precisa do arquivo `chave.key` para funcionar.
    * Ele varre o diretório e usa a chave para descriptografar todos os arquivos `.txt` que encontrar, restaurando o conteúdo original.

## Estrutura do Diretório

Após a execução do ataque, seu diretório de testes ficará assim:
