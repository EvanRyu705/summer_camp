<div class="h-screen bg-gradient-to-b from-black via-indigo-900 to-black relative overflow-hidden">
    <div class="absolute bg-gradient-to-r from-yellow-300 via-yellow-500 to-yellow-300 animate-pulse w-8 h-8 centered rounded-full"></div>


    <!-- mercury -->
    <div class="absolute animate-[spin_8s_linear_infinite] rounded-full border border-gray-200/40 w-12 h-12 centered">
        <div class="absolute w-2 h-2 bg-blue-300 translate-[3px] rounded-full"></div>
    </div>

    <!-- venus -->
    <div class="absolute animate-[spin_12s_linear_infinite] rounded-full border border-gray-200/40 w-18 h-18 centered">
        <div class="absolute w-2 h-2 bg-gradient-to-b from-white via-orange-200 to-white translate-[6px] rounded-full animate-[spin_2s_linear_infinite]"></div>
    </div>

    <!-- earth -->
    <div class="absolute animate-[spin_16s_linear_infinite] rounded-full border border-gray-200/40 w-24 h-24 centered">
        <div class="absolute w-2 h-2 bg-gradient-to-b from-blue-300 via-green-600 to-blue-400 translate-[9px] rounded-full  animate-[spin_2s_linear_infinite]">
            <div class="w-1 h-1 bg-gray-300 rounded-full -translate-[4px]"></div>
        </div>
    </div>

    <!-- mars -->
     <div class="absolute animate-[spin_24s_linear_infinite] rounded-full border border-gray-200/40 w-30 h-30 centered">
        <div class="absolute w-2 h-2 bg-gradient-to-b from-orange-400 via-red-300 to-orange-400 translate-[13px] rounded-full animate-[spin_2s_linear_infinite]"></div>
    </div>

    <!-- stars -->
    {#each Array(100) as _, i}
    <div  class="w-0.5 h-0.5 bg-white/60 absolute rounded-full animate-pulse" 
          style="top: {Math.random() * 90}vh; left: {Math.random() * 90}vw;
          animation-delay: {Math.floor(Math.random() *250)}ms;"
    ></div>
    {/each}
</div>

<style>
    .centered {
        @apply absolute left-1/2 top-1/2 -translate-1/2;
    }
</style>