<script lang="ts" setup>
type Link = {
  name: string;
  to: string;
  icon: string;
};

const route = useRoute();

const links: Ref<Link[]> = ref([
  { name: "Dashboard", to: "/", icon: "mingcute:classify-add-fill" },
  { name: "Users", to: "/users", icon: "mingcute:user-4-line" },
  {
    name: "Schedule",
    to: "/schedule",
    icon: "material-symbols:calendar-month-outline-sharp",
  },
  { name: "Income", to: "/income", icon: "material-symbols:attach-money" },
  { name: "Saved", to: "/saved", icon: "mingcute:bookmark-fill" },
  { name: "Settings", to: "/settings", icon: "heroicons-solid:cog" },
]);
</script>

<template>
  <nav
    class="flex flex-col items-center justify-between bg-[#1E1F25] h-screen w-64 text-left text-xl px-4 py-6"
  >
    <div>
      <div class="p-8">
        <NuxtLink to="/"><img src="/assets/Group 513968.png" /></NuxtLink>
      </div>
      <ul class="space-y-2">
        <li
          :class="[
            'flex py-4 px-5 items-center gap-6 ',
            link.to === route.path
              ? 'bg-[#307BF4] rounded-2xl '
              : 'text-slate-400',
          ]"
          v-for="(link, index) in links"
          :key="index"
        >
          <UIcon :name="link.icon" class="text-3xl" />
          <NuxtLink :to="link.to" class="">{{ link.name }}</NuxtLink>
        </li>
      </ul>
    </div>
    <div
      class="flex flex-col items-center justify-center text-center w-full bg-[#307BF4] h-60 rounded-3xl gap-3 font-body"
    >
      <h1 class="text-2xl font-bold">Upgrade Pro</h1>
      <h1 class="text-sm max-w-36">Upgrade now for get benefits more.</h1>
      <UButton
        block
        label="Upgrade Plan"
        color="black"
        size="xl"
        class="rounded-3xl w-40"
      ></UButton>
    </div>
  </nav>
</template>
