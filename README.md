
# PaySwift

PaySwift is a monorepo for a payment platform inspired by Paytm, built with Next.js, TypeScript, and Prisma. It is organized for scalability and maintainability, with separate apps for merchants and users, and shared packages for UI, database, and configuration.

## Project Structure

```
PaySwift/
├── apps/
│   ├── merchant-app/   # Next.js app for merchants
│   └── user-app/       # Next.js app for users
├── packages/
│   ├── db/             # Prisma schema and migrations
│   ├── eslint-config/  # Shared ESLint config
│   ├── typescript-config/ # Shared TypeScript config
│   └── ui/             # Shared React UI components
├── package.json        # Root config, scripts, and workspaces
├── turbo.json          # Turborepo configuration
└── README.md           # Project documentation
```

## How to Run Locally

1. **Install dependencies**
   ```sh
   npm install
   ```

2. **Set up the database**
   - Edit your database connection string in `packages/db/prisma/schema.prisma` if needed.
   - Run Prisma migrations:
     ```sh
     npx prisma migrate dev --schema=packages/db/prisma/schema.prisma
     ```

3. **Start development servers**
   ```sh
   npm run dev
   ```
   This will start both `merchant-app` and `user-app` locally.

## Apps

- **merchant-app**: Next.js app for merchant features and dashboard.
- **user-app**: Next.js app for user-facing features.

## Packages

- **db**: Prisma ORM setup, schema, and migrations.
- **eslint-config**: Shared ESLint rules.
- **typescript-config**: Shared TypeScript configuration.
- **ui**: Reusable React components for both apps.

## Development Notes

- All code is written in TypeScript.
- Shared logic and UI components are imported from the `ui` package.
- Database schema and migrations are managed with Prisma in the `db` package.

## License

MIT

### Build

To build all apps and packages, run the following command:

```
cd my-turborepo
pnpm build
```

### Develop

To develop all apps and packages, run the following command:

```
cd my-turborepo
pnpm dev
```

### Remote Caching

> [!TIP]
> Vercel Remote Cache is free for all plans. Get started today at [vercel.com](https://vercel.com/signup?/signup?utm_source=remote-cache-sdk&utm_campaign=free_remote_cache).

Turborepo can use a technique known as [Remote Caching](https://turborepo.com/docs/core-concepts/remote-caching) to share cache artifacts across machines, enabling you to share build caches with your team and CI/CD pipelines.

By default, Turborepo will cache locally. To enable Remote Caching you will need an account with Vercel. If you don't have an account you can [create one](https://vercel.com/signup?utm_source=turborepo-examples), then enter the following commands:

```
cd my-turborepo
npx turbo login
```

This will authenticate the Turborepo CLI with your [Vercel account](https://vercel.com/docs/concepts/personal-accounts/overview).

Next, you can link your Turborepo to your Remote Cache by running the following command from the root of your Turborepo:

```
npx turbo link
```

## Useful Links

Learn more about the power of Turborepo:

- [Tasks](https://turborepo.com/docs/crafting-your-repository/running-tasks)
- [Caching](https://turborepo.com/docs/crafting-your-repository/caching)
- [Remote Caching](https://turborepo.com/docs/core-concepts/remote-caching)
- [Filtering](https://turborepo.com/docs/crafting-your-repository/running-tasks#using-filters)
- [Configuration Options](https://turborepo.com/docs/reference/configuration)
- [CLI Usage](https://turborepo.com/docs/reference/command-line-reference)
