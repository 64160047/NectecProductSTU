<template>
  <div>
    <!-- ✅ แสดง Navbar -->
    <NavBar />

    <section id="products" class="animated-bg w-full min-h-screen text-center py-24 relative">
      <!-- 🔹 หัวข้อ -->
      <h2 class="text-6xl font-extrabold text-white mt-10 mb-12 font-playfair tracking-wide">
        All Products
      </h2>

      <div class="flex justify-start px-12 mb-10">
  <div class="relative w-80">
    <select v-model="selectedCategory"
      class="w-full px-6 py-4 text-xl text-gray-900 bg-white border-2 border-gray-300 rounded-2xl shadow-lg
             focus:outline-none focus:ring-4 focus:ring-purple-500 focus:border-purple-500 
             transition duration-300 hover:border-purple-400 appearance-none pr-10">
      <option value="All Product" class="bg-white text-lg text-gray-900"> All Products 📌</option>
      <option value="Speech" class="bg-white text-lg text-gray-900"> Speech 🗣️ </option>
      <option value="Text" class="bg-white text-lg text-gray-900">Text 📝 </option>
      <option value="TextVoice" class="bg-white text-lg text-gray-900"> Speech and Text 🗣️ 📝 </option>
    </select>

  </div>
</div>




      <!-- 🔹 Grid แสดงสินค้า (เพิ่มระยะห่าง) -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-12 px-12 max-w-8xl mx-auto">
        <a v-for="product in filteredProducts" :key="product.name" :href="product.link" target="_blank"
          rel="noopener noreferrer" class="bg-white text-black rounded-3xl border-2 border-gray-300 shadow-lg
                 flex flex-col items-center p-6 h-[520px] transition-all duration-300 transform 
                 hover:scale-105 hover:shadow-xl hover:shadow-purple-400 cursor-pointer">

          <!-- ✅ รูปสินค้า (ขอบมน 4 ด้าน) -->
          <div class="w-[90%] h-[60%] flex items-center justify-center overflow-hidden rounded-2xl">
            <img :src="product.image" :alt="product.name"
              class="w-full h-full object-cover transition duration-500 hover:scale-110 rounded-2xl">
          </div>

          <!-- ✅ ข้อมูลสินค้า -->
          <div class="p-6 flex flex-col items-center text-center h-[40%]">
            <h3 class="text-4xl font-extrabold text-purple-700 font-sans mb-3">
              {{ product.name }}
            </h3>
            <p class="text-gray-700 text-xl leading-relaxed">
              {{ product.description }}
            </p>
          </div>

        </a>
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
import PathummaImage from '@/assets/images/Pathumma.png';
import AbdulImage from '@/assets/images/Abdul.png';
import PartiiImage from '@/assets/images/Partii.png';
import CopyCatchImage from '@/assets/images/CopyCath.png';
import SsenseImage from '@/assets/images/Ssense.png';
import SontanaImage from '@/assets/images/Sontana.png';
import VajaImage from '@/assets/images/Vaja.png';
import NavBar from '@/components/NavBar.vue';

// ✅ กำหนดค่าหมวดหมู่ที่เลือก
const selectedCategory = ref("All Product");

// ✅ สินค้าแต่ละตัวมี `category`
const products = [
  { name: "Patthumma LLM", image: PathummaImage, description: "ระบบ AI ที่สามารถตอบคำถาม ให้คำปรึกษา และแนะนำข้อมูล", link: "https://aiforthai.in.th/pathumma-llm/", category: "Text" },
  { name: "ABDUL Chatbot Platform", image: AbdulImage, description: "แพลตฟอร์มสำหรับสร้างแชทบอท", link: "https://abdul.ai", category: "Text" },
  { name: "CopyCatch", image: CopyCatchImage, description: "ระบบตรวจสอบการคัดลอกเอกสารอัตโนมัติ", link: "https://www.copycatch.in.th", category: "Text" },
  { name: "SSENSE", image: SsenseImage, description: "ระบบวิเคราะห์ความคิดเห็นของข้อความภาษาไทย", link: "https://aiforthai.in.th/service_sa.php", category: "Text" },
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
</style>
