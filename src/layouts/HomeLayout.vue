<script setup></script>

<template>
  <div class="container">
    <!-- Nav bar -->
    <div class="w-full bg-slate-500 flex p-4 items-center">
        <div class="ml-8">
            <img src="https://cdn.pixabay.com/photo/2020/09/16/18/39/icon-5577198_1280.png" width="50" alt="">
        </div>
        <!-- Make it a pointer -->
        <div class="ml-8"><button>Menu 1</button></div>
        <div class="ml-8"><button>Menu 2</button></div>
        <div class="ml-8"><button>Menu 3</button></div>
    </div>
    <div class="bg-slate-300">
        <slot></slot>
    </div>
  </div>
</template>
