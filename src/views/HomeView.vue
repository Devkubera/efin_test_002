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
    <div class="flex gap-4 bg-slate-200 text-center">
      <div v-for="(item, index) in apiData.data" :key="index">
        {{ item }}
      </div>
    </div>
  </HomeLayout>
</template>

