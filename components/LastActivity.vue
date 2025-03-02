<script lang="ts" setup>
interface Activity {
  name: string;
  icon: string;
  state: string;
  statusDate: string;
  progress: number;
}

const activities: Ref<Activity[]> = ref([
  {
    name: "Ads Challenge",
    icon: "material-symbols-light:post-outline-rounded",
    state: "14k See posted",
    statusDate: "29 Mar, 2022",
    progress: 37,
  },
  {
    name: "Add Members",
    icon: "carbon:user-avatar-filled",
    state: "Waiting join",
    statusDate: "30 Mar, 2022",
    progress: 89,
  },
]);
</script>

<template>
  <div class="flex flex-col justify-center p-10 bg-[#1E1F25] w-1/2 rounded-3xl">
    <div class="flex flex-1 justify-between">
      <p>Last Activity</p>
      <UButton
        variant="ghost"
        color="black"
        class="border-2 border-gray-500 rounded-xl"
      >
        <UIcon name="material-symbols:share-windows" />
        Share</UButton
      >
    </div>
    <p class="text-gray-500">Recently for this week</p>
    <div
      v-for="(activity, index) in activities"
      :key="index"
      class="flex flex-1 justify-between"
    >
      <div class="flex w-1/3 gap-6">
        <UIcon :name="activity.icon" size="60" class="text-blue-500" />
        <div class="flex flex-col">
          {{ activity.name }}
          <p class="text-gray-500">{{ activity.state }}</p>
        </div>
      </div>
      <div class="w-1/3">
        <p>{{ activity.progress }}% Targeted</p>
        <UProgress :value="activity.progress" />
      </div>
      <div>
        <p>Status {{ activity.statusDate }}</p>
        <p>Details</p>
      </div>
    </div>
  </div>
</template>
