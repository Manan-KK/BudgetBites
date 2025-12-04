# BudgetBites
College Meal Planning

## Deploying to Render
- Create a Render PostgreSQL instance first. The service exposes `DATABASE_URL`, `DATABASE_INTERNAL_URL`, `PG*` variables automatically (the app will pick any of these), or set `POSTGRES_HOST/PORT/DB/USER/PASSWORD` yourself. If your database requires SSL, set `DB_SSL=true`.
- Create a Web Service from this repo. Use the default build command (`npm install`) and set the start command to `npm run render-start` for a production process (keeps `npm start` for local nodemon).
- Required environment: `SESSION_SECRET` (any random string), database variables above, and `SPOONACULAR_API_KEY` for live API calls (otherwise a dev key is used).
- Optional one-off job to import custom recipes after each deploy: set `CUSTOM_RECIPE_CSV` (e.g. `/opt/render/project/src/database/custom.csv`) and run `npm run import:custom`. Optional overrides: `CUSTOM_RECIPE_IMAGE_SOURCE`, `CUSTOM_RECIPE_IMAGE_DEST`, `CUSTOM_RECIPE_IMAGE_URL`, `CUSTOM_RECIPE_IMAGE_EXT`, `CUSTOM_RECIPE_ID_OFFSET`, `CUSTOM_RECIPE_DEFAULT_SERVINGS`, `CUSTOM_RECIPE_DRY_RUN=true`, `CUSTOM_RECIPE_FORCE=true`.
