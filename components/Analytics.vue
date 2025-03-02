<script lang="ts" setup>
type Detail = {
  name: string;
  number: string;
  percentage: string;
  color: string;
};

const details: Ref<Detail[]> = ref([
  {
    name: "Total Followers",
    number: "240k",
    percentage: "+10,3%",
    color: "#29BB89",
  },
  {
    name: "New Likes",
    number: "17302",
    percentage: "+3,14%",
    color: "#307BF4",
  },
  { name: "Comments", number: "2042", percentage: "+0%", color: "#FF0073" },
  { name: "Total Posts", number: "1300", percentage: "+5%", color: "#724EE6" },
  {
    name: "Blocked Accounts",
    number: "0",
    percentage: "+0%",
    color: "#F6C059",
  },
]);
</script>

<template>
  <div class="flex flex-1 w-full gap-8">
    <div
      v-for="(Detail, index) in details"
      class="flex flex-col justify-between w-1/5 bg-[#1E1F25] h-48 rounded-3xl p-8"
      :key="index"
    >
      <div>
        <ul class="pl-5 list-none">
          <li class="relative">
            <div
              class="absolute w-2.5 h-2.5 rounded-full -left-5 top-1.5"
              :style="{ backgroundColor: Detail.color }"
            ></div>
            {{ Detail.name }}
          </li>
        </ul>
      </div>
      <h1 class="text-2xl font-bold">
        {{ Detail.number }}
      </h1>
      <h1 :style="{ color: Detail.color }">{{ Detail.percentage }}</h1>
    </div>
  </div>
</template>
