<script setup>
import { onMounted, reactive } from "vue";
import axios from "axios";

import HomeLayout from "@/layouts/HomeLayout.vue";

const BASE_URL = "https://demotrade.efintradeplus.com/ExamAPI/examdata";

const apiData = reactive({ data: [] });

onMounted(async () => {
  try {
    const response = await axios.get(`${BASE_URL}`);
    if (response.data) {
      apiData.data = response.data;
      console.log(response.data);
    }
  } catch (e) {
    console.error("error to fetch data: ", e);
  }
});
</script>

<template>
  <HomeLayout>
    <div class="flex p-4 gap-4 text-white text-center">
      <!-- left -->
      <div class="flex-grow">
        <div class="grid gap-4 grid-cols-3 h-screen">
          <div class="bg-stone-600 row-span-2 col-span-2">
            {{ apiData.data.data_1 }}
          </div>
          <div class="bg-slate-800 row-span-2">{{ apiData.data.data_2 }}</div>
          <div class="bg-zinc-500 col-span-2">{{ apiData.data.data_3 }}</div>
          <div class="bg-sky-950">{{ apiData.data.data_4 }}</div>
          <div class="bg-yellow-950 col-span-full">
            {{ apiData.data.data_5 }}
          </div>
        </div>
      </div>
      <!-- right -->
      <div class="flex-grow bg-violet-950">{{ apiData.data.data_6 }}</div>
    </div>
  </HomeLayout>
</template>
