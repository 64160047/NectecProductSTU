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
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-10 px-12 max-w-8xl mx-auto">
        <div v-for="product in products" :key="product.name" class="bg-white text-black rounded-3xl border-2 border-gray-300 shadow-md shadow-gray-500
                 flex flex-col items-center p-6 h-[500px] transition duration-300 transform hover:scale-105 
                 hover:shadow-lg hover:shadow-purple-400">

          <!-- ✅ รูปสินค้า -->
          <div class="w-[90%] h-[100%] flex items-center justify-center overflow-hidden rounded-3xl">
            <img :src="product.image" :alt="product.name"
              class="w-full h-full object-cover transition duration-500 hover:scale-110 rounded-3xl">
          </div>

          <!-- ✅ ข้อมูลสินค้า -->
          <div class="p-6 flex flex-col items-center text-center h-[60%]">
            <!-- ✅ ชื่อสินค้า (ใหญ่ขึ้น & สีเด่นขึ้น) -->
            <h3 class="text-3xl font-extrabold text-purple-700 font-sans  mb-4 pt-5 ">
              {{ product.name }}
            </h3>

            <!-- ✅ คำอธิบายสินค้า (ขนาดใหญ่ขึ้น & อ่านง่ายขึ้น) -->
            <p class="text-gray-700 text-xl leading-relaxed line-clamp-2">
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
import AbdulImage from '@/assets/images/Abdul.png';
import PartiiImage from '@/assets/images/Partii.png';
import CopyCatchImage from '@/assets/images/CopyCath.png';
import SsenseImage from '@/assets/images/Ssense.png';
import SontanaImage from '@/assets/images/Sontana.png';
import VajaImage from '@/assets/images/Vaja.png';
import NavBar from '@/components/NavBar.vue'; // ✅ นำเข้า Navbar


const products = [
  { name: "Patthumma LLM", image: PathummaImage, description: "ระบบ AI ที่สามารถตอบคำถาม ให้คำปรึกษา และแนะนำข้อมูลในรูปแบบข้อความหรือการสนทนา" },
  { name: "ABDUL Chatbot Platform", image: AbdulImage, description: "แพลตฟอร์มสำหรับสร้างแชทบอท" },
  { name: "CopyCatch", image: CopyCatchImage, description: "ระบบตรวจสอบการคัดลอกเอกสารอัตโนมัติ" },
  { name: "SSENSE", image: SsenseImage, description: "ระบบวิเคราะห์ความคิดเห็นของข้อความภาษาไทย" },
  { name: "Sontana", image: SontanaImage, description: "อวทาร์ให้บริการตอบคำถามแบบอัตโนมัติ พร้อมสีหน้าและน้ำเสียงที่สุภาพ" },
  { name: "DocChat", image: PathummaImage, description: "AI ที่ช่วยสรุปสาระสำคัญของเอกสาร และตอบคำถามเกี่ยวกับเอกสารได้" },
  { name: "Partii", image: PartiiImage, description: "ระบบแปลงเสียงพูดให้เป็นข้อความภาษาไทย " },
  { name: "Vaja ", image: VajaImage, description: "ซอฟต์แวร์แปลงข้อความเป็นเสียงพูด รองรับทั้งภาษาไทยและอังกฤษ" },
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
