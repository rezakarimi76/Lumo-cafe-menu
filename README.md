# Lumo-cafe-menu
<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>منوی دیجیتال لومو کافه</title>
</head>
<body>
    <div id="root"></div>
</body>
</html>
import React from "react";
import ReactDOM from "react-dom/client";
import App from "./App";
import "./index.css";

ReactDOM.createRoot(document.getElementById("root")).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
@tailwind base;
@tailwind components;
@tailwind utilities;

body {
  font-family: 'Vazir', sans-serif;
  background-color: #fefcf9;
}
import React, { useState } from "react";

const menuData = [
  {
    category: "نوشیدنی‌ها",
    items: [
      { name: "قهوه کلد برو", price: "45,000 تومان", img: "coldbrew.jpg", desc: "خنک و خوش‌طعم" },
      { name: "لاته کلاسیک", price: "35,000 تومان", img: "latte.jpg", desc: "با اسپرسو تازه" },
    ],
  },
  {
    category: "میان‌وعده‌ها",
    items: [
      { name: "وافل شکلاتی", price: "25,000 تومان", img: "waffle.jpg", desc: "نرم و خوشمزه" },
      { name: "پنکیک میوه‌ای", price: "28,000 تومان", img: "pancake.jpg", desc: "با توت تازه" },
    ],
  },
  {
    category: "دسرها",
    items: [
      { name: "کیک روز", price: "30,000 تومان", img: "cake.jpg", desc: "تازه و لذیذ" },
    ],
  },
];

export default function App() {
  const [category, setCategory] = useState(menuData[0].category);

  const currentItems = menuData.find(cat => cat.category === category).items;

  return (
    <div className="p-4 max-w-3xl mx-auto">
      <h1 className="text-3xl font-bold mb-4 text-center">منوی دیجیتال لومو کافه</h1>

      <div className="flex justify-center gap-4 mb-6">
        {menuData.map(cat => (
          <button
            key={cat.category}
            className={`px-4 py-2 rounded ${category === cat.category ? 'bg-orange-500 text-white' : 'bg-gray-200'}`}
            onClick={() => setCategory(cat.category)}
          >
            {cat.category}
          </button>
        ))}
      </div>

      <div className="grid grid-cols-1 sm:grid-cols-2 gap-6">
        {currentItems.map(item => (
          <div key={item.name} className="border rounded-lg p-4 bg-white shadow hover:shadow-lg transition">
            <img src={`/images/${item.img}`} alt={item.name} className="w-full h-40 object-cover rounded mb-2"/>
            <h2 className="font-semibold text-lg">{item.name}</h2>
            <p className="text-orange-600 font-bold">{item.price}</p>
            <p className="text-gray-600 text-sm">{item.desc}</p>
          </div>
        ))}
      </div>
    </div>
  );
}
{
  "name": "lumo-cafe-menu",
  "version": "1.0.0",
  "private": true,
  "scripts": {
    "dev": "vite",
    "build": "vite build",
    "preview": "vite preview"
  },
  "dependencies": {
    "react": "^18.2.0",
    "react-dom": "^18.2.0"
  },
  "devDependencies": {
    "vite": "^4.3.0",
    "tailwindcss": "^3.3.2",
    "postcss": "^8.4.24",
    "autoprefixer": "^10.4.14"
  }
}
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}"
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}
lumo-cafe-menu/public/images
