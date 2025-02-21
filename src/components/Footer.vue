<template>
    <footer id="footer" class="w-full h-[30vh] bg-[#040A26] text-white py-12 px-20">
      <div class="container mx-auto flex flex-col md:flex-row justify-between items-center max-w-7xl space-y-8 md:space-y-0">
        
        <!-- 🔹 Contact us -->
        <div class="text-center md:text-left">
          <h4 class="text-2xl font-extrabold text-purple-400">Contact Us</h4>
          <p class="text-lg text-gray-300 mt-2">Email: example@email.com</p>
          <p class="text-lg text-gray-300">Phone: +123 456 7890</p>
        </div>
  
        <!-- 🔹 Information -->
        <div class="text-center md:text-left">
          <h4 class="text-2xl font-extrabold text-purple-400">Information</h4>
          <p class="text-lg text-gray-300 mt-2">Privacy Policy</p>
          <p class="text-lg text-gray-300">Terms & Conditions</p>
        </div>
  
        <!-- 🔹 STU Team (เพิ่มช่องว่างให้ดูสมดุลขึ้น) -->
        <div class="md:text-right">
          <h4 class="text-2xl md:text-4xl font-extrabold font-playfair tracking-wide leading-snug md:leading-normal mt-4">
            Speech and Text Understanding <br> Research Team (STU)
          </h4>
        </div>
      </div>
    </footer>
  </template>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&display=swap');
  
  .font-playfair {
    font-family: 'Playfair Display', serif;
  }
  </style>