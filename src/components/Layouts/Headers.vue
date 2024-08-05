<template>
   <!-- fontawesome -->
    
       <!-- Navbar -->
   <nav class="mt-3 px-4 sm:px-6 lg:px-8">
    <div class="flex flex-wrap justify-between items-center">
        <div class="block lg:flex flex-1 gap-4 items-center">
            <div class="flex items-center gap-2">
                <i class="fa-brands fa-instagram text-gray-900 text-md lg:text-xl"></i>
                <p class="text-sm">31.3M Followers</p>
            </div>
            <div class="text-sm sm:text-base">
                Free Shipping for all orders over $199.
                <span class="text-red-400"> Click and Shop Now.</span>
            </div>
        </div>
        <div class="flex gap-5 items-center mt-3 sm:mt-0">
            <ul class=" block lg:flex gap-5">
                <li class="flex gap-1 items-center">
                    <i class="fa-solid fa-box-open text-gray-900"></i> 
                    <span>Order Tracking</span>
                </li>
                <li class="flex gap-1 items-center">
                    English <i class="fa-solid fa-caret-down text-gray-900"></i>
                </li>
                <li class="flex gap-1 items-center">
                    USD <i class="fa-solid fa-caret-down text-gray-900"></i>
                </li>
            </ul>
        </div>
    </div>
</nav>


    <hr class="mt-4 border-gray-500" />
    <!-- part2 -->
    <div class="block md:justify-center lg:flex  lg:justify-around m-5 lg:mt-4 items-center">
  <div class="flex items-center">
    <svg
      xmlns="http://www.w3.org/2000/svg"
      width="30.222"
      height="30.217"
      viewBox="0 0 46.222 46.217"
    >
      <path
        id="Icon_awesome-shopware"
        data-name="Icon awesome-shopware"
        d="M37.415,42.252a23.111,23.111,0,1,1,1.7-35.773.333.333,0,0,1-.267.576,39.007,39.007,0,0,0-5.284-.343c-12.054,0-20.723,4.982-20.723,14.476,0,10.157,8.585,13.593,16.477,16.654,3.135,1.211,6.094,2.363,8.107,3.875a.334.334,0,0,1,0,.533Zm9.271-20.716a.339.339,0,0,0-.118-.227c-4.823-4.007-8.724-5.636-13.463-5.636-7.839,0-7.478,4.861-7.478,5,0,3.969,4.851,5.777,10.468,7.873a63.276,63.276,0,0,1,8.636,3.721.333.333,0,0,0,.466-.17A23.2,23.2,0,0,0,46.687,21.536Z"
        transform="translate(-0.563 -0.562)"
        fill="#fe8080"
      />
    </svg>
    <span class="text-6xl">Inot</span>
  </div>
  <div>
    <div class="flex border border-gray-300 rounded-md overflow-hidden bg-white items-center">
      <div class="flex items-center px-3">
        <svg
          class="h-5 w-5 text-gray-500 cursor-pointer"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 20 20"
          fill="currentColor"
        >
          <path
            fill-rule="evenodd"
            d="M12.9 14.32a8 8 0 111.414-1.414l4.29 4.29a1 1 0 01-1.414 1.414l-4.29-4.29zM8 14a6 6 0 100-12 6 6 0 000 12z"
            clip-rule="evenodd"
          />
        </svg>
      </div>
      <input
        type="text"
        class="px-4 py-3 w-auto border-0"
        placeholder="Search..."
      />
      <span class="text-3xl">|</span>
      <select class="px-4 py-2 bg-transparent border-0">
        <option>Select Category</option>
        <option>1111</option>
        <option>2222</option>
        <option>3333</option>
      </select>
    </div>
  </div>
  <div class="space-x-3">
    <i class="fa-solid fa-circle-user text-xl cursor-pointer"></i>
    <i class="fa-regular fa-heart text-xl cursor-pointer"></i>
    <span class="text-xl cursor-pointer">$0.00</span>
    <i class="fa-solid fa-box-open text-xl cursor-pointer"></i>
  </div>
</div>

    <hr class="mt-4 border-gray-500" />
    <!-- part 3 home -->
 
 <nav class="flex justify-between px-6 sm:px-12 md:px-24 mt-4 items-center">
    <div class="">
      <select class="px-4 py-2 bg-transparent border-0">
        <option>All Category</option>
        <option>1111</option>
        <option>2222</option>
        <option>3333</option>
      </select>
    </div>
    <div class="block sm:hidden">
      <button id="nav-toggle" class="text-gray-900 text-xl focus:outline-none">
        <i class="fas fa-bars"></i>
      </button>
    </div>
    <div id="nav-links" class="hidden sm:flex gap-3">
      <ul class="flex flex-col sm:flex-row sm:gap-3 sm:flex sm:items-center">
        <li class="uppercase">Home</li>
        <li class="uppercase">
          shop <i class="fa-solid fa-caret-down text-gray-900"></i>
        </li>
        <li class="uppercase">man</li>
        <li class="uppercase">women</li>
        <li class="uppercase">outerwear</li>
        <li class="uppercase">Blog</li>
        <li class="uppercase">Contact</li>
      </ul>
    </div>
  </nav>
</template>
    <script>
  // JavaScript to toggle the navigation menu
  document.addEventListener('DOMContentLoaded', () => {
    const navToggle = document.getElementById('nav-toggle');
    const navLinks = document.getElementById('nav-links');

    navToggle.addEventListener('click', () => {
      navLinks.classList.toggle('hidden');  

    });
  });

  export default {
  name :'Headers'
};
</script>
