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

3. **Configuração de Ambiente**

   Copie o arquivo `.env.example` para `.env` e ajuste as configurações de banco de dados:

   ```bash
   cp .env.example .env
   ```

   Atualize as seguintes linhas no arquivo `.env` para corresponder às configurações do seu banco de dados:

   ```
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=nome_do_banco
   DB_USERNAME=usuario
   DB_PASSWORD=senha
   ```

4. **Geração de Key**

   Gere a chave da aplicação com o Artisan:

   ```bash
   php artisan key:generate
   ```

5. **Migrações de Banco de Dados**

   Execute as migrações para criar as tabelas no banco de dados:

   ```bash
   php artisan migrate
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

## Criando Eventos e Listeners

Para registrar eventos e listeners, siga estes passos:

1. **Criação de Evento e Listener**

   Crie um evento e um listener via Artisan:

   ```bash
   php artisan make:event ChirpEvent
   php artisan make:listener LogChirpListener --event=ChirpEvent
   ```

2. **Registrar o Listener**

   Abra `app/Providers/EventServiceProvider.php` e registre seu evento e listener no array `$listen`:

   ```php
   protected $listen = [
       'App\Events\ChirpEvent' => [
           'App\Listeners\LogChirpListener',
       ],
   ];
   ```
3. **Log no Laravel.log**

   No método `handle` do seu listener `LogChirpListener`, adicione um log para registrar as informações:

   ```php
   public function handle(ChirpEvent $event)
   {
       Log::info("Evento Chirp registrado", ['chirp' => $event->chirp]);
   }
   ```

## Explorando o Laravel Tinker

Você pode usar o Laravel Tinker para interagir com a aplicação via linha de comando. Por exemplo, para criar um novo Chirp:

```bash
php artisan tinker
>>> $chirp = new App\Models\Chirp(['content' => 'Hello, Chirp!']);
>>> $chirp->save();
```

---
