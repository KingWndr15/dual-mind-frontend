# Dual Mind Chat Frontend

This is a Vue.js frontend application that allows users to send messages to an AI model and select their preferred response style. The app communicates with an Express API backend to generate responses using Google's Gemini model.

## Features

- Allows users to type a message and select a response style (e.g., friendly, formal, informative).
- Sends the message and style to the backend API and displays the AI-generated response.

## Prerequisites

- [Node.js](https://nodejs.org/) (v14 or higher)
- Vue CLI installed globally (`npm install -g @vue/cli`)

## Installation

1. Clone the repository and navigate to the `frontend` directory.

   ```bash
   git clone https://github.com/KingWndr15/dual-mind-frontend
   cd gemini-frontend
   ```

2. Install dependencies.

   ```bash
   npm install
   ```

3. Update the `API_URL` in `MessageForm.vue` if necessary. By default, it's set to `http://localhost:3000/api/v1/respond`.

## Usage

1. Start the development server.

   ```bash
   npm run serve
   ```

2. Open your browser and navigate to `http://localhost:5173` to view the app.

## File Structure

- `App.vue`: Main app component.
- `components/MessageForm.vue`: Component with input for message, style selection, and response display.

## Customize

You can add more styles to the response dropdown by modifying the options in the `<select>` dropdown in `MessageForm.vue`.

---

