<template>
  <DocumentLayout>
    <div class="space-y-6">
      <!-- Title -->
      <div class="text-center border-b-2 border-blue-900 pb-3">
        <h1 class="text-[22px] font-bold text-blue-900 tracking-wide">DIGITAL PICK LIST</h1>
        <p class="text-[11px] text-gray-600 mt-1">Order {{ order.id }} • Warehouse Fulfillment Sheet</p>
      </div>

      <!-- Order Info -->
      <div class="bg-gradient-to-r from-blue-900 to-blue-700 text-white p-5 rounded-lg">
        <div class="grid grid-cols-4 gap-4">
          <div>
            <p class="text-[10px] opacity-80 uppercase">Order ID</p>
            <p class="text-[15px] font-bold">{{ order.id }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Pick Date</p>
            <p class="text-[13px] font-semibold">{{ order.pickDate }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Move Date</p>
            <p class="text-[13px] font-semibold">{{ order.moveDate }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Priority</p>
            <p class="text-[13px] font-semibold">{{ order.priority }}</p>
          </div>
        </div>
        <div class="mt-3 pt-3 border-t border-white/20">
          <p class="text-[10px] opacity-80 uppercase mb-1">Picker Assigned</p>
          <p class="text-[13px] font-semibold">{{ picker.name }} ({{ picker.employeeId }}) | Team Lead: {{ teamLead }}</p>
        </div>
      </div>

      <!-- Walking Path -->
      <div class="bg-blue-50 border-2 border-blue-300 p-4 rounded-lg">
        <p class="text-[11px] font-bold text-blue-900 mb-2">🚶 OPTIMIZED WALKING PATH</p>
        <div class="flex items-center gap-2 text-[11px] text-gray-700">
          <span class="bg-blue-600 text-white px-2 py-1 rounded font-semibold">START</span>
          <template v-for="(aisle, i) in walkingPath" :key="i">
            <span>→</span>
            <span class="bg-white px-2 py-1 rounded border border-blue-300">{{ aisle }}</span>
          </template>
          <span>→</span>
          <span class="bg-green-600 text-white px-2 py-1 rounded font-semibold">LOADING DOCK</span>
        </div>
        <p class="text-[10px] text-gray-600 mt-2">Estimated time: {{ pathTime }} | Total distance: {{ pathDistance }}</p>
      </div>

      <!-- Pick List Table -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">ITEMS TO PICK ({{ items.length }} ITEMS)</h3>
        <table class="w-full text-[10px]">
          <thead>
            <tr class="bg-gray-200 text-gray-700">
              <th class="text-center p-2 border border-gray-300 w-[40px]">✓</th>
              <th class="text-left p-2 border border-gray-300">Item Description</th>
              <th class="text-center p-2 border border-gray-300 w-[80px]">Location</th>
              <th class="text-center p-2 border border-gray-300 w-[50px]">Qty</th>
              <th class="text-center p-2 border border-gray-300 w-[80px]">Bin/Rack</th>
            </tr>
          </thead>
          <tbody class="text-gray-800">
            <tr v-for="(item, index) in items" :key="index" :class="index % 2 !== 0 ? 'bg-gray-50' : (index === 0 ? 'bg-blue-50' : '')">
              <td class="text-center p-2 border border-gray-300"><input type="checkbox"></td>
              <td class="p-2 border border-gray-300" :class="index === 0 ? 'font-semibold' : ''">{{ item.description }}</td>
              <td class="text-center p-2 border border-gray-300">{{ item.location }}</td>
              <td class="text-center p-2 border border-gray-300 font-semibold">{{ item.qty }}</td>
              <td class="text-center p-2 border border-gray-300">{{ item.bin }}</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Summary Stats -->
      <div class="grid grid-cols-4 gap-3">
        <div class="bg-gradient-to-br from-blue-600 to-blue-500 text-white p-3 rounded text-center">
          <p class="text-[10px] opacity-90">Total Items</p>
          <p class="text-[20px] font-bold">{{ items.length }}</p>
        </div>
        <div class="bg-gradient-to-br from-green-600 to-green-500 text-white p-3 rounded text-center">
          <p class="text-[10px] opacity-90">Total Quantity</p>
          <p class="text-[20px] font-bold">{{ items.reduce((s, i) => s + i.qty, 0) }}</p>
        </div>
        <div class="bg-gradient-to-br from-purple-600 to-purple-500 text-white p-3 rounded text-center">
          <p class="text-[10px] opacity-90">Aisles to Visit</p>
          <p class="text-[20px] font-bold">{{ new Set(items.map(i => i.location)).size }}</p>
        </div>
        <div class="bg-gradient-to-br from-orange-600 to-orange-500 text-white p-3 rounded text-center">
          <p class="text-[10px] opacity-90">Est. Time</p>
          <p class="text-[20px] font-bold">{{ pathTime }}</p>
        </div>
      </div>

      <!-- Verification -->
      <div class="border-2 border-gray-300 rounded-lg p-4">
        <h3 class="text-[11px] font-bold text-gray-800 mb-3">VERIFICATION & HANDOFF</h3>
        <div class="grid grid-cols-2 gap-4">
          <div>
            <p class="text-[10px] text-gray-600 mb-2">Picker Signature:</p>
            <div class="border-b-2 border-gray-400 h-[40px]"></div>
            <p class="text-[9px] text-gray-500 mt-1">Name: ___________________ Date: ___________</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 mb-2">Team Lead Verification:</p>
            <div class="border-b-2 border-gray-400 h-[40px]"></div>
            <p class="text-[9px] text-gray-500 mt-1">Name: ___________________ Time: ___________</p>
          </div>
        </div>
      </div>

      <!-- Notes -->
      <div class="bg-amber-50 border-l-4 border-amber-500 p-3">
        <p class="text-[10px] font-bold text-amber-800 mb-1">📝 SPECIAL NOTES:</p>
        <ul class="text-[10px] text-gray-700 space-y-1">
          <li>• Check all boxes for damage before picking</li>
          <li>• Ensure bubble wrap rolls are full (not partially used)</li>
          <li>• Load heavy items at bottom of cart</li>
          <li>• Scan barcode after picking each item (if applicable)</li>
        </ul>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup>
import DocumentLayout from './DocumentLayout.vue';

const props = defineProps({
  order: {
    type: Object,
    default: () => ({ id: 'CC-12345', pickDate: 'Dec 19, 2024', moveDate: 'Dec 20, 2024', priority: 'HIGH' })
  },
  picker: {
    type: Object,
    default: () => ({ name: 'Suresh M.', employeeId: 'EMP-1245' })
  },
  teamLead: { type: String, default: 'Rajesh Kumar' },
  walkingPath: {
    type: Array,
    default: () => ['Aisle A', 'Aisle B', 'Aisle C', 'Aisle D']
  },
  pathTime: { type: String, default: '45 minutes' },
  pathDistance: { type: String, default: '280 meters' },
  items: {
    type: Array,
    default: () => [
      { description: 'Cardboard Moving Boxes - Large (24x18x18)', location: 'Aisle A', qty: 15, bin: 'A-12-C' },
      { description: 'Cardboard Moving Boxes - Medium (18x14x12)', location: 'Aisle A', qty: 13, bin: 'A-12-D' },
      { description: 'Bubble Wrap Roll (500mm x 100m)', location: 'Aisle A', qty: 3, bin: 'A-08-B' },
      { description: 'Packing Tape - Brown (2 inch x 65m)', location: 'Aisle A', qty: 8, bin: 'A-05-A' },
      { description: 'Furniture Blankets - Quilted (72x80 inch)', location: 'Aisle B', qty: 6, bin: 'B-15-E' },
      { description: 'Stretch Wrap Film - Clear (450mm x 300m)', location: 'Aisle B', qty: 4, bin: 'B-10-C' },
      { description: 'Foam Sheets - Protective (24x36 inch)', location: 'Aisle B', qty: 20, bin: 'B-07-D' },
      { description: 'Permanent Markers - Black (Pack of 4)', location: 'Aisle C', qty: 2, bin: 'C-03-A' },
      { description: 'Label Stickers - Fragile (Red, Pack of 100)', location: 'Aisle C', qty: 1, bin: 'C-03-B' },
      { description: 'Hand Trolley / Dolly (300 kg capacity)', location: 'Aisle C', qty: 2, bin: 'C-18-F' },
      { description: 'Ratchet Tie-Down Straps (25 ft)', location: 'Aisle C', qty: 6, bin: 'C-20-B' },
      { description: 'Furniture Sliders / Glides (Set of 16)', location: 'Aisle D', qty: 2, bin: 'D-05-C' },
      { description: 'Tool Kit - Basic (Screwdriver, Wrench set)', location: 'Aisle D', qty: 1, bin: 'D-09-A' },
      { description: 'Safety Gloves - Cotton (Pack of 6 pairs)', location: 'Aisle D', qty: 1, bin: 'D-02-E' },
      { description: 'Utility Knife / Box Cutter (Retractable)', location: 'Aisle D', qty: 2, bin: 'D-02-F' }
    ]
  }
})
</script>
