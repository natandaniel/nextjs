## Next.js Dashboard Application

This is a modern dashboard application built with Next.js App Router, featuring a robust and scalable architecture.

### Key Features

- **Modern Framework**: Built with Next.js (Latest) using the App Router architecture
- **Type Safety**: Full TypeScript implementation with Zod for runtime validation
- **Authentication**: Secure authentication using NextAuth.js v5
- **Database**: PostgreSQL for reliable data storage
- **Styling**: Modern UI with Tailwind CSS and PostCSS
- **Development**: Fast development experience with Turbopack

### Project Structure

```
nextjs-dashboard/
├── app/                    # Main application code
│   ├── ui/                # Reusable UI components
│   ├── lib/               # Utility functions
│   ├── query/             # Data fetching and API logic
│   └── seed/              # Database seeding scripts
├── docs/                  # Documentation
│   ├── fonts.md          # Font system documentation
│   ├── images.md         # Image optimization documentation
│   └── imports.md        # JavaScript/TypeScript import syntax guide
├── public/                # Static assets
└── [Configuration Files]  # TypeScript, Tailwind, Next.js configs
```

### Documentation

- [Font System Guide](docs/fonts.md) - Learn about Next.js font optimization and usage
- [Image Optimization Guide](docs/images.md) - Learn about Next.js image optimization and best practices
- [Import Syntax Guide](docs/imports.md) - Understand JavaScript/TypeScript import patterns in Next.js

### Technology Stack

- **Frontend**: React, Next.js, TypeScript
- **Styling**: Tailwind CSS, PostCSS
- **Authentication**: NextAuth.js
- **Database**: PostgreSQL
- **Package Manager**: PNPM
- **Development Tools**: Turbopack, TypeScript
- **UI Components**: Heroicons
- **Form Handling**: @tailwindcss/forms

### Getting Started

1. Clone the repository
2. Install dependencies: `pnpm i`
3. Set up environment variables (see `.env.example`)
4. Run development server: `pnpm dev`
5. Build for production: `pnpm build`

For more information about the Next.js App Router, see the [course curriculum](https://nextjs.org/learn) on the Next.js Website.
