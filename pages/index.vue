<script setup lang="ts">
definePageMeta({
  layout: "default",
});
</script>

<template>
  <div class="flex flex-1 flex-col items-center gap-8">
    <Analytics />
    <Activity />
    <div class="flex w-full gap-8 items-center">
      <LastActivity />
      <NewAchievement />
    </div>
  </div>
</template>
