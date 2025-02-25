<template>
    <section id="products"
        class="relative w-full min-h-screen bg-gradient-to-br from-[#2A1D72] via-[#2C327C] to-[#04C484] text-center py-16">

        <!-- 🔹 รูปพื้นหลัง -->
        <div class="absolute inset-0 bg-cover bg-center opacity-50 z-0 mix-blend-overlay"
            style="background-image: url('/src/assets/images/stars-1845852_1920.jpg')"></div>

        <!-- 🔹 หัวข้อ -->
        <h2 class="text-5xl font-extrabold text-white mb-12 font-playfair tracking-wide">
            Products
        </h2>

        <!-- 🔹 Grid แสดงสินค้า -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8 px-6 md:px-12 max-w-8xl mx-auto">
            <div v-for="product in products" :key="product.name" @click="goToWebsite(product.link)"
                class="bg-black/30 border border-white/10 rounded-3xl shadow-lg transform transition hover:scale-105 
                      flex flex-col w-full max-w-[500px] h-[550px] mx-auto overflow-hidden p-6 cursor-pointer hover:shadow-purple-400">

                <!-- ✅ รูปภาพ (เว้นระยะห่างไม่ให้ติดขอบ) -->
                <div class="w-full h-[250px] flex items-center justify-center rounded-3xl overflow-hidden p-4">
                    <img :src="product.image" :alt="product.name"
                        class="w-full h-full object-contain transition-transform duration-200 ease-in-out hover:scale-110" />
                </div>

                <!-- ✅ ข้อมูลสินค้า -->
                <div class="flex flex-col items-center justify-center mt-2 text-center gap-2">
                    <!-- ✅ ชื่อสินค้า -->
                    <h3
                        class="text-3xl font-bold text-purple-400 font-poppins min-h-[60px] h-[60px] flex items-center justify-center">
                        {{ product.name }}
                    </h3>

                    <!-- ✅ คำอธิบายสินค้า -->
                    <p class="text-white text-xl leading-relaxed px-4 whitespace-normal break-words">
                        {{ product.description }}
                    </p>
                </div>

            </div>
        </div>

        <!-- 🔹 ปุ่ม All Product -->
        <div class="mt-12 relative z-10">
            <router-link to="/all-products" class="px-10 py-4 text-lg font-semibold bg-gradient-to-r from-purple-600 to-indigo-600 text-white rounded-full shadow-lg 
                       hover:shadow-2xl transition-transform duration-300 transform hover:scale-110">
                All Products
            </router-link>
        </div>

    </section>
</template>



<script setup>
import PathummaImage from "@/assets/images/Pathumma.png";
import AbdulImage from '@/assets/images/Abdul.png';
import SontanaImage from '@/assets/images/Sontana.png';
import PartiiImage from '@/assets/images/Partii.png';

// ✅ ฟังก์ชันเปิดลิงก์
const goToWebsite = (link) => {
    if (link) {
        window.open(link, "_blank");
    }
};

// ✅ ข้อมูลสินค้า (เพิ่ม `link` สำหรับการนำทาง)
const products = [
    {
        name: "Patthumma LLM",
        image: PathummaImage,
        description: "ระบบ AI ที่สามารถตอบคำถาม ให้คำปรึกษา และแนะนำข้อมูลในรูปแบบข้อความหรือการสนทนา",
        link: "https://aiforthai.in.th/pathumma-llm/"
    },
    {
        name: "Abdul Chatbot ",
        image: AbdulImage,
        description: "แพลตฟอร์มสำหรับสร้างแชทบอท",
        link: "https://chat.abdul.in.th/"
    },
    {
        name: "Partii",
        image: PartiiImage,
        description: "ระบบแปลงเสียงพูดให้เป็นข้อความภาษาไทย",
        link: "https://aiforthai.in.th/service_st.php"
    },
];
</script>

<!-- ✅ ใช้ Google Fonts + Tailwind -->
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Poppins:wght@500&display=swap");

.font-playfair {
    font-family: "Playfair Display", serif;
}

.font-poppins {
    font-family: "Poppins", sans-serif;
}
</style>
