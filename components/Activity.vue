<script setup lang="ts">
import { VisXYContainer, VisStackedBar, VisAxis } from "@unovis/vue";

type DataRecord = {
  name: string;
  followers: string;
  y: number;
};

type Follower = {
  name: string;
  followers: string;
  profilePicture: string;
};

const followers: Ref<Follower[]> = ref([
  {
    name: "@USER1",
    followers: "25K",
    profilePicture: "https://xsgames.co/randomusers/avatar.php?g=male",
  },
  {
    name: "@USER2",
    followers: "25K",
    profilePicture: "https://xsgames.co/randomusers/avatar.php?g=male",
  },
  {
    name: "@USER3",
    followers: "250K",
    profilePicture: "https://xsgames.co/randomusers/avatar.php?g=male",
  },
  {
    name: "@USER4",
    followers: "2K",
    profilePicture: "https://xsgames.co/randomusers/avatar.php?g=male",
  },
]);

const data: Ref<DataRecord[]> = ref([
  {
    name: "Jan",
    followers: "5K",
    y: 1,
  },
  {
    name: "Feb",
    followers: "10K",
    y: 10,
  },
  {
    name: "Mar",
    followers: "17K",
    y: 17,
  },
  {
    name: "Jan",
    followers: "5K",
    y: 1,
  },
  {
    name: "Feb",
    followers: "10K",
    y: 10,
  },
  {
    name: "Mar",
    followers: "17K",
    y: 20,
  },
]);

const countries = ["United States", "Canada", "Mexico"];

const country = ref(countries[0]);

const x = (_d: DataRecord, index: number) => index;
const y = (d: DataRecord) => d.y;
</script>
<template>
  <div class="flex gap-8 flex-1 w-full">
    <div class="flex flex-col w-4/5 bg-[#1E1F25] p-8 rounded-3xl gap-8">
      <div class="flex flex-1 items-center justify-between">
        <p>Activity Followers</p>
        <div class="flex items-center gap-3">
          <UButton
            icon="material-symbols-light:bar-chart"
            variant="ghost"
            color="blue"
          ></UButton>
          <UButton
            icon="material-symbols-light:show-chart"
            variant="ghost"
            color="blue"
          ></UButton>
          <USelect v-model="country" :options="countries" />
        </div>
      </div>
      <VisXYContainer :data="data" class="bg-[#1E1F25]">
        <VisStackedBar :x="x" :y="y" rounded-corners="30" />
        <VisAxis type="x" />
        <VisAxis type="y" />
      </VisXYContainer>
    </div>
    <div
      class="flex flex-col w-1/5 shrink-0 rounded-3xl bg-[#1E1F25] p-8 gap-8"
    >
      <div class="flex flex-1 items-center justify-between">
        <p>New Followers</p>
        <UButton variant="ghost" color="blue">See All</UButton>
      </div>
      <div
        v-for="follower in followers"
        :key="follower.name"
        class="flex items-center gap-8"
      >
        <UAvatar :src="follower.profilePicture" alt="Avatar" size="xl" />
        <div class="space-y-2">
          <div class="flex items-center gap-2">
            <p>{{ follower.name }}</p>
            <UIcon
              name="material-symbols:verified"
              class="text-blue-500"
            ></UIcon>
          </div>
          <p>{{ follower.followers }} Followers</p>
        </div>
      </div>
    </div>
  </div>
</template>
