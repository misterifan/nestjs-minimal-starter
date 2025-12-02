# NestJS Minimal Starter 🚀
NestJS Minimal Starter / Minimal Boilerplate

![Node.js](https://img.shields.io/badge/Node.js-20.x-green?logo=node.js&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-v11.1.9-red?logo=nestjs&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5.x-blue?logo=typescript&logoColor=white)
![npm](https://img.shields.io/badge/npm-10.x-orange?logo=npm&logoColor=white)
![License](https://img.shields.io/badge/license-MIT-green)
![Build](https://img.shields.io/github/actions/workflow/status/yourusername/nestjs-minimal-starter/node.js.yml?branch=main&label=build&logo=github)

A **minimal NestJS boilerplate** ready for development with:

- ✅ Global **ValidationPipe** (`class-validator` + `class-transformer`)
- ✅ TypeScript **path aliases** (`@/*` → `src/*`)
- ✅ Ready for **development** & **production** builds
- ✅ Console log shows server **running port**

---

<details>
<summary>🏗 Project Structure</summary>
project/
├─ src/
│ ├─ main.ts # Application entry point
│ ├─ app.module.ts
│ └─ modules/
├─ dist/ # Compiled JS (auto-generated)
├─ package.json
├─ tsconfig.json
├─ tsconfig.build.json
└─ nest-cli.json

</details>

<details>
<summary>⚡ Installation</summary>

# Clone the repository
git clone https://github.com/yourusername/nestjs-minimal-starter.git
cd nestjs-minimal-starter

# Install dependencies
npm install

</details>

<details>
<summary>🚀 Running the App</summary>
Development
npm run start:dev
- Runs with live reload
- dist/ folder not required
- Console output:
🚀 Application is running on: http://localhost:3000

Production
npm run start:prod
- Runs prestart:prod → builds TypeScript into dist/
- Executes node dist/main.js

</details>

<details>
<summary>📝 Scripts</summary>
| Script       | Description                        |
| ------------ | ---------------------------------- |
| `build`      | Compile TypeScript → JS in `dist/` |
| `start`      | Run NestJS app (default)           |
| `start:dev`  | Dev mode with live reload          |
| `start:prod` | Build + run production app         |
| `lint`       | Lint project                       |
| `format`     | Format code using Prettier         |
</details> <details> <summary>🔧 Features</summary>

Path Aliases
Configured in tsconfig.json:
"baseUrl": "./",
"paths": { "@/*": ["./src/*"] }

Usage:
import { AppService } from '@/app.service';
import { UserModule } from '@/modules/user/user.module';

ValidationPipe
Global in main.ts:
app.useGlobalPipes(new ValidationPipe({
    whitelist: true,
    forbidNonWhitelisted: true,
    transform: true,
    transformOptions: { enableImplicitConversion: true },
}));

- Automatically validates DTOs
- Converts types (e.g., string → number)
- Rejects unknown properties

Server Port
const port = process.env.PORT || 3000;
await app.listen(port);
console.log(`🚀 Application is running on: http://localhost:${port}`);

</details>

<details>
<summary>💡 Notes</summary>

Ensure rootDir in tsconfig.build.json includes all TypeScript files to avoid Cannot find module 'dist/main'

Use npm run start:dev for development

Dist folder is automatically generated after build

</details> 

<details> 
<summary>📜 License</summary>
MIT
</details>