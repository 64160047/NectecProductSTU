<template>
    <section
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
                class="bg-white rounded-3xl shadow-2xl transform transition hover:scale-105 flex flex-col h-[500px] overflow-hidden">
                <!-- ✅ รูปภาพมี Animation -->
                <div class="w-full h-[60%] flex items-center justify-center">
                    <img :src="product.image" :alt="product.name"
                        class="w-[85%] h-[85%] object-contain rounded-t-3xl opacity-0 animate-fadeIn transition-transform duration-700 ease-in-out hover:scale-110" />
                </div>

                <!-- ✅ ข้อมูลสินค้า (เลื่อน description ขึ้นมาใกล้หัวข้อ) -->
                <div class="p-6 flex flex-col items-center justify-between h-[40%]">
                    <h3 class="text-2xl font-serif text-purple-600 font-poppins">
                        {{ product.name }}
                    </h3>
                    <p class="font-serif text-gray-600 text-md mt-1">
                        {{ product.description }}
                    </p>
                    <!-- ลดช่องว่างตรงนี้ -->
                </div>
            </div>
        </div>


        <!-- 🔹 ปุ่ม All Product -->
        <div class="mt-20 relative z-10">
            <router-link to="/all-products"
                class="px-12 py-5 text-xl font-bold bg-gradient-to-r from-purple-600 to-indigo-600 text-white rounded-full shadow-lg hover:shadow-2xl transition-transform duration-300 transform hover:scale-110">
                All Products
            </router-link>
        </div>

    </section>

</template>

<script setup>
import PathummaImage from "@/assets/images/Pathumma.png";

const products = [
    {
        name: "Patthumma LLM",
        image: PathummaImage,
        description:
            "Lorem ipsum odor amet, consectetuer adipiscing elit. Ornare ac sit dictum finibus vehicula libero. Lectus ultricies viverra dui habitant torquent litora ante. Fusce nunc vivamus consectetur nunc quis nunc. Est donec aenean elit, mi ipsum purus.",
    },
    {
        name: "Abdul GI",
        image: PathummaImage,
        description:
            "Lorem ipsum odor amet, consectetuer adipiscing elit. Ornare ac sit dictum finibus vehicula libero. Lectus ultricies viverra dui habitant torquent litora ante. Fusce nunc vivamus consectetur nunc quis nunc. Est donec aenean elit, mi ipsum purus.",
    },
    {
        name: "Sontana",
        image: PathummaImage,
        description:
            "Lorem ipsum odor amet, consectetuer adipiscing elit. Ornare ac sit dictum finibus vehicula libero. Lectus ultricies viverra dui habitant torquent litora ante. Fusce nunc vivamus consectetur nunc quis nunc. Est donec aenean elit, mi ipsum purus.",
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

/* ✅ Custom Animation */
@keyframes fadeIn {
    from {
        opacity: 0;
        transform: translateY(10px);
    }

    to {
        opacity: 1;
        transform: translateY(0);
    }
}

.animate-fadeIn {
    animation: fadeIn 1s ease-out forwards;
}
</style>
