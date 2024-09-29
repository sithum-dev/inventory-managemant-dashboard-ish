# Database Seeding with Prisma

This guide explains how to seed the database for your Node.js backend project using Prisma. It covers seeding the database with sample data to prepare it for development.

## Seed Data

The seed data is stored in JSON files located in the `server/prisma/seedData/` directory. For example, the `products.json` file contains a list of products:

```json
[
  {
    "productId": "d35623ee-bef6-42b2-8776-2f99f8bb4782",
    "name": "Pinkscale Blazing Star",
    "price": 456.04,
    "rating": 2.25,
    "stockQuantity": 124834
  },
  {
    "productId": "8ac1ac77-7358-425e-be16-0bdde9f02e59",
    "name": "Gila Milkvetch",
    "price": 899.05,
    "rating": 3.56,
    "stockQuantity": 799402
  }
]
```

Additional data files exist for other models (e.g., `users.json`, `sales.json`).

## Seed Script

The seeding process is defined in the `server/prisma/seed.ts` file. This script:

1. Deletes existing data from the database.
2. Loads the seed data from the JSON files.
3. Populates the database with this data.

The script automatically matches JSON files with their corresponding Prisma models by their file names.

## Running the Seed Process

To seed the database, follow these steps:

1. **Install Dependencies**:
   Ensure you have Prisma and other dependencies installed by running:

   ```bash
   npm install
   ```

2. **Generate Prisma Client**:
   Generate the Prisma client by running:

   ```bash
   npx prisma generate
   ```

3. **Run Migrations**:
   Set up the database schema by running the Prisma migrations:

   ```bash
   npx prisma migrate dev --name init
   ```

4. **Run the Seed Script**:
   Finally, run the seed script to populate the database with the seed data:
   ```bash
   npm run seed
   ```

## Example for New Developers

For new developers, follow these steps to set up the project:

1. Clone the repository and navigate to the project folder.
2. Install the required dependencies using `npm install`.
3. Create a new `.env` file in the root of your project based on the `.env.example` file. This should include your database connection details.
4. Run `npx prisma generate` to generate the Prisma client.
5. Run the migrations with `npx prisma migrate dev --name init` to set up the database schema.
6. Run the seeding script using `npm run seed` to populate the database with initial data.

That's it! Your local database should now be seeded with the necessary data.
