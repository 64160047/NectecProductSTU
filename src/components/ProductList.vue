<template>
    <section class="w-full min-h-screen bg-gradient-to-b from-blue-100 to-white text-center py-16">
      <!-- 🔹 หัวข้อ (เพิ่มระยะห่าง) -->
      <h2 class="text-6xl font-extrabold text-gray-900 mb-16 font-playfair tracking-wide">
        Products
      </h2>
  
      <!-- 🔹 Grid แสดงสินค้า -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-20 px-12 max-w-8xl mx-auto">
        <div v-for="product in products" :key="product.name"
          class="bg-white p-10 rounded-3xl shadow-2xl transform transition hover:scale-105 flex flex-col items-center h-[520px]">
          <img :src="product.image" :alt="product.name" class="w-44 h-44 object-contain">
          <h3 class="text-3xl font-semibold mt-6 text-gray-900 font-poppins">{{ product.name }}</h3>
          <p class="text-gray-600 text-lg mt-4">{{ product.description }}</p>
        </div>
      </div>
  
      <!-- 🔹 ปุ่ม All Product -->
      <div class="mt-16">
        <button class="px-12 py-5 text-xl font-semibold bg-purple-600 text-white rounded-full shadow-xl hover:bg-purple-700 transition">
          All Product
        </button>
      </div>
    </section>
  </template>
  
  <script setup>
  const products = [
    { name: "Patthumma LLM", image: "/path/to/image1.png", description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit." },
    { name: "Abdul GI", image: "/path/to/image2.png", description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit." },
    { name: "Sontana", image: "/path/to/image3.png", description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit." },
  ];
  </script>
  
  <!-- ✅ ใช้ Google Fonts + Tailwind -->
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Poppins:wght@500&display=swap');
  
  .font-playfair {
    font-family: 'Playfair Display', serif;
  }
  
  .font-poppins {
    font-family: 'Poppins', sans-serif;
  }
  </style>
  