<script setup></script>

<template>
  <div class="mx-auto container">
    <!-- Nav bar -->
    <div class="bg-slate-500 flex p-4 items-center">
        <div class="ml-8">
            <img src="https://cdn.pixabay.com/photo/2020/09/16/18/39/icon-5577198_1280.png" width="50" alt="">
        </div>
        <!-- Make it a pointer -->
        <div class="ml-8 font-bold"><button>Menu 1</button></div>
        <div class="ml-8 font-bold"><button>Menu 2</button></div>
        <div class="ml-8 font-bold"><button>Menu 3</button></div>
    </div>
    <div class="bg-slate-300 max-h-screen">
        <slot></slot>
    </div>
  </div>
</template>
