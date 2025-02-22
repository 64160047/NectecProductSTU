<template>
  <div>
    <!-- ✅ แสดง Navbar -->
    <NavBar />

    <section id="products" class="animated-bg w-full min-h-screen text-center py-24 relative">
    

      <!-- 🔹 หัวข้อ -->
      <h2 class="text-5xl font-extrabold text-white mt-10 mb-12 font-playfair tracking-wide">
        All Products
      </h2>

      <!-- 🔹 Grid แสดงสินค้า -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-14 px-12 max-w-8xl mx-auto">
        <div v-for="product in products" :key="product.name"
          class="bg-white rounded-3xl shadow-lg flex flex-col items-center p-8 h-[540px] transition duration-300 transform hover:scale-105">

          <!-- ✅ รูปสินค้า -->
          <div class="w-[90%] h-[55%] flex items-center justify-center overflow-hidden rounded-t-3xl">
            <img :src="product.image" :alt="product.name"
              class="w-full h-full object-cover transition duration-500 hover:scale-110">
          </div>

          <!-- ✅ ข้อมูลสินค้า -->
          <div class="p-6 flex flex-col items-center justify-center h-[45%]">
            <h3 class="text-3xl font-semibold text-purple-700 font-poppins">{{ product.name }}</h3>
            <p class="text-gray-600 text-lg mt-2 text-center leading-relaxed">
              {{ product.description }}
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script setup>
import PathummaImage from '@/assets/images/Pathumma.png';
import NavBar from '@/components/NavBar.vue'; // ✅ นำเข้า Navbar

const products = [
  { name: "Patthumma LLM", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit." },
  { name: "Abdul GI", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit." },
  { name: "Sontana", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit." },
  { name: "Party", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit." },
  { name: "Chatbot Arena", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit." },
  { name: "DocChat", image: PathummaImage, description: "Lorem ipsum dolor sit amet, consectetur adipiscing elit." },
];
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Poppins:wght@500&display=swap');

.font-playfair {
  font-family: 'Playfair Display', serif;
}

.font-poppins {
  font-family: 'Poppins', sans-serif;
}

.animated-bg {
  background: radial-gradient(circle at 20% 30%, rgba(52, 80, 200, 0.3), transparent),
              radial-gradient(circle at 80% 70%, rgba(255, 255, 255, 0.1), transparent),
              linear-gradient(-45deg, #1282d2, #110636, #580cae, #4e74ff);
  background-size: 400% 400%;
  animation: gradientMove 10s ease infinite;
}

/* ✅ Animation ให้ Gradient เคลื่อนที่ */
@keyframes gradientMove {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

/* ✅ เอฟเฟกต์แสงแบบ Soft Glow */
@keyframes glowingLight {
  0% { opacity: 0.2; transform: scale(1); }
  50% { opacity: 0.7; transform: scale(1.3); }
  100% { opacity: 0.2; transform: scale(1); }
}

.glowing-light {
  position: absolute;
  width: 150px;
  height: 150px;
  background: radial-gradient(circle, rgba(0, 153, 255, 0.4), transparent);
  border-radius: 50%;
  animation: glowingLight 5s infinite alternate;
  filter: blur(25px);
}



</style>




