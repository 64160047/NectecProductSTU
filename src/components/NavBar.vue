<script setup>
import { useRoute, useRouter } from 'vue-router';

// ✅ ดึงข้อมูลเส้นทางปัจจุบัน & router
const route = useRoute();
const router = useRouter();

// ✅ ฟังก์ชันเลื่อนหน้าไปยัง Section ที่ต้องการ
const scrollToSection = (sectionId) => {
  const section = document.getElementById(sectionId);
  if (section) {
    section.scrollIntoView({ behavior: 'smooth' });
  }
};

// ✅ ฟังก์ชัน Home: ถ้าอยู่หน้า All Products ให้ย้อนกลับ
const goHome = () => {
  if (route.path === "/all-products") {
    router.push("/"); // 🔹 กลับไปหน้าแรก
  } else {
    scrollToSection('home'); // 🔹 เลื่อนหน้าไปยัง Home
  }
};
</script>

<template>
    <!-- ✅ Navbar (Fixed ด้านบน) -->
    <nav class="fixed top-0 left-0 w-full bg-[#060E36] shadow-lg border-b border-gray-700 z-50">
        <div class="mx-auto px-8 lg:px-16">
            <div class="flex h-20 items-center">

                <!-- 🔹 ปุ่มเมนู (ชิดซ้าย) -->
                <div class="flex space-x-8">
                    <button @click="goHome" class="nav-button">Home</button>
                    <button @click="scrollToSection('products')" class="nav-button">Products</button>
                    <button @click="scrollToSection('footer')" class="nav-button">Contact</button>
                </div>

            </div>
        </div>
    </nav>
</template>

<style scoped>
/* ✅ ปุ่มเมนู */
.nav-button {
    color: white;
    padding: 14px 22px;
    font-size: 20px;
    font-weight: bold;
    border-radius: 12px;
    transition: all 0.3s ease-in-out;
}

/* ✅ เอฟเฟกต์ Hover */
.nav-button:hover {
    background: linear-gradient(90deg, #6A5ACD, #9370DB);
    transform: scale(1.05);
    box-shadow: 0px 4px 10px rgba(255, 255, 255, 0.2);
}
</style>
