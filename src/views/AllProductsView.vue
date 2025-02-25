<template>
  <div>
    <!-- ✅ แสดง Navbar -->
    <NavBar />

    <section id="products" class="animated-bg w-full min-h-screen text-center pt-24 pb-16 relative">
      <!-- 🔹 รูปพื้นหลัง -->
      <div class="absolute inset-0 bg-cover bg-center opacity-50 z-0 mix-blend-overlay"
        style="background-image: url('/src/assets/images/stars-1845852_1920.jpg')"></div>

      <!-- 🔹 หัวข้อและ Filter -->
      <div class="relative flex flex-col md:flex-row items-center px-12 mb-12 mt-12 w-full">
        <!-- ✅ หัวข้อ All Products (อยู่ตรงกลาง) -->
        <h2 class="absolute left-1/2 transform -translate-x-1/2 text-5xl md:text-6xl font-extrabold text-transparent bg-clip-text 
         bg-gradient-to-r from-purple-400 via-pink-500 to-yellow-500 animate-glow tracking-wider w-max text-center mb-5 ">
          All Products
        </h2>

        <!-- ✅ Select Filter (อยู่ขวาในจอใหญ่ & ใต้หัวข้อในจอเล็ก) -->
        <div class="relative w-full md:w-auto md:ml-auto mt-10 md:mt-0">
          <select v-model="selectedCategory" class="w-full md:w-80 px-6 py-4 text-lg text-gray-900 bg-white border-2 border-gray-300 rounded-3xl shadow-lg
       focus:outline-none focus:ring-4 focus:ring-purple-500 focus:border-purple-500 
       transition duration-300 hover:border-purple-400 appearance-none pr-8">
            <option value="All Product">All Products 📌</option>
            <option value="Speech">Speech 🗣️</option>
            <option value="Text">Text 📝</option>
            <option value="TextVoice">Speech and Text 🗣️📝</option>
          </select>
        </div>
      </div>

      <!-- 🔹 Grid แสดงสินค้า (การ์ดใหญ่ขึ้น) -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 px-4 md:px-8 max-w-8xl mx-auto">
        <a v-for="product in filteredProducts" :key="product.name" :href="product.link" target="_blank"
          rel="noopener noreferrer" class="bg-white/10 border text-black rounded-3xl shadow-lg max-w-lg w-full mx-auto flex flex-col p-8 h-[500px] md:h-[600px] transition-all duration-500 transform 
                 hover:scale-105 hover:shadow-xl hover:shadow-blue-400 cursor-pointer">

          <!-- ✅ รูปสินค้า (ใหญ่ขึ้น + responsive) -->
          <div class="w-full h-80 md:h-96 flex items-center justify-center rounded-2xl overflow-hidden aspect-[4/3]">
            <img :src="product.image" :alt="product.name"
              class="w-full h-full object-contain rounded-2xl transition duration-500 hover:scale-110">
          </div>

          <!-- ✅ ข้อมูลสินค้า -->
          <div class="p-3 flex flex-col items-center text-center">
            <h3 class="text-2xl md:text-3xl text-purple-300 font-serif font-semibold mb-2">
              {{ product.name }}
            </h3>
            <p class="text-white text-xl md:text-2xl leading-snug">
              {{ product.description }}
            </p>
          </div>
        </a>
      </div>
    </section>

    <!-- ✅ ใช้ Footer Component -->
    <Footer />
  </div>
</template>










<script setup>
import { ref, computed } from 'vue';
import PathummaImage from '@/assets/images/Pathumma.png';
import AbdulImage from '@/assets/images/Abdul.png';
import PartiiImage from '@/assets/images/Partii.png';
import SsenseImage from '@/assets/images/Ssense.png';
import SontanaImage from '@/assets/images/Sontana.png';
import VajaImage from '@/assets/images/Vaja.png';
import CopyCatchOneImage from '@/assets/images/CopyCathone.png';
import SsenseTwoImage from '@/assets/images/SsenseTwo.png';
import NavBar from '@/components/NavBar.vue';
import Footer from '@/components/Footer.vue';

// ✅ กำหนดค่าหมวดหมู่ที่เลือก
const selectedCategory = ref("All Product");

// ✅ สินค้าแต่ละตัวมี `category`
const products = [
  { name: "Patthumma LLM", image: PathummaImage, description: "ระบบ AI ที่สามารถตอบคำถาม ให้คำปรึกษา และแนะนำข้อมูล", link: "https://aiforthai.in.th/pathumma-llm/", category: "Text" },
  { name: "Abdul Chatbot Platform", image: AbdulImage, description: "แพลตฟอร์มสำหรับสร้างแชทบอท", link: "https://aiforthai.in.th/service_cb.php", category: "Text" },
  { name: "CopyCatch", image: CopyCatchOneImage, description: "ระบบตรวจสอบการคัดลอกเอกสารอัตโนมัติ", link: "https://www.copycatch.in.th", category: "Text" },
  { name: "S-SENSE", image: SsenseTwoImage, description: "ระบบวิเคราะห์ความคิดเห็นของข้อความภาษาไทย", link: "https://aiforthai.in.th/service_sa.php", category: "Text" },
  { name: "Sontana", image: SontanaImage, description: "อวทาร์ให้บริการตอบคำถามแบบอัตโนมัติ พร้อมสีหน้าและน้ำเสียงที่สุภาพ", link: "https://example.com/sontana", category: "TextVoice" },
  { name: "Partii", image: PartiiImage, description: "ระบบแปลงเสียงพูดให้เป็นข้อความภาษาไทย", link: "https://aiforthai.in.th/service_st.php", category: "Speech" },
  { name: "Vaja", image: VajaImage, description: "ซอฟต์แวร์แปลงข้อความเป็นเสียงพูด รองรับทั้งภาษาไทยและอังกฤษ", link: "https://aiforthai.in.th/service_ts.php", category: "Speech" },
];

// ✅ ฟิลเตอร์ข้อมูลตามหมวดหมู่
const filteredProducts = computed(() => {
  if (selectedCategory.value === "All Product") {
    return products;
  } else {
    return products.filter(product => product.category === selectedCategory.value);
  }
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Poppins:wght@500&display=swap');

.font-playfair {
  font-family: 'Playfair Display', serif;
}

.font-poppins {
  font-family: 'Poppins', sans-serif;
}


/* ✅ พื้นหลัง Gradient */
.animated-bg {
  background: linear-gradient(to bottom, #1A1043, #311B92, #512DA8);
}

.bg-gradient-space {
  background: linear-gradient(to bottom, #13072E, #2E1065, #4C1D95);
}

@keyframes moveStars {
  0% {
    background-position: 50% 0%;
  }

  50% {
    background-position: 50% 10%;
  }

  /* ขยับขึ้น */
  100% {
    background-position: 50% 0%;
  }

  /* กลับลงมา */
}

.animated-bg {

  background-image: url('/src/assets/images/starpurple.png');
  background-size: cover;
  background-position: 50% 0%;
  animation: moveStars 10s ease-in-out infinite;
  /* เคลื่อนที่ขึ้น-ลง */
}



@keyframes glow {
  0% {
    text-shadow: 0 0 5px rgba(255, 255, 255, 0.3), 0 0 10px rgba(255, 255, 255, 0.2);
  }

  50% {
    text-shadow: 0 0 20px rgba(255, 255, 255, 0.6), 0 0 30px rgba(255, 0, 255, 0.3);
  }

  100% {
    text-shadow: 0 0 5px rgba(255, 255, 255, 0.3), 0 0 10px rgba(255, 255, 255, 0.2);
  }
}

@keyframes wave {

  0%,
  100% {
    transform: translateY(0);
  }

  50% {
    transform: translateY(-10px);
  }
}

.animate-glow {
  animation: glow 2s infinite alternate ease-in-out, wave 3s infinite ease-in-out;
}
</style>
