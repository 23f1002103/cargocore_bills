<template>
  <DocumentLayout>
    <div class="space-y-6">
      <!-- Title -->
      <div class="text-center border-b-2 border-blue-900 pb-3">
        <h1 class="text-[22px] font-bold text-blue-900 tracking-wide">AI VOLUME ESTIMATE REPORT</h1>
        <p class="text-[11px] text-gray-600 mt-1">Computer Vision Analysis</p>
      </div>

      <!-- Order Details -->
      <div class="grid grid-cols-2 gap-4 bg-gray-50 p-4 rounded-lg">
        <div>
          <p class="text-[10px] text-gray-600 uppercase">Order ID</p>
          <p class="text-[13px] font-semibold text-gray-900">CC-12345</p>
        </div>
        <div>
          <p class="text-[10px] text-gray-600 uppercase">Customer</p>
          <p class="text-[13px] font-semibold text-gray-900">Sarah Khan</p>
        </div>
        <div>
          <p class="text-[10px] text-gray-600 uppercase">Estimate Date</p>
          <p class="text-[13px] font-semibold text-gray-900">December 15, 2024</p>
        </div>
        <div>
          <p class="text-[10px] text-gray-600 uppercase">Analysis Method</p>
          <p class="text-[13px] font-semibold text-gray-900">AI Photo Analysis</p>
        </div>
      </div>

      <!-- Photo Upload Section -->
      <div class="border-2 border-dashed border-blue-300 rounded-lg p-6 bg-blue-50">
        <div class="text-center">
          <div class="w-full h-[180px] bg-white rounded-lg flex items-center justify-center border border-gray-300">
            <div>
              <div class="text-blue-600 text-[40px] mb-2">📷</div>
              <p class="text-[12px] text-gray-600">Photos Uploaded: 8 images</p>
              <p class="text-[10px] text-gray-500">Living room, Bedroom, Kitchen, Storage</p>
            </div>
          </div>
        </div>
      </div>

      <!-- AI Analysis Results -->
      <div class="bg-gradient-to-r from-blue-900 to-blue-700 text-white p-5 rounded-lg">
        <h2 class="text-[15px] font-bold mb-4">AI ANALYSIS RESULTS</h2>
        <div class="grid grid-cols-3 gap-4">
          <div class="bg-white/10 backdrop-blur-sm p-3 rounded">
            <p class="text-[10px] opacity-90">Estimated Boxes</p>
            <p class="text-[24px] font-bold">28</p>
          </div>
          <div class="bg-white/10 backdrop-blur-sm p-3 rounded">
            <p class="text-[10px] opacity-90">Labor Required</p>
            <p class="text-[24px] font-bold">4</p>
          </div>
          <div class="bg-white/10 backdrop-blur-sm p-3 rounded">
            <p class="text-[10px] opacity-90">Truck Size</p>
            <p class="text-[18px] font-bold mt-1">14 ft</p>
          </div>
        </div>
        <div class="mt-4 flex items-center justify-center gap-2 bg-white/10 p-2 rounded">
          <span class="text-[11px]">Confidence Level:</span>
          <div class="flex-1 bg-white/20 h-[12px] rounded-full overflow-hidden max-w-[200px]">
            <div class="bg-green-400 h-full" style="width: 92%"></div>
          </div>
          <span class="text-[13px] font-bold">92%</span>
        </div>
      </div>

      <!-- Detailed Breakdown -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">DETAILED BREAKDOWN</h3>
        <table class="w-full text-[11px]">
          <thead>
            <tr class="bg-gray-200 text-gray-700">
              <th class="text-left p-2 border border-gray-300">Room</th>
              <th class="text-center p-2 border border-gray-300">Items Detected</th>
              <th class="text-center p-2 border border-gray-300">Boxes Needed</th>
              <th class="text-center p-2 border border-gray-300">Volume (cu.ft)</th>
            </tr>
          </thead>
          <tbody class="text-gray-800">
            <tr>
              <td class="p-2 border border-gray-300">Living Room</td>
              <td class="text-center p-2 border border-gray-300">45</td>
              <td class="text-center p-2 border border-gray-300">8</td>
              <td class="text-center p-2 border border-gray-300">120</td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">Master Bedroom</td>
              <td class="text-center p-2 border border-gray-300">38</td>
              <td class="text-center p-2 border border-gray-300">10</td>
              <td class="text-center p-2 border border-gray-300">150</td>
            </tr>
            <tr>
              <td class="p-2 border border-gray-300">Kitchen</td>
              <td class="text-center p-2 border border-gray-300">52</td>
              <td class="text-center p-2 border border-gray-300">6</td>
              <td class="text-center p-2 border border-gray-300">80</td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">Storage/Others</td>
              <td class="text-center p-2 border border-gray-300">21</td>
              <td class="text-center p-2 border border-gray-300">4</td>
              <td class="text-center p-2 border border-gray-300">60</td>
            </tr>
            <tr class="bg-blue-100 font-bold">
              <td class="p-2 border border-gray-300">TOTAL</td>
              <td class="text-center p-2 border border-gray-300">156</td>
              <td class="text-center p-2 border border-gray-300">28</td>
              <td class="text-center p-2 border border-gray-300">410</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Note -->
      <div class="bg-amber-50 border-l-4 border-amber-500 p-3 text-[10px] text-gray-700">
        <p class="font-semibold mb-1">📌 Note:</p>
        <p>This is an AI-generated estimate based on photo analysis. Final requirements may vary slightly upon physical inspection. Our team will confirm exact requirements before the move.</p>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup>
import DocumentLayout from './DocumentLayout.vue';
</script>
