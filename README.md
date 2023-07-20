This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

## Download env from vercel

```bash
vercel env pull .env
```

## Prisma

```bash
npm install prisma --save-dev
npx prisma init

# Once the schema is created in prisma/schema.prisma, run the following command to create the database tables:
npx prisma db push

# create a postinstall script  with the content:
echo '{
  "scripts" {
    "postinstall": "prisma generate"
  }
}' > postinstall

# change the package.json file to include the postinstall script:
# "build": "prisma generate && next build"

# To open the Prisma Studio, run the following command:
npx prisma studio

# To install the Prisma Client, run the following command:
npm install @prisma/client

# Locally every time you change the schema, you need to run the following command:
# To generate the Prisma Client, run the following command:
npx prisma generate

# You'll use a single PrismaClient instance that you can import into any file where it's needed. The instance will be created in a prisma.ts file inside the lib/ directory
mkdir lib
touch lib/prisma.ts
```

## Next Auth

```bash
npm install next-auth@4 @next-auth/prisma-adapter

# After adding the new schema run:
npx prisma db push
```

## GitHub authentication

Create a OAuth App in GitHub

Set the callback URL to <http://localhost:3000/api/auth> for now, when in production another setting will be needed

### Add the following environment variables to Vercel Environment Variables

GITHUB_ID=<>
GITHUB_SECRET=<>
NEXTAUTH_URL=<http://localhost:3000/api/auth>

Run the following command to download the environment variables from Vercel:

```bash
vercel env pull .env
```
