<template>
  <div>
    <!-- ✅ แสดง Navbar -->
    <NavBar />

    <section id="products" class="animated-bg w-full min-h-screen text-center py-24 relative">
      <!-- 🔹 หัวข้อ -->
      <h2 class="text-6xl font-extrabold text-white mt-10 mb-12 font-playfair tracking-wide">
        All Products
      </h2>

      <!-- 🔹 Grid แสดงสินค้า (เพิ่มระยะห่าง) -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-12 px-12 max-w-8xl mx-auto">
        <a v-for="product in products" :key="product.name" :href="product.link" target="_blank" rel="noopener noreferrer"
          class="bg-white text-black rounded-3xl border-2 border-gray-300 shadow-lg
                 flex flex-col items-center p-6 h-[520px] transition-all duration-300 transform 
                 hover:scale-105 hover:shadow-xl hover:shadow-purple-400 cursor-pointer">

          <!-- ✅ รูปสินค้า (ขอบมน 4 ด้าน) -->
          <div class="w-[90%] h-[60%] flex items-center justify-center overflow-hidden rounded-2xl">
            <img :src="product.image" :alt="product.name"
              class="w-full h-full object-cover transition duration-500 hover:scale-110 rounded-2xl">
          </div>

          <!-- ✅ ข้อมูลสินค้า -->
          <div class="p-6 flex flex-col items-center text-center h-[40%]">
            <!-- ✅ ชื่อสินค้า (ใหญ่ขึ้น & สีเด่นขึ้น) -->
            <h3 class="text-4xl font-extrabold text-purple-700 font-sans mb-3">
              {{ product.name }}
            </h3>

            <!-- ✅ คำอธิบายสินค้า (ขนาดใหญ่ขึ้น & อ่านง่ายขึ้น) -->
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
import PathummaImage from '@/assets/images/Pathumma.png';
import AbdulImage from '@/assets/images/Abdul.png';
import PartiiImage from '@/assets/images/Partii.png';
import CopyCatchImage from '@/assets/images/CopyCath.png';
import SsenseImage from '@/assets/images/Ssense.png';
import SontanaImage from '@/assets/images/Sontana.png';
import VajaImage from '@/assets/images/Vaja.png';
import NavBar from '@/components/NavBar.vue'; // ✅ นำเข้า Navbar

const products = [
  { name: "Patthumma LLM", image: PathummaImage, description: "ระบบ AI ที่สามารถตอบคำถาม ให้คำปรึกษา และแนะนำข้อมูลในรูปแบบข้อความหรือการสนทนา", link: "https://aiforthai.in.th/pathumma-llm/" },
  { name: "ABDUL Chatbot Platform", image: AbdulImage, description: "แพลตฟอร์มสำหรับสร้างแชทบอท", link: "https://abdul.ai" },
  { name: "CopyCatch", image: CopyCatchImage, description: "ระบบตรวจสอบการคัดลอกเอกสารอัตโนมัติ", link: "https://www.copycatch.in.th" },
  { name: "SSENSE", image: SsenseImage, description: "ระบบวิเคราะห์ความคิดเห็นของข้อความภาษาไทย", link: "https://aiforthai.in.th/service_sa.php" },
  { name: "Sontana", image: SontanaImage, description: "อวทาร์ให้บริการตอบคำถามแบบอัตโนมัติ พร้อมสีหน้าและน้ำเสียงที่สุภาพ", link: "https://example.com/sontana" },
  { name: "Partii", image: PartiiImage, description: "ระบบแปลงเสียงพูดให้เป็นข้อความภาษาไทย", link: "https://aiforthai.in.th/service_st.php" },
  { name: "Vaja", image: VajaImage, description: "ซอฟต์แวร์แปลงข้อความเป็นเสียงพูด รองรับทั้งภาษาไทยและอังกฤษ", link: "https://aiforthai.in.th/service_ts.php" },
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

/* ✅ พื้นหลัง Gradient */
.animated-bg {
  background: linear-gradient(to bottom, #1A1043, #311B92, #512DA8);
}
</style>
