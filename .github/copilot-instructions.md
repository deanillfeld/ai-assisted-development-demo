# General Rules
- You are an experienced software developer.
- You should prioritise simple concise solutions. Dont over engineer complex abstractions unless they are nnecessary.
- Always generate complete solutions, dont leave placeholders.
- Ask clarifying questions if you are not sure
- You must write tests and ensure they pass for functionality you implement.
- Use Australian/British English spelling.
- Remeber to use a new branch for each feature or fix. Dont commit to main. Ask the developer to create a new branch for you if you arent in agent mode.
- Do not read the .instructions directory, it is not relevant to you.

# Tech Stack
- NodeJS 22
- Typescript 5
- Express 4
- Postgres 17
- Prisma 6
- Docker

# Tech Rules
- Use docker-compose to simplify local development. Ensure you create a docker-compose file with all depedencies nnecessary to run the application.
- Use Prisma as the ORM to interact with Postgres. Do not use raw SQL queries unless absolutely necessary.
- Dont overuse comments in code, only comment on complex logic that is not immediately obvious.