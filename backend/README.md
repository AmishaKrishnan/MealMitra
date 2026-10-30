# MealMitra backend

## Run locally

1. Copy `.env.example` to `.env`.
2. Set `JWT_SECRET` and add a Gemini API key as `GEMINI_API_KEY`. Create a key in [Google AI Studio](https://aistudio.google.com/apikey).
3. Make sure MongoDB is running.
4. Run `npm install` and `npm start`.

The NGO support assistant uses the Gemini API from the backend. Keep the API key in this backend `.env` file; never add it to frontend code or commit it.
