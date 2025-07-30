# GlobeTrek - Windows Setup Guide

## Prerequisites

### 1. Install Node.js
- Download Node.js 18 or 20 from [nodejs.org](https://nodejs.org/)
- Choose the "LTS" version (recommended)
- Run the installer and follow the setup wizard
- Verify installation by opening PowerShell or Command Prompt and running:
  ```
  node --version
  npm --version
  ```

### 2. Install VS Code (Optional but recommended)
- Download from [code.visualstudio.com](https://code.visualstudio.com/)
- Install recommended extensions:
  - ES7+ React/Redux/React-Native snippets
  - Tailwind CSS IntelliSense
  - TypeScript Importer
  - Auto Rename Tag
  - Prettier - Code formatter

## Project Setup

### 1. Extract/Clone the Project
- Extract the project files to a folder like `C:\Users\YourName\Documents\GlobeTrek`
- Or clone with Git: `git clone <repository-url>`

### 2. Open in VS Code
- Open VS Code
- File → Open Folder → Select your project folder
- Or open PowerShell in the project folder and run: `code .`

### 3. Install Dependencies
Open the integrated terminal in VS Code (Ctrl + `) and run:
```bash
npm install
```

### 4. Start the Development Server

**Option 1: Use cross-env (recommended)**
```bash
npx cross-env NODE_ENV=development tsx server/index.ts
```

**Option 2: Set environment variable first**
```cmd
set NODE_ENV=development
npx tsx server/index.ts
```

**Option 3: Use PowerShell**
```powershell
$env:NODE_ENV="development"; npx tsx server/index.ts
```

The application will start on `http://localhost:5000`

## Common Windows Issues & Solutions

### Issue 1: ENOTSUP Error (Fixed)
If you see an error like `ENOTSUP` or `operation not supported`, this is now fixed in the updated server configuration.

### Issue 2: Port Already in Use
If port 5000 is busy, you can specify a different port:
```bash
set PORT=3000 && npm run dev
```

### Issue 3: PowerShell Execution Policy
If you get execution policy errors, run PowerShell as Administrator and execute:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Issue 4: Node.js Path Issues
If `npm` commands don't work:
1. Restart your terminal/VS Code
2. Check if Node.js is in your PATH
3. Reinstall Node.js if necessary

## Project Structure

```
GlobeTrek/
├── client/                 # React frontend
│   ├── src/
│   │   ├── components/     # UI components
│   │   ├── pages/          # Page components
│   │   ├── lib/            # Utilities
│   │   └── App.tsx         # Main app component
│   └── index.html          # HTML template
├── server/                 # Express backend
│   ├── index.ts            # Server entry point
│   ├── routes.ts           # API routes
│   └── storage.ts          # Data storage
├── shared/                 # Shared types
│   └── schema.ts           # Data schemas
├── package.json            # Dependencies
└── README-WINDOWS.md       # This file
```

## Available Scripts

- `npm run dev` - Start development server (frontend + backend)
- `npm run build` - Build for production
- `npm run preview` - Preview production build

## Features

- ✅ React with TypeScript
- ✅ Express.js backend
- ✅ Mobile-responsive design
- ✅ Dark/light theme toggle
- ✅ Interactive country explorer
- ✅ Travel planning checklist
- ✅ Real-time search and filtering

## Troubleshooting

### Clear npm cache
```bash
npm cache clean --force
```

### Reinstall dependencies
```bash
rmdir /s node_modules
del package-lock.json
npm install
```

### Check firewall/antivirus
Some antivirus software may block the development server. Add an exception for Node.js if needed.

## Getting Help

If you encounter issues:
1. Check this README
2. Ensure Node.js version 18+ is installed
3. Try running commands in a new terminal window
4. Check if any antivirus is blocking the application

## Development Tips

- The app uses hot reloading - changes are reflected automatically
- Backend API is available at `/api/*` routes
- Frontend runs on the same port as backend
- All modern browsers are supported
- Mobile-responsive design works on all screen sizes

Happy coding! 🚀