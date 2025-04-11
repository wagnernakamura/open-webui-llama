# Open WebUI com LLMs via Ollama

Este guia explica passo a passo como montar um servidor local do **Open WebUI**, utilizando **LLMs** como `llama3.2:1b` e `deepseek-r1:1.5b`, com o backend utilizando modelos baixados no **Ollama**.

## Requisitos

- Sistema operacional: **Windows**, macOS ou Linux
- Acesso à internet
- Permissões de instalação de software
- Liberações de firewall

---

## Passo 1: Baixar o Python 3.11.8

O Open WebUI requer uma versão compatível do Python. A utilizada foi a **3.11.8**.

🔗 Acesse: [https://www.python.org/downloads/release/python-3118/](https://www.python.org/downloads/release/python-3118/) - Windows installer (64-bit)

### Dicas de instalação:
- No Windows, marque a opção **“Add Python to PATH”**.
- No Linux/Mac, use pyenv ou gerencie versões manualmente.

Verifique a instalação:
```bash
python --version
# Ou
python3 --version
```

Output:
```bash
PS C:\Users\wagner> Python --version
Python 3.11.8
```


## Passo 2: Instalar o Ollama

O Ollama é responsável por rodar localmente os modelos LLM.

🔗 Acesse: https://ollama.com/download

Baixe a versão apropriada para seu sistema operacional e siga as instruções de instalação.

Verifique se a instalação do Ollama ocorreu com sucesso:

```bash
ollama --version
```

Output:
```bash
PS C:\Users\wagner> ollama --version
ollama version is 0.6.5
```

## Passo 3: Escolher e baixar os modelos LLM

Acesse o catálogo de modelos da Ollama e selecione o modelo que deseja trabalhar.

🔗 [https://ollama.com/library](https://ollama.com/library)

Neste exemplo, utilizaremos os seguintes modelos:
- `llama3.2:1b`
- `deepseek-r1:1.5b`

### Para instalar ou testar os modelos diretamente

Instalar os modelos diretamente.
```bash
ollama run llama3.2:1b
ollama run deepseek-r1:1.5b
```

---

## Passo 4: Instalar o Open WebUI

Instale o Open WebUI diretamente via pip install.

```bash
pip install open-webui
```

Se estiver utilizando um ambiente virtual, ative-o antes (não utilizei na minha execução).

---

## Passo 5: Executar o Open WebUI

Agora é a hora de iniciar o servidor, digite no cmd utilizado o comando serve.

```bash
open-webui serve
```

Se tudo estiver correto, o servidor será iniciado no **localhost** na porta padrão **8080**.

---

## Passo 6: Acessar via navegador

Abra o navegador e acesse a url descrita abaixo e aproveite seu modelo de LLM executando-o localmente.

🔗 [http://localhost:8080/](http://localhost:8080/)

Agora é só escolher o modelo, instalado via Ollama, na interface do Open WebUI, interagir e se divertir!

---

## Dicas adicionais

- Mantenha seu Python, o Ollama e o Open WebUI atualizados, sempre garantindo a compatibilidade de versões (no momento da criação desse material o Open WebUI não possuia uma versão compativel com o Python 3.13.3).
- Use ambientes virtuais (`venv`) para evitar conflitos de pacotes.
- Explore mais modelos e versões no site da Ollama, o céu e o Ollama são os limites!!!
- Combine o Open WebUI com autenticação ou reverse proxy se for publicar para acesso externo (Security First, primeiramente garanta sua segurança e de seus dados).

---

## Referências

- [Python 3.11.8](https://www.python.org/downloads/release/python-3118/)
- [Ollama](https://ollama.com)
- [Ollama Model Library](https://ollama.com/library)
- [Open WebUI PyPI](https://pypi.org/project/open-webui/)

---

## Testado em

| Sistema       | Python     | Ollama       | Modelos                       |
|---------------|------------|--------------|-------------------------------|
| Windows 11    | 3.11.8     | v0.1.x       | llama3.2:1b, deepseek-r1:1.5b |

---

**Divirta-se com sua própria IA local, segura e rápida (No quesito velocidade, vai depende da quantidade dos dados usados para treinar o modelo, quanto mais dados foram utilizados no treinamento do modelo, mais pesado ele vai ser! - Nesse exemplo usei dois modelos um de 1 bilhão de tokens e outro de 1.5 bilhões)**
