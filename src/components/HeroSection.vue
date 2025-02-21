<template>
  <section
    class="relative w-full h-[60vh] flex items-center bg-gradient-to-br from-[#000000] via-[#2C327C] via-[#43218F] via-[#683BA9] to-[#AF3EFF] text-white"
  >
    <!-- 🔹 รูปพื้นหลัง (ถูกต้อง) -->
    <div
      class="absolute inset-0 bg-cover bg-center opacity-30"
      style="background-image: url('/src/assets/images/stars-1845852_1920.jpg');"
    ></div>

    <!-- 🔹 ด้านซ้าย: ข้อความ -->
    <div class="relative z-10 w-1/2 px-16 ">
      <h1 class="text-[25px] font-bold text-green-300">
        Speech and Text Understanding Research Team (STU)
      </h1>
      <p class="mt-6 text-[18px] text-white text-justify">
        Speech and Text Understanding (STU) lab conducts research and development in Thai spoken and written language technologies. The lab is engaged in wide range of R&D activities such as natural language processing, speech recognition and synthesis, information retrieval and extraction and knowledge discovered from texts. Such activities help enable computers to interact and communicate with humans with natural language capabilities.
      </p>
    </div>

    <!-- 🔹 ด้านขวา: STU -->
    <div class="relative z-10 w-1/2 flex justify-center items-center">
      <h1 class="text-[200px] font-extrabold text-white">STU</h1>
    </div>
  </section>
</template>
