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
          class="bg-white text-black rounded-3xl border-2 border-gray-300 shadow-lg shadow-gray-500
                 flex flex-col items-center p-8 h-[560px] transition duration-300 transform hover:scale-105 
                 hover:shadow-xl hover:shadow-purple-400">

          <!-- ✅ รูปสินค้า -->
          <div class="w-[90%] h-[50%] flex items-center justify-center overflow-hidden rounded-t-3xl">
            <img :src="product.image" :alt="product.name"
              class="w-full h-full object-cover transition duration-500 hover:scale-110">
          </div>

          <!-- ✅ ข้อมูลสินค้า -->
          <div class="p-6 flex flex-col items-center justify-center h-[50%]">
            <h3 class="text-3xl font-semibold text-purple-600 font-poppins text-center min-h-[50px]">
              {{ product.name }}
            </h3>
            <p class="text-gray-700 text-xl mt-3 text-center leading-relaxed min-h-[90px]">
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
  { name: "Patthumma LLM", image: PathummaImage, description: "นวัตกรรมการสื่อสารที่สามารถตอบคำถาม ให้คำปรึกษา แนะนำข้อมูล และให้บริการต่างๆ ในรูปแบบของข้อความหรือการสนทนา  " },
  { name: "ABDUL Chatbot Platform", image: PathummaImage, description: "แพลตฟอร์มสำหรับสร้างแชทบอท" },
  { name: "CopyCatch", image: PathummaImage, description: "ระบบตรวจสอบการคัดลอกและลอกเลียนเอกสารอิเล็กทรอนิกส์แบบอัตโนมัติ " },
  { name: "SSENSE", image: PathummaImage, description: "ระบบวิเคราะห์ความคิดเห็นข้อความภาษาไทย โดยวิเคราะห์ในเชิงจุดประสงค์ของข้อความ" },
  { name: "Sontana", image: PathummaImage, description: "อวทาร์ให้บริการตอบคำถามแบบอัตโนมัติ โดยตอบ FAQ ด้วยสีหน้า ท่าทาง และน้ำเสียงที่สุภาพ  " },
  { name: "DocChat", image: PathummaImage, description: "เทคโนโลยีปัญญาประดิษฐ์สรุปสาระสำคัญของเอกสาร ที่ผู้ใช้งานสามารถพูดคุยตอบโต้หรือตั้งคำถามเกี่ยวกับเอกสารได้ " },
  { name: "Partii", image: PathummaImage, description: "ระบบแปลงเสียงพูดให้เป็นข้อความภาษาไทย โดยปัจจุบันมี 2 รูปแบบ คือ Partii Enterprise และ Partii2go " },
  { name: "Vaja", image: PathummaImage, description: "ซอฟต์แวร์ที่แปลงข้อความภาษาไทย/อังกฤษเป็นเสียงพูดได้ทั้งภาษาไทยและภาษาอังกฤษ ที่มีคุณภาพเสียงใกล้เคียงกับมนุษย์" },
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
