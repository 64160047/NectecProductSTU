<template>
  <section class="w-full min-h-screen bg-gradient-to-br from-[#97B8FF] via-[#B0B1FF] to-[#80FFDA]  min-h-screen text-center py-16">
    <!-- 🔹 ปุ่มย้อนกลับ -->
    <div class="absolute top-6 left-6">
      <router-link to="/" 
        class="px-6 py-3 text-lg font-semibold bg-purple-600 text-white rounded-full shadow-md hover:bg-purple-700 transition duration-300 flex items-center">
        ← Back
      </router-link>
    </div>

    <!-- 🔹 หัวข้อ -->
    <h2 class="text-5xl font-extrabold text-purple-900 mb-12 font-playfair tracking-wide">
      All Products
    </h2>

    <!-- 🔹 Grid แสดงสินค้า -->
    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-14 px-12 max-w-8xl mx-auto">
      <div v-for="product in products" :key="product.name"
        class="bg-white rounded-3xl shadow-lg flex flex-col items-center p-8 h-[540px] transition duration-300 transform hover:scale-105">
        
        <!-- ✅ รูปสินค้า (ขยายให้สมดุล) -->
        <div class="w-[90%] h-[55%] flex items-center justify-center overflow-hidden rounded-t-3xl">
          <img :src="product.image" :alt="product.name" 
               class="w-full h-full object-cover transition duration-500 hover:scale-110">
        </div>

        <!-- ✅ ข้อมูลสินค้า (เพิ่มขนาดฟอนต์ + จัดวางให้ดูดีขึ้น) -->
        <div class="p-6 flex flex-col items-center justify-center h-[45%]">
          <h3 class="text-3xl font-semibold text-purple-700 font-poppins">{{ product.name }}</h3>
          <p class="text-gray-600 text-lg mt-2 text-center leading-relaxed">
            {{ product.description }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import PathummaImage from '@/assets/images/Pathumma.png';

const products = [
  { name: "Patthumma LLM", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec varius, risus eget aliquet tristique, orci eros convallis libero." },
  { name: "Abdul GI", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec varius, risus eget aliquet tristique, orci eros convallis libero." },
  { name: "Sontana", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec varius, risus eget aliquet tristique, orci eros convallis libero." },
  { name: "Party", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec varius, risus eget aliquet tristique, orci eros convallis libero." },
  { name: "Chatbot Arena", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec varius, risus eget aliquet tristique, orci eros convallis libero." },
  { name: "DocChat", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec varius, risus eget aliquet tristique, orci eros convallis libero." },
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