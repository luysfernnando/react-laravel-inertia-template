<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

# Criando uma aplicação com Laravel 10, React.js 18 e Inertia.js com Autenticação e Docker

## ✨ Requisitos
<details>
<summary>1- Criando o projeto usando sail (Docker)</summary>

```bash
curl -s "https://laravel.build/example-app?with=mysql,redis" | bash
```
</details>
<details>
<summary>2- Instalando o pacote Inertia.js</summary>

2.1 Instalar o pacote Breeze:

```bash
# Instalando o Breeze
sail composer require laravel/breeze --dev
```



2.2 Instalando o Inertia.js com o Breeze:

```bash
# Instalando o Breeze com Inertia.js
sail php artisan breeze:install
```

Opções durante a instalação:

````
Dark Mode [opcional]
TypeScript [opcional]
Inertia SSR (Server-Side Rendering) [opcional]
Pest tests ao invés do PHPUnit [opcional] -> NO
 
````
</details>
<details>
<summary>3- Configurando o vite.config.js</summary>

Na raiz do projeto edite o arquivo `vite.config.js`:

```javascript
import { defineConfig } from 'vite';
import laravel from 'laravel-vite-plugin';
import react from '@vitejs/plugin-react';

export default defineConfig({
    plugins: [
        laravel({
            input: 'resources/js/app.tsx',
            refresh: true,
        }),
        react(),
    ],
    // Configuração pra funcionar o vite com o sail
    watch: {
        usePolling: true,
        origin: 'http://localhost'
    },
    server: {
        hmr: {
            host: 'localhost'
        }
    }
    // Fim da configuração
});
```
</details>

## 🚀 Tecnologias
Esse projeto contará com as mais diversas tecnologias, como por exemplo:

<table border="0">
<tr>
<td>PHP 8.1</td>
<td>Laravel 10</td>
<td>React.JS 18</td>
<td>Docker</td>
<td>Inertia.js</td>
<td>MySQL</td>
<td>Vite</td>
</tr>
</table>

## 📁 Entendendo a estrutura do projeto
<details>
<summary>Estrutura de pastas</summary>

```
.
├── app/ [App do Laravel]
│   ├── Console/
│   ├── Events/
│   ├── Exceptions/
│   ├── Http/
│   │   ├── Controllers/    [Controllers do Laravel]
│   │   ├── Middleware/
│   │   └── Requests/
│   ├── Models/             [Models do Laravel]
│   └── Providers/
├── bootstrap/
│   └── cache/
├── config/                 [Configurações do Laravel]
├── database/
│   ├── factories/          [Factories do Laravel]
│   ├── migrations/         [Migrations do Laravel]
│   └── seeders/            [Seeders do Laravel]
├── node_modules/
├── public/                 [Public do Laravel (onde fica os assets)]
├── resources/
│   ├── css/                [Onde fica os arquivos de css]
│   ├── js/                 [Pasta do React.js]
│   │   ├── Components/     [Componentes do React.js]
│   │   ├── Layouts/        [Layouts do React.js]
│   │   ├── Pages/          [Páginas do React.js]
│   │   ├── Plugins/        [Plugins do React.js]
│   │   ├── App.tsx         [Arquivo principal do React.js]
│   │   └── bootstrap.ts
│   └── views/              [Views do Laravel]
├── routes/
│   ├── api.php
│   ├── channels.php
│   ├── console.php
│   └── web.php             [Rotas do Laravel]
├── storage/
├── tests/
├── vendor/
├── .env                   [Variáveis de ambiente do Laravel]
├── .gitignore             [Arquivo de configuração do git]
├── docker-compose.yml     [Arquivo de configuração do Docker]
├── package.json           [Arquivo de configuração do Node.js]
├── postcss.config.js      [Arquivo de configuração do PostCSS]
├── README.md              [Arquivo de documentação]
├── tailwind.config.js     [Arquivo de configuração do Tailwind]
├── tsconfig.json          [Arquivo de configuração do TypeScript]
└── vite.config.js         [Arquivo de configuração do Vite]
```
</details>

## 💻 Executando o projeto
<details>
<summary>Docker + Laravel + MySQL</summary>

#### Iniciar
```bash
./vendor/bin/sail up
```
#### Parar
```bash
./vendor/bin/sail down
```
</details>
<details>
<summary>Vite + React.js + Inertia.js</summary>

#### Iniciar
```bash
sail npm run dev
```
#### Parar
```bash
Use as teclas "Ctrl + C"
```
</details>

Após iniciar os serviços, acesse o projeto em: [http://localhost](http://localhost)

## 📕 Documentação Oficial:
<details>
<summary>Back-end:</summary>

- [Laravel](https://laravel.com/docs/10.x)
- [Laravel Sail](https://laravel.com/docs/10.x/sail)
- [Laravel Breeze](https://laravel.com/docs/10.x/starter-kits#breeze-and-inertia)
- [Docker](https://docs.docker.com/)
- [Vite](https://vitejs.dev/guide/)
</details>
<details>
<summary>Front-end:</summary>

- [React.js](https://reactjs.org/docs/getting-started.html)
- [Tailwind CSS](https://tailwindcss.com/docs)
</details>
<details>
<summary>API:</summary>

- [Inertia.js](https://inertiajs.com/)
</details>
