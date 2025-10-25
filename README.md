#Ransomware - Estudo de Caso em Python

**⚠️ AVISO IMPORTANTE: Este projeto foi desenvolvido exclusivamente para fins educacionais e de estudo sobre segurança da informação. O uso indevido deste código para atividades maliciosas é ilegal e de total responsabilidade do usuário.**

---

## 📝 Descrição

Este repositório contém um par de scripts em Python que simulam o comportamento básico de um ransomware. O objetivo é demonstrar os conceitos de criptografia de arquivos e a importância de práticas seguras de programação e gerenciamento de chaves.

- **`ransoware.py`**: Um script que criptografa arquivos de texto (`.txt`) em seu diretório.
- **`descriptografar.py`**: Um script que utiliza uma chave para reverter o processo e descriptografar os arquivos.

## 📂 Estrutura do Projeto

```
teste_files/
├── ransoware.py             # Script de criptografia
├── descriptografar.py       # Script de descriptografia
├── senhas.txt               # Arquivo de exemplo para ser criptografado
├── dados_confidenciais.txt  # Outro arquivo de exemplo
├── chave.key                # (Gerado) Chave de criptografia/descriptografia
└── LEIA-ME.txt              # (Gerado) Nota de resgate
```

## ⚙️ Como Funciona

### Criptografia (`ransoware.py`)

1.  **Geração de Chave**: Ao ser executado pela primeira vez, o script verifica se o arquivo `chave.key` existe. Caso não exista, ele gera uma nova chave de criptografia simétrica usando a biblioteca `cryptography` e a salva.
2.  **Busca de Arquivos**: O script varre o diretório atual em busca de todos os arquivos com a extensão `.txt`.
3.  **Exclusões**: Ele ignora arquivos de sistema, o próprio script e a nota de resgate (`LEIA-ME.txt`) para evitar a autodestruição ou corrupção do processo.
4.  **Criptografia**: O conteúdo de cada arquivo encontrado é lido, criptografado e reescrito no mesmo arquivo, substituindo os dados originais pelos dados cifrados.
5.  **Nota de Resgate**: Por fim, cria o arquivo `LEIA-ME.txt` com uma mensagem simulando uma nota de resgate.

### Descriptografia (`descriptografar.py`)

1.  **Carregamento da Chave**: O script lê o arquivo `chave.key` para obter a chave necessária para a descriptografia.
2.  **Busca de Arquivos**: Assim como o ransomware, ele procura por todos os arquivos `.txt` no diretório.
3.  **Descriptografia**: Para cada arquivo encontrado (exceto a nota de resgate), ele tenta descriptografar seu conteúdo usando a chave carregada.
4.  **Tratamento de Erros**: Caso a chave esteja incorreta ou o arquivo não esteja criptografado corretamente, uma mensagem de falha é exibida, e o script continua para o próximo arquivo.

## 🚀 Como Usar

### Pré-requisitos

- Python 3.x
- Biblioteca `cryptography`

### Instalação

1.  Clone o repositório:
    ```sh
    git clone <https://github.com/ArgelCostaPinto>
    cd <Ransomware>
    ```

2.  Instale as dependências:
    ```sh
    pip install cryptography
    ```

### Execução

1.  **Criptografar os arquivos**:
    Execute o script `ransoware.py`. Certifique-se de ter alguns arquivos `.txt` de exemplo na pasta.
    ```sh
    python ransoware.py
    ```
    Você verá a mensagem "Ransomware executado com sucesso!!" e notará que o conteúdo dos seus arquivos `.txt` foi alterado e os arquivos `chave.key` e `LEIA-ME.txt` foram criados.

2.  **Descriptografar os arquivos**:
    Para recuperar os arquivos, execute o script `descriptografar.py`.
    ```sh
    python descriptografar.py
    ```
    A mensagem "Arquivos descriptografados com sucesso!" será exibida, e o conteúdo dos seus arquivos `.txt` voltará ao estado original.
