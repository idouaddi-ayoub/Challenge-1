<script lang="ts" setup></script>

<template>
  <div class="flex">
    <SideNav />
    <div class="flex-1 p-8">
      <TopNav />
      <slot />
    </div>
  </div>
</template>
