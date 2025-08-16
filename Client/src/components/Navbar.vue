<template>
    <nav class="navbar flex shadow-lg text-white h-24 px-10 bg-[rgba(0,0,0,0.09)]  relative  justify-between items-center content-center flex-wrap">
      <div class="left flex items-center gap-20 font-[500] text-[1em]">
        <div class="logo w-40 h-full">
            <img class="w-full h-full" src="../assets/20250814_0107_White Logo Conversion_remix_01k2jggk4dfhraebeedfgfb441.png" alt="">
        </div>
        <ul class=" hidden lg:flex gap-4 text-white">
            <li class="">
                <router-link to="/">Home</router-link>
            </li>
            <li>
                <router-link to="/about">About</router-link>    
            </li>
            <li>
                <router-link to="/contact">Contact</router-link>
            </li>
            <li>
                <router-link to="/products">Products</router-link>
            </li>
        </ul>
      </div>
      <div class="right ">
        <ul class="flex items-center gap-4">
            <li class=" hidden lg:block text-[1em] ">
                <router-link to="/cart">About</router-link>
            </li>
            <li class=" hidden lg:block text-[1em]">
                <router-link to="/login">Contact us</router-link>
            </li>
            <li >
                <router-link to="/cart" class=" flex items-center gap-2 text-[1em] cursor-pointer">
                    $00.00
                <span to="/cart" class="relative">
                    <Handbag class="w-5 h-5" />
                    <div class="dot absolute w-4 h-4 flex justify-center items-center  -top-2 left-3 bg-white rounded-full text-sm font-bold text-black">0</div>
                </span>
                </router-link>
                
            </li>
            <li class="hidden lg:block">
                <router-link to="/profile">
                    <User class="w-5 h-5" />
                </router-link>
            </li>
            <li class="relative lg:hidden">
                <button @click="is_active = !is_active" >
                    <AlignJustify class="w-5 h-5" />
                </button>
            </li>
        </ul>
      </div>
    </nav>
    <nav v-if="is_active" class=" overflow-auto fixed z-50 top-0 right-0 w-[50%] h-screen text-black bg-[#FFFFFF]" >
        <div class=" absolute flex justify-center items-center right-5 top-2 hover:cursor-pointer p-4 hover:bg-gray-100 transition-all duration-300 rounded-full">
            <button @click="is_active = !is_active">
                <X class="w-5 h-5" />
            </button>

        </div>
        
        <ul class="flex flex-col items-left justify-center w-full font-[500] h-full  ">
            <li class="text-[1em] w-full px-10 py-5 hover:text-[#1B6A97] hover:bg-gray-100 transition-all duration-300 cursor-pointer border-[#eaeaea] border-b-[1px]">
                Home
            </li>
            <li  class="text-[1em] w-full px-10 py-5 hover:text-[#1B6A97] hover:bg-gray-100 transition-all duration-300 cursor-pointer border-[#eaeaea] border-b-[1px]">
                <router-link to="/about">Everything</router-link>    
            </li>
            <li  class="text-[1em] w-full px-10 py-5 hover:text-[#1B6A97] hover:bg-gray-100 transition-all duration-300 cursor-pointer border-[#eaeaea] border-b-[1px]">
                <router-link to="/contact">Contact</router-link>
            </li>
            <li  class="text-[1em] w-full px-10 py-5 hover:text-[#1B6A97] hover:bg-gray-100 transition-all duration-300 cursor-pointer border-[#eaeaea] border-b-[1px]">
                <router-link to="/products">Products</router-link>
            </li>
            <li   class="text-[1em] w-full px-10 py-5 hover:text-[#1B6A97] hover:bg-gray-100 transition-all duration-300 cursor-pointer border-[#eaeaea] border-b-[1px]">
                <router-link to="/cart">Cart</router-link>
            </li>
            <li  class="text-[1em] w-full px-10 py-5 hover:text-[#1B6A97] hover:bg-gray-100 transition-all duration-300 cursor-pointer border-[#eaeaea] border-b-[1px]">
                <router-link to="/login">Login</router-link>
            </li>
        </ul>
    </nav>
</template>

<script setup>
import { User,Handbag,AlignJustify ,X  } from 'lucide-vue-next';
import { ref } from 'vue';
const is_active = ref(false);
</script>
