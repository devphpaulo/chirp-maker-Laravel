# Chirp Maker - Laravel

Chirp Maker é uma aplicação Laravel que permite aos usuários criar e gerenciar "chirps" (mensagens curtas), simulando uma plataforma de blogging tipo o twitter, mas em baixa escala.

## Pré-Requisitos

Antes de começar, certifique-se de ter instalado:
- PHP (versão 7.4 ou superior)
- Composer
- Node.js e npm
- Um servidor de banco de dados (SQLite, MySQL)

## Configuração Inicial

1. **Clone o Repositório**
   
   ```bash
   git clone https://github.com/devphpaulo/chirp-maker-Laravel.git
   cd chirp-maker-Laravel
   ```

2. **Instalação de Dependências**

   Instale as dependências do PHP usando Composer, e as dependências do JavaScript usando npm:

   ```bash
   composer install
   npm install
   ```

## Compilação de Assets

Compile os assets do front-end com:

```bash
npm run dev
```

## Executando o Projeto

Inicie o servidor de desenvolvimento do Laravel:

```bash
php artisan serve
```

Isso iniciará o servidor em `http://localhost:8000`.

## Estrutura do Projeto

- **Models**: Os models são utilizados para interagir com as informações no banco de dados. Eles representam as tabelas do banco de dados como classes no Laravel.
- **Migrations**: As migrations são como um controle de versão para o seu banco de dados. Elas permitem que defina modificações e alterações na estrutura do banco de dados.
- **Controllers**: Os controllers lidam com a lógica de processamento de requisições. Eles recuperam dados do modelo e retornam respostas para o cliente na interface.

---
