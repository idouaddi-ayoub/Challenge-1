<template>
  <div class="flex flex-1">
    <div class="flex justify-between w-full h-32 items-center">
      <div class="flex px-8 items-center">
        <div class="w-full max-w-sm min-w-[200px]">
          <div class="relative">
            <input
              class="w-full placeholder:text-slate-400 text-white text-sm bg-[#1E1F25] rounded-2xl pl-3 pr-28 py-3 transition duration-300 ease focus:outline-none focus:border-slate-400 hover:border-slate-300 shadow-sm focus:shadow"
              placeholder="Search..."
            />
            <UIcon
              name="tdesign:search"
              class="text-2xl absolute right-3 top-2 items-center justify-center"
            />
          </div>
        </div>
      </div>
      <div class="flex px-20 items-center gap-3">
        <UIcon
          name="material-symbols-light:notifications-outline-rounded"
          class="text-3xl"
        />
        <div class="w-10 h-10 rounded-full inline-flex bg-white"></div>
        <div>
          <h1 class="font-bold">Zachary A.</h1>
          <h1 class="text-sm text-gray-600">Owner Admin</h1>
        </div>
      </div>
    </div>
  </div>
</template>
