# 📮 Desafio_CEP_API — Consulta de Endereços por CEP

Projeto desenvolvido como desafio do curso **"Java: consumindo API, gravando arquivos e lidando com erros"** da [Alura](https://www.alura.com.br/), parte da formação **Java** em parceria com a **Oracle Next Education (ONE)**.

---

## 📋 Sobre o Projeto

O **DesafioCEPAPI** é uma aplicação Java de linha de comando que consulta endereços a partir de um CEP informado pelo usuário, utilizando a API pública **ViaCEP**. Os dados retornados são desserializados com **Gson** e persistidos localmente em um arquivo `enderecos.json`.

---

## ✨ Funcionalidades

- 🔍 Consulta de endereço a partir de um CEP via [ViaCEP](https://viacep.com.br/)
- 🗂️ Desserialização do JSON retornado para um objeto `Endereco`
- 💾 Persistência dos dados consultados em arquivo `enderecos.json`
- ⚠️ Tratamento de erros para CEPs inválidos ou inexistentes
- 🔁 Menu interativo para consultas sucessivas

---

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Descrição |
|---|---|
| Java 17+ | Linguagem principal |
| HttpClient | Requisições HTTP nativas do Java |
| Gson | Serialização/desserialização de JSON |
| ViaCEP | API pública de consulta de CEPs brasileiros |
| IntelliJ IDEA | IDE utilizada no desenvolvimento |

---

## 🚀 Como Executar

### Pré-requisitos

- Java 17 ou superior instalado
- Biblioteca [Gson](https://mvnrepository.com/artifact/com.google.code.gson/gson) adicionada ao classpath (ou via Maven/Gradle)

### Clonando o Repositório

```bash
git clone https://github.com/Lujan023/DesafioCEPAPI.git
cd DesafioCEPAPI
```

### Adicionando o Gson (caso use Maven)

Adicione ao seu `pom.xml`:

```xml
<dependency>
    <groupId>com.google.code.gson</groupId>
    <artifactId>gson</artifactId>
    <version>2.10.1</version>
</dependency>
```

### Rodando a Aplicação

Execute a classe principal pelo IntelliJ IDEA ou via terminal:

```bash
javac -cp .:gson-2.10.1.jar src/**/*.java
java -cp .:gson-2.10.1.jar Main
```

---

## 💡 Como Usar

1. Execute a aplicação
2. Quando solicitado, informe um CEP brasileiro (ex: `01310-100`)
3. O endereço correspondente será exibido no terminal
4. Os dados serão salvos automaticamente no arquivo `enderecos.json`
5. Digite `sair` para encerrar o programa

### Exemplo de saída

```
Digite o CEP que deseja consultar (ou 'sair' para encerrar):
> 01310100

CEP:        01310-100
Logradouro: Avenida Paulista
Bairro:     Bela Vista
Cidade:     São Paulo
UF:         SP

Endereço salvo em enderecos.json com sucesso!
```

### Exemplo do arquivo `enderecos.json`

```json
[
  {
    "cep": "01310-100",
    "logradouro": "Avenida Paulista",
    "bairro": "Bela Vista",
    "localidade": "São Paulo",
    "uf": "SP"
  }
]
```

---

## 📁 Estrutura do Projeto

```
DesafioCEPAPI/
├── src/
│   ├── model/
│   │   └── Endereco.java        # Record/classe que representa o endereço
│   ├── service/
│   │   ├── ConsultaCepService.java   # Consome a API ViaCEP
│   │   └── GeraArquivoService.java   # Salva os dados em JSON
│   └── Main.java                # Ponto de entrada e menu interativo
├── enderecos.json               # Arquivo gerado com os endereços consultados
├── .gitignore
└── DesafioAluraAPI.iml
```

---

## 🔗 API Utilizada

**ViaCEP** — API pública e gratuita para consulta de CEPs brasileiros.

Endpoint: `https://viacep.com.br/ws/{CEP}/json/`

Exemplo: [https://viacep.com.br/ws/01310100/json/](https://viacep.com.br/ws/01310100/json/)

---

## 📚 Aprendizados

Este projeto foi desenvolvido para praticar:

- Consumo de APIs REST com `HttpClient` nativo do Java
- Desserialização de JSON com **Gson**
- Gravação e leitura de arquivos com `FileWriter`
- Tratamento de exceções (`IOException`, `InterruptedException`)
- Uso de **Records** do Java para modelagem de dados
- Boas práticas de separação de responsabilidades (model / service)

---

## 🧑‍💻 Autor

Feito por **[Lujan023](https://github.com/Lujan023)** durante a formação Java com Oracle Next Education da Alura.

---
