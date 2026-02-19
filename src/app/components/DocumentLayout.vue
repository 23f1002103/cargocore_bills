<template>
  <div 
    class="relative bg-white w-[794px] min-h-[1123px] mx-auto shadow-lg pb-[55px]" 
    style="font-family: system-ui, -apple-system, sans-serif"
  >
    <!-- Header with gradient -->
    <div 
      class="h-[100px] flex items-center px-8"
      style="background: linear-gradient(to right, #0A2540 0%, #1e4976 50%, #4fb3d9 100%)"
    >
      <img :src="logo" alt="CargoCore" class="h-[60px] w-[60px] rounded-full object-cover" />
      <div class="ml-4">
        <div class="text-white text-[24px] font-bold tracking-wide">CARGOCORE</div>
        <div class="text-cyan-200 text-[11px] tracking-wider">Moving What Matters</div>
      </div>
    </div>

    <!-- Watermark -->
    <div class="absolute inset-0 flex items-center justify-center pointer-events-none z-0">
      <img 
        :src="logo" 
        alt="" 
        class="w-[400px] h-[400px] opacity-[0.08] rounded-full object-cover"
        style="filter: brightness(1.2)"
      />
    </div>

    <!-- Content -->
    <div class="relative z-10 px-8 py-4">
      <slot />
    </div>

    <!-- Seal if needed -->
    <div v-if="showSeal" class="absolute bottom-[70px] right-[60px] z-20">
      <img :src="seal" alt="Official Seal" class="w-[100px] h-[100px] rounded-full mix-blend-multiply" />
    </div>

    <!-- Footer -->
    <div class="absolute bottom-0 left-0 right-0 border-t border-gray-300 bg-gray-50 px-8 py-3">
      <p class="text-[9px] text-gray-600 text-center leading-relaxed">
        This is a system-generated document | <span class="font-semibold">CargoCore Logistics Pvt. Ltd.</span> Registered Office: Koramangala, Bangalore, Karnataka - 560034 | www.cargocore.com
      </p>
    </div>
  </div>
</template>

<script setup>
import logo from '../../assets/f27e35eb84d6e7810aa280143872a57f44f6325d.png'
import seal from '../../assets/d5049f13d8040cb86739a20ff59fc7644e086a4b.png'

defineProps({
  showSeal: {
    type: Boolean,
    default: false
  }
})
</script>
