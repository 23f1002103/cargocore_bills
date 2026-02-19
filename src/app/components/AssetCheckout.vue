<template>
  <DocumentLayout>
    <div class="space-y-6">
      <!-- Title -->
      <div class="text-center border-b-2 border-blue-900 pb-3">
        <h1 class="text-[22px] font-bold text-blue-900 tracking-wide">SERVICE KIT CHECKOUT SLIP</h1>
        <p class="text-[11px] text-gray-600 mt-1">Equipment & Asset Assignment Form</p>
      </div>

      <!-- Order & Driver Details -->
      <div class="bg-gradient-to-r from-blue-900 to-blue-700 text-white p-5 rounded-lg">
        <div class="grid grid-cols-2 gap-4 mb-3">
          <div>
            <p class="text-[10px] opacity-80 uppercase">Order ID</p>
            <p class="text-[15px] font-bold">CC-12345</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Checkout Date</p>
            <p class="text-[13px] font-semibold">December 20, 2024 - 08:30 AM</p>
          </div>
        </div>
        <div class="pt-3 border-t border-white/20">
          <p class="text-[10px] opacity-80 uppercase mb-1">Assigned Driver</p>
          <p class="text-[15px] font-bold">Prakash Reddy</p>
          <div class="grid grid-cols-3 gap-3 mt-2 text-[11px]">
            <div>
              <p class="text-[9px] opacity-80">Employee ID</p>
              <p class="font-semibold">DRV-8765</p>
            </div>
            <div>
              <p class="text-[9px] opacity-80">License No.</p>
              <p class="font-semibold">KA07-20210012345</p>
            </div>
            <div>
              <p class="text-[9px] opacity-80">Contact</p>
              <p class="font-semibold">+91 98765 55555</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Vehicle Details -->
      <div class="bg-gray-50 p-4 rounded-lg border border-gray-300">
        <h3 class="text-[11px] font-bold text-gray-800 mb-2">VEHICLE DETAILS</h3>
        <div class="grid grid-cols-3 gap-3 text-[11px]">
          <div>
            <p class="text-[10px] text-gray-600">Vehicle Number</p>
            <p class="font-semibold text-gray-900">KA 01 MN 5678</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600">Vehicle Type</p>
            <p class="font-semibold text-gray-900">14 ft Covered Truck</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600">Odometer Reading</p>
            <p class="font-semibold text-gray-900">45,234 km</p>
          </div>
        </div>
      </div>

      <!-- Equipment Checklist -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">EQUIPMENT CHECKOUT LIST</h3>
        <table class="w-full text-[11px]">
          <thead>
            <tr class="bg-gray-200 text-gray-700">
              <th class="text-left p-2 border border-gray-300">Item Description</th>
              <th class="text-center p-2 border border-gray-300 w-[60px]">Asset ID</th>
              <th class="text-center p-2 border border-gray-300 w-[60px]">Qty</th>
              <th class="text-center p-2 border border-gray-300 w-[80px]">Condition</th>
              <th class="text-center p-2 border border-gray-300 w-[50px]">✓</th>
            </tr>
          </thead>
          <tbody class="text-gray-800">
            <tr>
              <td class="p-2 border border-gray-300 font-semibold">Hand Trolley / Moving Dolly</td>
              <td class="text-center p-2 border border-gray-300">HT-245</td>
              <td class="text-center p-2 border border-gray-300">2</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">Furniture Blankets (Quilted)</td>
              <td class="text-center p-2 border border-gray-300">FB-112</td>
              <td class="text-center p-2 border border-gray-300">6</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
            </tr>
            <tr>
              <td class="p-2 border border-gray-300">Ratchet Tie-Down Straps</td>
              <td class="text-center p-2 border border-gray-300">TS-678</td>
              <td class="text-center p-2 border border-gray-300">6</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">Tool Kit (Screwdrivers, Wrenches)</td>
              <td class="text-center p-2 border border-gray-300">TK-034</td>
              <td class="text-center p-2 border border-gray-300">1</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
            </tr>
            <tr>
              <td class="p-2 border border-gray-300">Fire Extinguisher (ABC Type)</td>
              <td class="text-center p-2 border border-gray-300">FE-089</td>
              <td class="text-center p-2 border border-gray-300">1</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">First Aid Kit (Certified)</td>
              <td class="text-center p-2 border border-gray-300">FA-156</td>
              <td class="text-center p-2 border border-gray-300">1</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
            </tr>
            <tr>
              <td class="p-2 border border-gray-300">GPS Tracking Device</td>
              <td class="text-center p-2 border border-gray-300">GPS-412</td>
              <td class="text-center p-2 border border-gray-300">1</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Active</td>
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">Digital Weighing Scale</td>
              <td class="text-center p-2 border border-gray-300">WS-234</td>
              <td class="text-center p-2 border border-gray-300">1</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
            </tr>
            <tr>
              <td class="p-2 border border-gray-300">Reflective Safety Vests</td>
              <td class="text-center p-2 border border-gray-300">SV-445</td>
              <td class="text-center p-2 border border-gray-300">4</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">Warning Triangles</td>
              <td class="text-center p-2 border border-gray-300">WT-789</td>
              <td class="text-center p-2 border border-gray-300">2</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Photo Documentation -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">PHOTO DOCUMENTATION</h3>
        <div class="grid grid-cols-3 gap-3">
          <div class="border-2 border-dashed border-gray-300 rounded p-3 text-center">
            <div class="w-full h-[100px] bg-gray-100 rounded flex items-center justify-center mb-2">
              <span class="text-[30px]">📷</span>
            </div>
            <p class="text-[10px] text-gray-600">Vehicle Front View</p>
          </div>
          <div class="border-2 border-dashed border-gray-300 rounded p-3 text-center">
            <div class="w-full h-[100px] bg-gray-100 rounded flex items-center justify-center mb-2">
              <span class="text-[30px]">📷</span>
            </div>
            <p class="text-[10px] text-gray-600">Equipment in Vehicle</p>
          </div>
          <div class="border-2 border-dashed border-gray-300 rounded p-3 text-center">
            <div class="w-full h-[100px] bg-gray-100 rounded flex items-center justify-center mb-2">
              <span class="text-[30px]">📷</span>
            </div>
            <p class="text-[10px] text-gray-600">Odometer Reading</p>
          </div>
        </div>
      </div>

      <!-- Signatures -->
      <div class="border-2 border-gray-300 rounded-lg p-4">
        <h3 class="text-[11px] font-bold text-gray-800 mb-3">CHECKOUT VERIFICATION</h3>
        <div class="grid grid-cols-2 gap-4">
          <div>
            <p class="text-[10px] text-gray-600 mb-2">Driver Acknowledgment:</p>
            <div class="border-b-2 border-gray-400 h-[50px] mb-2"></div>
            <p class="text-[9px] text-gray-700">I acknowledge receipt of above equipment in good condition</p>
            <p class="text-[9px] text-gray-500 mt-2">Driver Name: ___________________</p>
            <p class="text-[9px] text-gray-500">Date & Time: ___________________</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 mb-2">Warehouse Supervisor:</p>
            <div class="border-b-2 border-gray-400 h-[50px] mb-2"></div>
            <p class="text-[9px] text-gray-700">Equipment checked and issued as per list</p>
            <p class="text-[9px] text-gray-500 mt-2">Supervisor Name: ___________________</p>
            <p class="text-[9px] text-gray-500">Date & Time: ___________________</p>
          </div>
        </div>
      </div>

      <!-- Return Section -->
      <div class="bg-amber-50 border-2 border-amber-400 rounded-lg p-4">
        <h3 class="text-[11px] font-bold text-amber-800 mb-3">RETURN CHECKIN (To be filled on return)</h3>
        <div class="grid grid-cols-3 gap-3 mb-3">
          <div>
            <p class="text-[10px] text-gray-600">Return Date</p>
            <div class="border-b border-amber-400 h-[25px]"></div>
          </div>
          <div>
            <p class="text-[10px] text-gray-600">Return Time</p>
            <div class="border-b border-amber-400 h-[25px]"></div>
          </div>
          <div>
            <p class="text-[10px] text-gray-600">Odometer Reading</p>
            <div class="border-b border-amber-400 h-[25px]"></div>
          </div>
        </div>
        <div class="grid grid-cols-2 gap-3">
          <div>
            <p class="text-[10px] text-gray-600 mb-1">All Equipment Returned:</p>
            <div class="flex gap-3">
              <label class="flex items-center gap-1 text-[10px]">
                <input type="checkbox"> Yes
              </label>
              <label class="flex items-center gap-1 text-[10px]">
                <input type="checkbox"> No (Specify missing items below)
              </label>
            </div>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 mb-1">Equipment Condition:</p>
            <div class="flex gap-3">
              <label class="flex items-center gap-1 text-[10px]">
                <input type="checkbox"> Good
              </label>
              <label class="flex items-center gap-1 text-[10px]">
                <input type="checkbox"> Damaged
              </label>
            </div>
          </div>
        </div>
        <div class="mt-3">
          <p class="text-[10px] text-gray-600 mb-1">Remarks / Damage Report:</p>
          <div class="border border-amber-400 rounded h-[40px] bg-white"></div>
        </div>
        <div class="mt-3 pt-3 border-t border-amber-300">
          <p class="text-[10px] text-gray-600 mb-2">Supervisor Signature (Return):</p>
          <div class="border-b-2 border-amber-600 h-[40px]"></div>
        </div>
      </div>

      <!-- Important Note -->
      <div class="bg-red-50 border-l-4 border-red-500 p-3">
        <p class="text-[10px] font-bold text-red-800 mb-1">⚠ IMPORTANT:</p>
        <ul class="text-[10px] text-gray-700 space-y-1">
          <li>• Driver is responsible for all checked-out equipment</li>
          <li>• Report any damage or loss immediately to operations manager</li>
          <li>• All equipment must be returned in same condition</li>
          <li>• Missing or damaged equipment will be charged to driver account</li>
        </ul>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup lang="ts">
import DocumentLayout from './DocumentLayout.vue';
</script>
