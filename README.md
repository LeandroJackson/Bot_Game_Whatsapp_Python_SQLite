# O-QUE-VOCE-PREFERE
# Jogo de Perguntas e Respostas "O QUE VOCÊ PREFERE" no WhatsApp

Este é um projeto de um bot para WhatsApp que implementa um jogo de perguntas e respostas "O QUE VOCÊ PREFERE" usando a biblioteca Selenium em Python. O objetivo do bot é interagir com os usuários, enviando perguntas de diferentes níveis de dificuldade e categorias.

## Funcionalidades

### Manipulação das Perguntas

O bot possui funções para manipulação das perguntas, incluindo:

- Função `pergunta(nivel, repeticao)`: Recebe um arquivo de texto com perguntas de um determinado nível, escolhe uma pergunta aleatória que ainda não foi repetida e retorna a pergunta e seu índice.
- Função `iteracao(text)`: Envia mensagens de iteração para os usuários de forma aleatória, com uma probabilidade de 40% de enviar uma pergunta iterativa e 60% de enviar a mensagem "O que vocês preferem?".
- Função `BOT_MENSAGEM(out)`: Envia uma mensagem para os contatos/grupos do WhatsApp usando o Selenium WebDriver.
- Função `EXCLUIR_MENSAGENS()`: Exclui todas as mensagens do contato/grupo para manter a privacidade.

### Manipulação do Banco de Dados

O bot utiliza o SQLite para manipulação dos dados dos contatos/grupos. As funções relacionadas ao banco de dados incluem:

- Função `adicionar_contato(nome, nivel1='', nivel2='', nivel3='', nivel4='', publico=0, adulto=0)`: Adiciona um novo contato/grupo ao banco de dados com seu nome, níveis de perguntas respondidas, configuração de privacidade e categorias de perguntas permitidas.
- Função `atualizar_perguntas(nome, nivel, ultimo_indice)`: Atualiza as perguntas respondidas por um determinado contato/grupo em um determinado nível.
- Função `contato_existe(nome)`: Verifica se um contato/grupo já existe no banco de dados.
- Função `obter_perguntas(nome, nivel)`: Obtém as perguntas respondidas por um determinado contato/grupo em um determinado nível.
- Função `obter_adulto(nome)`: Obtém a configuração de perguntas "extremas" (apenas para maiores de 18 anos) de um determinado contato/grupo.
- Função `atualizar_adulto(nome, novo_valor)`: Atualiza a configuração de perguntas "extremas" de um determinado contato/grupo.
- Função `atualizar_ultima_mensagem(nome, mensagem)`: Atualiza a última mensagem enviada por um determinado contato/grupo.
- Função `obter_ultima_mensagem(nome)`: Obtém a última mensagem enviada por um determinado contato/grupo.
- Função `incrementa_numero_mensagens(nome)`: Incrementa o número de mensagens recebidas por um determinado contato/grupo.
- Função `zera_numero_mensagens(nome)`: Zera o número de mensagens recebidas por um determinado contato/grupo.
- Função `get_numero_de_mensagens(nome_contato)`: Obtém o número de mensagens recebidas por um determinado contato/grupo.

### Funcionalidade do Jogo

A função principal `Game_OQVCP()` implementa a lógica do jogo. O bot verifica as mensagens recebidas, identifica o nível de dificuldade solicitado e categorias de perguntas, e responde com perguntas aleatórias de acordo com as configurações de cada contato/grupo. O jogo inclui diferentes categorias de perguntas, como normais, ousadas, quentes e extremas (para maiores de 18 anos).

Além disso, o bot possui regras de privacidade, como a exclusão das mensagens do contato/grupo e a possibilidade de configurar restrições de perguntas "quentes" e "extremas" para grupos públicos.

## Como Usar

1. Abra um ambiente Jupyter Notebook em sua máquina local.
2. Crie um novo notebook ou abra um existente.
3. Copie o código fornecido para o notebook.
4. Execute as células do notebook sequencialmente para importar as bibliotecas e definir as funções.
5. Execute a função `Game_OQVCP()` para iniciar o jogo.
6. Faça login no WhatsApp Web escaneando o código QR.
7. Interaja com o bot no WhatsApp enviando mensagens para o contato/grupo correspondente.

## Configuração do Projeto

O projeto requer a instalação das bibliotecas re, os, time, random, psutil, sqlite3, datetime, pandas, emoji, selenium e IPython. Certifique-se de ter o Chrome WebDriver instalado e configurado corretamente para o Selenium.

## Contribuição

Sinta-se à vontade para contribuir para este projeto. Você pode abrir issues para relatar problemas, sugerir novas funcionalidades ou enviar pull requests com melhorias no código.

## Observação

Este projeto foi desenvolvido com base no conhecimento e habilidades até a data 28/04/2023 e pode exigir atualizações para se adequar a futuras mudanças no WhatsApp ou nas bibliotecas utilizadas.
