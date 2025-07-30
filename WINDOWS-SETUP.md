# GlobeTrek - Complete Windows Setup

## Quick Start Commands

1. **Install dependencies:**
```cmd
npm install
```

2. **Start development server:**
```cmd
npx cross-env NODE_ENV=development tsx server/index.ts
```

3. **Open in browser:**
```
http://localhost:5000
```

## Alternative Start Methods

**Method 1: Two commands**
```cmd
set NODE_ENV=development
npx tsx server/index.ts
```

**Method 2: PowerShell**
```powershell
$env:NODE_ENV="development"; npx tsx server/index.ts
```

## What You'll See
- Beautiful travel website with country cards
- Search and filter functionality
- Mobile-responsive design
- Dark/light theme toggle
- Interactive country details
- Travel checklist

## Troubleshooting
- Make sure Node.js 18+ is installed
- Use Command Prompt or PowerShell
- If port 5000 is busy, the app will show an error
- Restart terminal if commands don't work

## Project Features
- React + TypeScript frontend
- Express.js backend
- Tailwind CSS styling
- Mobile-first responsive design
- Real-time search and filtering
- Local storage for preferences