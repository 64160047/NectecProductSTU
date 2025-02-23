<template>
    <section id="products"
        class="relative w-full min-h-screen bg-gradient-to-br from-[#2A1D72] via-[#2C327C] to-[#04C484] text-center py-16">
        
        <!-- 🔹 รูปพื้นหลัง -->
        <div class="absolute inset-0 bg-cover bg-center opacity-50 z-0 mix-blend-overlay"
            style="background-image: url('/src/assets/images/stars-1845852_1920.jpg')"></div>

        <!-- 🔹 หัวข้อ -->
        <h2 class="text-6xl font-extrabold text-white mb-16 font-playfair tracking-wide">
            Products
        </h2>

        <!-- 🔹 Grid แสดงสินค้า -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-16 px-12 max-w-8xl mx-auto">
            <div v-for="product in products" :key="product.name" 
                @click="goToWebsite(product.link)" 
                class="bg-white rounded-3xl shadow-2xl transform transition hover:scale-105 flex flex-col h-[500px] 
                      overflow-hidden p-6 cursor-pointer hover:shadow-purple-400">

                <!-- ✅ รูปภาพ (มุมมนทุกด้าน) -->
                <div class="w-full h-[55%] flex items-center justify-center rounded-3xl overflow-hidden">
                    <img :src="product.image" :alt="product.name"
                        class="w-full h-full object-contain rounded-3xl transition-transform duration-700 ease-in-out hover:scale-110" />
                </div>

                <!-- ✅ ข้อมูลสินค้า (ขยับคำอธิบายขึ้นมา) -->
                <div class="flex flex-col items-center justify-center h-[45%]">
                    <h3 class="text-3xl font-bold text-purple-700 font-poppins text-center">
                        {{ product.name }}
                    </h3>
                    <p class="text-gray-700 text-lg text-center leading-relaxed mt-3 px-4">
                        {{ product.description }}
                    </p>
                </div>
            </div>
        </div>

        <!-- 🔹 ปุ่ม All Product -->
        <div class="mt-16 relative z-10">
            <router-link to="/all-products"
                class="px-12 py-5 text-xl font-bold bg-gradient-to-r from-purple-600 to-indigo-600 text-white rounded-full shadow-lg hover:shadow-2xl transition-transform duration-300 transform hover:scale-110">
                All Products
            </router-link>
        </div>

    </section>
</template>

<script setup>
import PathummaImage from "@/assets/images/Pathumma.png";
import AbdulImage from '@/assets/images/Abdul.png';
import SontanaImage from '@/assets/images/Sontana.png';

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
        name: "Abdul Chatbot Platform",
        image: AbdulImage,
        description: "แพลตฟอร์มสำหรับสร้างแชทบอท",
        link: "https://abdul.ai"
    },
    {
        name: "Sontana",
        image: SontanaImage,
        description: "อวทาร์ให้บริการตอบคำถามแบบอัตโนมัติ พร้อมสีหน้าและน้ำเสียงที่สุภาพ",
        link: "https://example.com/sontana"
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
