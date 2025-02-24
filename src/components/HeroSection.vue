<template>
  <section
    class="relative w-full h-[60vh] flex flex-col lg:flex-row items-center bg-gradient-to-br from-[#000000] via-[#2C327C] via-[#43218F] via-[#683BA9] to-[#AF3EFF] text-white pt-32"
  >
    <!-- 🔹 รูปพื้นหลัง -->
    <div
      class="absolute inset-0 bg-cover bg-center opacity-30"
      style="background-image: url('/src/assets/images/stars-1845852_1920.jpg');"
    ></div>

    <!-- 🔹 ด้านซ้าย: ข้อความ -->
    <div class="relative z-10 w-full lg:w-1/2 px-5 lg:px-16 text-center lg:text-left">
      <h1 class="text-2xl md:text-3xl lg:text-4xl xl:text-5xl font-bold text-green-300 tracking-wide leading-snug">
        Speech and Text Understanding Research Team (STU)
      </h1>
      <p class="mt-6 text-lg md:text-xl text-white text-justify  tracking-wide ">
        Speech and Text Understanding (STU) lab conducts research and development in Thai spoken and written language technologies.
        The lab is engaged in wide range of R&D activities such as natural language processing, speech recognition and synthesis, 
        information retrieval and extraction and knowledge discovered from texts. Such activities help enable computers to interact 
        and communicate with humans with natural language capabilities.
      </p>
    </div>

    <!-- 🔹 ด้านขวา: STU -->
    <div class="relative z-10 w-full lg:w-1/2 flex justify-center items-center mt-8 lg:mt-0">
      <h1 class="text-7xl md:text-8xl lg:text-[160px] xl:text-[200px] font-extrabold text-white tracking-widest leading-none">
        STU
      </h1>
    </div>
  </section>
</template>


