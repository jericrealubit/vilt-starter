Based on your package.json and composer.json files, I can see this is actually a **Laravel + Vue.js + Inertia.js** project, not a ViLT starter. Here's an updated README with the correct tech stack:

````markdown
# 🚀 Laravel Vue Inertia Starter

A modern full-stack web application starter template built with Laravel, Vue.js, and Inertia.js. Perfect for building reactive single-page applications with the power of Laravel's backend and Vue's frontend capabilities.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PHP 8.2+](https://img.shields.io/badge/PHP-8.2+-777BB4.svg?logo=php&logoColor=white)](https://php.net)
[![Laravel 12](https://img.shields.io/badge/Laravel-12-FF2D20?logo=laravel&logoColor=white)](https://laravel.com)

## 🎯 Overview

This project provides a clean, modern starting point for building full-stack web applications. It combines Laravel's robust backend framework with Vue.js's reactive frontend capabilities, connected seamlessly through Inertia.js for a true SPA experience without the API complexity.

## ✨ Features

-   🔧 **Laravel 12** - Latest Laravel framework with modern PHP features
-   ⚡ **Vue.js 3** - Composition API and reactive frontend
-   🔗 **Inertia.js** - Modern monolith architecture
-   🎨 **Tailwind CSS 4** - Utility-first CSS framework
-   ⚡ **Vite** - Lightning-fast build tool
-   🧪 **Pest Testing** - Elegant testing framework
-   🐳 **Laravel Sail** - Docker development environment
-   🔄 **Hot Module Replacement** - Instant development feedback

## 🛠️ Tech Stack

### Backend

![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)
![Composer](https://img.shields.io/badge/Composer-885630?style=for-the-badge&logo=composer&logoColor=white)

### Frontend

![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Inertia.js](https://img.shields.io/badge/Inertia.js-9553E9?style=for-the-badge&logo=inertia&logoColor=white)

### Styling & Build Tools

![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![NPM](https://img.shields.io/badge/NPM-CB3837?style=for-the-badge&logo=npm&logoColor=white)

### Development Tools

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Pest](https://img.shields.io/badge/Pest-6366F1?style=for-the-badge&logo=php&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

### Additional Tools

![Axios](https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white)
![Pint](https://img.shields.io/badge/Laravel_Pint-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)

## 🚦 Quick Start

### Prerequisites

-   🐘 **PHP 8.2** or higher
-   🎼 **Composer** 2.0+
-   📦 **Node.js 18** or higher
-   🗄️ **Database** (MySQL, PostgreSQL, or SQLite)

### Installation

1. **Clone the repository**
    ```bash
    git clone https://github.com/jericrealubit/vilt-starter.git
    cd vilt-starter
    ```
````

2. **Install PHP dependencies**

    ```bash
    composer install
    ```

3. **Install Node dependencies**

    ```bash
    npm install
    ```

4. **Environment setup**

    ```bash
    cp .env.example .env
    php artisan key:generate
    ```

5. **Database setup**

    ```bash
    touch database/database.sqlite  # For SQLite
    php artisan migrate
    ```

6. **Start development servers**

    ```bash
    composer run dev
    ```

    This runs all services concurrently:

    - 🌐 Laravel server on `http://localhost:8000`
    - 🔄 Queue worker for background jobs
    - ⚡ Vite dev server with HMR

### 🐳 Docker Setup (Laravel Sail)

```bash
# Start with Sail
./vendor/bin/sail up -d

# Install dependencies inside container
./vendor/bin/sail composer install
./vendor/bin/sail npm install

# Run migrations
./vendor/bin/sail artisan migrate

# Start dev servers
./vendor/bin/sail npm run dev
```

## 📖 Usage Examples

### Creating a New Page

1. **Create a Laravel route** (`routes/web.php`):

    ```php
    Route::get('/dashboard', function () {
        return Inertia::render('Dashboard', [
            'user' => auth()->user(),
            'stats' => ['visitors' => 1234]
        ]);
    });
    ```

2. **Create Vue component** (`resources/js/Pages/Dashboard.vue`):

    ```vue
    <template>
        <div class="bg-white rounded-lg shadow p-6">
            <h1 class="text-2xl font-bold text-gray-900">
                Welcome, {{ user.name }}!
            </h1>
            <p class="mt-2 text-gray-600">
                You have {{ stats.visitors }} visitors today.
            </p>
        </div>
    </template>

    <script setup>
    defineProps({
        user: Object,
        stats: Object,
    });
    </script>
    ```

### Making API Requests

```javascript
import { router } from "@inertiajs/vue3";

// Navigate with data
router.post("/users", {
    name: "John Doe",
    email: "john@example.com",
});

// Or using axios for traditional AJAX
import axios from "axios";

const response = await axios.get("/api/users");
```

## 📁 Project Structure

```
laravel-vue-starter/
├── 📁 app/                    # Laravel application logic
│   ├── 📁 Http/Controllers/   # Request handlers
│   ├── 📁 Models/            # Eloquent models
│   └── 📁 Providers/         # Service providers
├── 📁 database/              # Database files
│   ├── 📁 migrations/        # Database migrations
│   └── 📁 seeders/          # Database seeders
├── 📁 resources/             # Frontend resources
│   ├── 📁 js/               # Vue.js components
│   │   ├── 📁 Pages/        # Inertia pages
│   │   ├── 📁 Components/   # Reusable components
│   │   └── 📄 app.js        # Main JS entry
│   └── 📁 css/              # Stylesheets
├── 📁 routes/                # Application routes
│   ├── 📄 web.php           # Web routes
│   └── 📄 api.php           # API routes
├── 📁 tests/                 # Pest tests
├── 📄 package.json          # Node dependencies
├── 📄 composer.json         # PHP dependencies
├── 📄 vite.config.js        # Vite configuration
└── 📄 tailwind.config.js    # Tailwind configuration
```

## 🧪 Testing

Run the test suite using Pest:

```bash
# Run all tests
composer run test

# Run specific test file
php artisan test tests/Feature/ExampleTest.php

# Run with coverage
php artisan test --coverage
```

## 🎨 Available Scripts

### Composer Scripts

```bash
composer run dev        # Start all development servers
composer run test       # Run test suite
```

### NPM Scripts

```bash
npm run dev            # Start Vite development server
npm run build          # Build for production
```

### Artisan Commands

```bash
php artisan serve      # Start Laravel server
php artisan queue:work # Start queue worker
php artisan migrate    # Run migrations
php artisan tinker     # Laravel REPL
```

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](CONTRIBUTING.md) for details.

1. 🍴 Fork the repository
2. 🌿 Create a feature branch (`git checkout -b feature/amazing-feature`)
3. 💾 Commit your changes (`git commit -m 'Add amazing feature'`)
4. 📤 Push to the branch (`git push origin feature/amazing-feature`)
5. 🔄 Open a Pull Request

## 📚 Documentation

-   📖 [Laravel Documentation](https://laravel.com/docs)
-   ⚡ [Vue.js Guide](https://vuejs.org/guide/)
-   🔗 [Inertia.js Documentation](https://inertiajs.com/)
-   🎨 [Tailwind CSS Docs](https://tailwindcss.com/docs)
-   ⚡ [Vite Documentation](https://vitejs.dev/)

## 🐛 Issues & Support

If you encounter any issues or have questions:

-   🐛 [Report bugs](https://github.com/jericrealubit/vilt-starter/issues)
-   💬 [Discussions](https://github.com/jericrealubit/vilt-starter/discussions)
-   📧 Contact: [your-email@example.com]

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

-   🔥 [Laravel Team](https://laravel.com/team)
-   💚 [Vue.js Core Team](https://vuejs.org/about/team.html)
-   🔗 [Inertia.js Creator](https://twitter.com/reinink)
-   🎨 [Tailwind CSS Team](https://tailwindcss.com/team)

---

<div align="center">

**⭐ Star this repository if you find it helpful!**

Made with ❤️ by [Jeric Realubit](https://github.com/jericrealubit)

</div>
```

## Key Updates Made:

1. **🔄 Corrected Project Type**: Changed from ViLT to Laravel+Vue+Inertia
2. **🛠️ Updated Tech Stack**: Added proper badges for Laravel, Vue.js, Inertia.js, Tailwind CSS, etc.
3. **📦 Package-Based Features**: Reflected actual dependencies from your files
4. **🚀 Proper Installation**: Laravel-specific setup instructions
5. **🐳 Sail Integration**: Added Laravel Sail Docker setup
6. **🧪 Pest Testing**: Included Pest testing framework
7. **⚡ Vite Configuration**: Modern build tool setup
8. **🎨 Tailwind CSS**: Modern styling framework
9. **📁 Laravel Structure**: Proper Laravel project structure
10. **🔧 Development Scripts**: Both Composer and NPM scripts
