<template>
  <div class="flex w-full px-8 py-3 items-center bg-gray-100 overflow-scroll scroll-bar">
    <div class="w-12">
      <img
        src="../assets/images/search-icon.png"
        alt="seacrh icon"
        class="w-full"
      />
    </div>
    <div class="flex ml-6">
      <div class="w-5">
        <img src="../assets/images/save.png" alt="seacrh icon" class="w-full" />
      </div>
      <div class="flex ml-4">
        <div class="w-5">
          <img
            src="../assets/images/arrow-left.png"
            alt="seacrh icon"
            class="w-full"
          />
        </div>
        <div class="w-3 self-end justify-center">
          <img
            src="../assets/images/down-arrow.png"
            alt="seacrh icon"
            class="w-full"
          />
        </div>
      </div>

      <div class="flex ml-4">
        <div class="w-5">
          <img
            src="../assets/images/arrow-right.png"
            alt="seacrh icon"
            class="w-full"
          />
        </div>
        <div class="w-3 self-end justify-end">
          <img
            src="../assets/images/down-arrow.png"
            alt="seacrh icon"
            class="w-full"
          />
        </div>
      </div>
    </div>
    <div>
      <ul class="flex ml-6">
        <li class="text-[grey] text-sm">File</li>
        <li class="ml-6 text-[grey] text-sm">Home</li>
        <li class="ml-6 font-bold text-sm pb-1 border-b-[yellow] active">
          Transform
        </li>
        <li class="ml-6 text-[grey] text-sm">Add Column</li>
        <li class="ml-6 text-[grey] text-sm">View</li>
        <li class="ml-6 text-[grey] text-sm">Tools</li>
        <li class="ml-6 text-[grey] text-sm">Help</li>
      </ul>
    </div>
    <div class="ml-12">
      <p class="font-bold text-base">Dataname - MyDataClinic Editor</p>
    </div>
  </div>
</template>

<style scoped>
.active {
  position: relative;
  display: inline-block;
}
.active::after {
  content: "";
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 70%;
  border-bottom: 2px solid #ffd701;
  padding: 3px;
}
.scroll-bar {
  scrollbar-width: none;
}
.scroll-bar::-webkit-scrollbar {
  display: none;
}
</style>