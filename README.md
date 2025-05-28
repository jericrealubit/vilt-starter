# Vilt Stack Starter

A full-stack starter template combining Laravel, Inertia.js, Vue 3, Vite and Tailwind CSS (“Vilt”).

## Features

• Backend powered by Laravel 12
• Seamless SPA experience with Inertia.js + Vue 3
• Modern build tooling with Vite
• Utility-first styling with Tailwind CSS
• Out-of-the-box Docker dev environment via Sail
• Zero-config testing with PestPHP & PHPUnit
• Pre-configured linting, formatting & static analysis

---

## Tech Used

### Backend (Composer)

• PHP ^8.2
• Laravel Framework ^12.0
• Inertia.js adapter (inertiajs/inertia-laravel)
• Laravel Tinker
• Laravel Sail (Docker)
• SQLite (local dev)
• FakerPHP (factories)
• PestPHP & Pest-Laravel plugin
• PHPUnit
• Mockery (mocks)
• Nunomaduro Collision (pretty errors)
• Laravel Pint (code style)
• Laravel Pail (static analysis)

### Frontend (NPM / Vite)

• Vite ^6.2.4
• laravel-vite-plugin ^1.2.0
• @vitejs/plugin-vue ^5.2.4
• @tailwindcss/vite ^4.0.0
• Tailwind CSS ^4.0.0
• Vue 3 & @inertiajs/vue3 ^2.0.11
• @vue/server-renderer ^3.5.15
• Axios ^1.8.2
• concurrently ^9.0.1

---

## Requirements

• PHP 8.2+
• Composer
• Node.js 16+ & npm
• Docker (for Sail) or local MySQL/Postgres
• Optional: CUDA/GPU if using advanced queue/workers

---

## Installation

1. Clone and enter the repo

    ```bash
    git clone https://github.com/your-org/vilt-starter.git
    cd vilt-starter
    ```

2. Copy and configure environment

    ```bash
    cp .env.example .env
    ```

    Generate app key & SQLite file (if using Sail):

    ```bash
    composer install
    php artisan key:generate
    touch database/database.sqlite
    ```

3. Install NPM deps and build assets

    ```bash
    npm install
    npm run build
    ```

4. Run migrations & seed
    ```bash
    php artisan migrate --seed
    ```

---

## Development

• Start Laravel + queue + Vite in one command:

```bash
composer dev
```

– Starts `php artisan serve`
– Listens to jobs with `php artisan queue:listen`
– Runs Vite dev server with HMR

• Or run back- and front-end separately:

```bash
php artisan serve
npm run dev
```

---

## NPM Scripts

• `npm run dev` — Vite development server
• `npm run build` — Vite production build

## Composer Scripts

• `composer dev` — combined Laravel serve, queue listener & Vite dev
• `composer test` — clears config cache & runs tests
• Auto-publish assets & migrate on `composer install`

---

## Testing

```bash
composer test
```

Uses PestPHP (with PHPUnit under the hood).
Write tests in the `tests/` directory.

---

## Contributing

1. Fork the repo
2. Create a feature branch
3. Commit & push your changes
4. Open a Pull Request

Please follow PSR-12 and run `composer test` before submitting.

---

## License

MIT © Your Name / Your Organization
