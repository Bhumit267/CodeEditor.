# 🚀 Deployment Guide: CodeYourWay (Codexi)

This guide walks you through deploying your full-stack application to production.

## Part 1: Deploy Backend to Render ☁️

Render will host your Node.js server and connect it to your database.

1.  **Create an Account**: Go to [render.com](https://render.com/) and sign up / log in with GitHub.
2.  **Create Web Service**:
    *   Click the **New +** button in the dashboard.
    *   Select **Web Service**.
3.  **Connect Repository**:
    *   Find your repo `CodeEditor` (or whatever you named it) in the list.
    *   Click **Connect**.
4.  **Configure Service**:
    *   **Name**: `codexi-backend` (or similar).
    *   **Region**: Choose the one closest to you (e.g., Singapore, Frankfurt).
    *   **Branch**: `main`.
    *   **Root Directory**: `code_curator/backend` (⚠️ Important: Do not leave blank).
    *   **Runtime**: `Node`.
    *   **Build Command**: `npm install`.
    *   **Start Command**: `npm start`.
    *   **Instance Type**: `Free`.
5.  **Environment Variables**:
    *   Scroll down to "Environment Variables".
    *   Click **Add Environment Variable** for each key in your backend `.env` file:
        *   `MONGO_URI`: Your MongoDB connection string.
        *   `ACCESS_TOKEN_SECRET`: Your secret.
        *   `REFRESH_TOKEN_SECRET`: Your secret.
        *   `CLOUDINARY_CLOUD_NAME`: Your Cloudinary name.
        *   `CLOUDINARY_API_KEY`: Your key.
        *   `CLOUDINARY_API_SECRET`: Your secret.
        *   `CORS_ORIGIN`: `*` (We will change this later).
6.  **Deploy**:
    *   Click **Create Web Service**.
    *   Wait for the logs to show "Server running on port...".
    *   **Copy the URL** from the top left (e.g., `https://codexi-backend.onrender.com`).

---

## Part 2: Deploy Frontend to Vercel ▲

Vercel will host your React frontend and serve it to the world.

1.  **Create an Account**: Go to [vercel.com](https://vercel.com/) and log in with GitHub.
2.  **Add New Project**:
    *   Click **Add New...** -> **Project**.
    *   Import your `CodeEditor` repository.
3.  **Configure Project**:
    *   **Project Name**: `codexi` (or similar).
    *   **Framework Preset**: `Vite` (should auto-detect).
    *   **Root Directory**:
        *   Click **Edit** next to Root Directory.
        *   Select `code_curator/frontend`.
4.  **Environment Variables**:
    *   Expand the "Environment Variables" section.
    *   Add:
        *   **Key**: `VITE_BASE_URL`
        *   **Value**: The **Render Backend URL** you copied (e.g., `https://codexi-backend.onrender.com`).
5.  **Deploy**:
    *   Click **Deploy**.
    *   Wait for the confetti! 🎉
    *   **Copy your new Frontend URL** (e.g., `https://codexi.vercel.app`).

---

## Part 3: Secure the Connection 🔒

Now that you have the Frontend URL, let's lock down the Backend.

1.  Go back to your **Render Dashboard**.
2.  Select your backend service.
3.  Go to **Environment**.
4.  Edit `CORS_ORIGIN`.
5.  Set the value to your **Vercel Frontend URL** (no trailing slash, e.g., `https://codexi.vercel.app`).
6.  Save Changes. Render will restart the server.

**Done! Your app is live!** 🚀
