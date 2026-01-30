# 🚀 Codexi

**Codexi** is a modern, premium online code editor and problem-solving platform designed for developers who want to code in style. Featuring a stunning "Cyber Neon" aesthetic, it allows users to write, compile, and execute code in multiple languages, solve LeetCode-style problems, and track their progress.

**🔗 Live Frontend**: https://codexi.vercel.app/
**🔗 Live Backend**: https://codeeditor2.onrender.com

## ✨ Features

-   **🎨 Cyber Neon UI**: A fully responsive, dark-mode-first design with vibrant gradients, glassmorphism, and smooth animations.
-   **💻 Powerful Online Playground**:
    -   Powered by **Monaco Editor** (VS Code experience).
    -   Multi-language support (JavaScript, Python, C++, Java).
    -   Real-time code execution via **Piston API**.
    -   Split-screen "Problem Mode" for simultaneous reading and coding.
-   **🧩 Problem Solving**:
    -   Browse a curated list of algorithmic challenges.
    -   Filter by difficulty (Easy, Medium, Hard) and search by title.
    -   View detailed problem descriptions and examples.
-   **👤 User Profile & Progress**:
    -   Track your "victory count" (Solved Problems).
    -   View a history of all solved challenges.
    -   Customizable user profile (Avatar, Name, Username).
-   **🔐 Secure Authentication**: JWT-based auth with HttpOnly cookies for secure sessions.

## 🛠️ Tech Stack

### Frontend
-   **React** (Vite)
-   **Tailwind CSS** (Styling & Animations)
-   **Shadcn UI** & **Radix UI** (Components)
-   **Monaco Editor** (Code Editor)
-   **Axios** (API Requests)
-   **Lucide React** (Icons)

### Backend
-   **Node.js** & **Express**
-   **MongoDB** & **Mongoose** (Database)
-   **JWT** (Authentication)
-   **Bcrypt** (Password Hashing)
-   **Cloudinary** (Image Storage)

### External APIs
-   **Piston API**: For code execution.
-   **Alfa LeetCode API**: For fetching coding problems.

## 🚀 Getting Started

Follow these steps to set up the project locally.

### Prerequisites
-   Node.js (v16+)
-   MongoDB Atlas URI (or local MongoDB)

### Installation

1.  **Clone the repository**
    ```bash
    git clone https://github.com/Bhumit267/codexi.git
    cd codexi
    ```

2.  **Setup Backend**
    ```bash
    cd code_curator/backend
    npm install
    ```
    Create a `.env` file in `code_curator/backend/`:
    ```env
    PORT=3000
    MONGO_URI=your_mongodb_connection_string
    CORS_ORIGIN=http://localhost:5173
    ACCESS_TOKEN_SECRET=your_access_secret
    ACCESS_TOKEN_VALIDITY=1d
    REFRESH_TOKEN_SECRET=your_refresh_secret
    REFRESH_TOKEN_VALIDITY=10d
    CLOUDINARY_CLOUD_NAME=...
    CLOUDINARY_API_KEY=...
    CLOUDINARY_API_SECRET=...
    ```
    Start the server:
    ```bash
    npm run dev
    ```

3.  **Setup Frontend**
    ```bash
    cd ../frontend
    npm install
    ```
    Create a `.env` file in `frontend/`:
    ```env
    VITE_BASE_URL=http://localhost:3000
    ```
    Start the development server:
    ```bash
    npm run dev
    ```

4.  **Open in Browser**
    Visit `http://localhost:5173` to start coding!



## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is licensed under the MIT License.
