<template>
  <div class="block lg:flex justify-between px-24 mt-16 items-center">
    <div class="w-auto">
      <h1 class="text-3xl lg:text-6xl text-gray-800">
        Bibendum soda <br />
        les mauris
      </h1>
      <p class="mt-5 text-xl lg:text-2xl">Nunc Scelerisque Tincidunt Elit Vestibulum Non</p>
      <h1 class="text-gray-800 underline text-lg lg:text-3xl mt-5">
        <span class="bg-rose-500"> Sh</span>op Now
        <i class="fa-solid fa-arrow-right-long ml-3" aria-hidden="true"></i>
      </h1>
    </div>

    <div class="relative mx-auto flex justify-center items-center mt-16">
  <!-- Container for images and text -->
  <div class="relative w-full max-w-lg">
    <!-- Background Circle Image -->
    <img
      src="../../assets/images/backcircle.png"
      class="w-[200px] h-[200px] md:w-[400px] md:h-[400px] lg:w-[500px] lg:h-[500px] mx-auto"
      alt="Background Circle"
    />
    <!-- Foreground Image -->
    <img
      src="../../assets/images/first.png"
      class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-[150px] h-[200px] md:w-[300px] md:h-[400px] lg:w-[400px] lg:h-[500px]"
      alt="Foreground Image"
    />
    <!-- Deal of the Day Text -->
    <div class="hidden md:block absolute bottom-0 left-1/2 transform -translate-x-1/2 translate-y-1/2 lg:translate-y-0 lg:left-0 lg:ml-16 text-gray-800 text-center lg:text-left">
      Deal of the day
    </div>
  </div>
</div>


  </div>

  <div id="downImage" class="hidden lg:flex justify-end mr-20 space-x-3">
    <!-- 1 -->
    <div class="max-w-sm">
      <div class="relative">
        <span
          class="absolute left-0 bg-red-500 text-white text-xs font-bold py-1 px-2 rounded-bl-lg"
          >-62.5%</span
        >
        <img
          src="../../assets/images/women.jpg"
          alt="Drapey Cardigan"
          class="w-full h-64 object-cover rounded-lg"
        />

        <div class="absolute bottom-0 bg-black/30 backdrop-blur-5xl w-full px-2 flex items-center">
          <p class="text-xs font-semibold text-white">Drapey Cardigan</p>
          <div class="block">
            <span class="text-xs font-medium text-gray-200 line-through">$200.00</span>
            <span class="text-s font-bold text-white">$75.00</span>
          </div>
        </div>
      </div>
    </div>

    <!-- 2 -->
    <div class="max-w-sm">
      <div class="relative">
        <span
          class="absolute left-0 bg-red-500 text-white text-xs font-bold py-1 px-2 rounded-bl-lg"
          >-62.5%</span
        >
        <img
          src="../../assets/images/women.jpg"
          alt="Drapey Cardigan"
          class="w-full h-64 object-cover rounded-lg"
        />

        <div class="absolute bottom-0 bg-black/30 backdrop-blur-5xl w-full px-2 flex items-center">
          <p class="text-xs font-semibold text-white">Drapey Cardigan</p>
          <div class="block">
            <span class="text-xs font-medium text-gray-200 line-through">$200.00</span>
            <span class="text-s font-bold text-white">$75.00</span>
          </div>
        </div>
      </div>
    </div>
    <!-- 3 -->
    <div class="max-w-sm">
      <div class="relative">
        <span
          class="absolute left-0 bg-red-500 text-white text-xs font-bold py-1 px-2 rounded-bl-lg"
          >-62.5%</span
        >
        <img
          src="../../assets/images/women.jpg"
          alt="Drapey Cardigan"
          class="w-full h-64 object-cover rounded-lg"
        />

        <div class="absolute bottom-0 bg-black/30 backdrop-blur-5xl w-full px-2 flex items-center">
          <p class="text-xs font-semibold text-white">Drapey Cardigan</p>
          <div class="block">
            <span class="text-xs font-medium text-gray-200 line-through">$200.00</span>
            <span class="text-s font-bold text-white">$75.00</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
