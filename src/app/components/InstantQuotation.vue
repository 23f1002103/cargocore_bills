<template>
  <DocumentLayout>
    <div class="space-y-6">
      <!-- Title -->
      <div class="text-center border-b-2 border-blue-900 pb-3">
        <h1 class="text-[22px] font-bold text-blue-900 tracking-wide">INSTANT QUOTATION</h1>
        <p class="text-[11px] text-gray-600 mt-1">Valid for 7 days from issue date</p>
      </div>

      <!-- Customer & Route Info -->
      <div class="grid grid-cols-2 gap-4">
        <div class="bg-gray-50 p-4 rounded-lg">
          <h3 class="text-[11px] font-bold text-gray-700 mb-2">CUSTOMER DETAILS</h3>
          <p class="text-[13px] font-semibold text-gray-900">Sarah Khan</p>
          <p class="text-[11px] text-gray-600">Phone: +91 98765 43210</p>
          <p class="text-[11px] text-gray-600">Email: sarah.khan@email.com</p>
        </div>
        <div class="bg-gray-50 p-4 rounded-lg">
          <h3 class="text-[11px] font-bold text-gray-700 mb-2">QUOTATION INFO</h3>
          <p class="text-[11px] text-gray-600">Quote ID: <span class="font-semibold text-gray-900">QT-2024-0567</span></p>
          <p class="text-[11px] text-gray-600">Date: <span class="font-semibold text-gray-900">December 15, 2024</span></p>
          <p class="text-[11px] text-gray-600">Valid Until: <span class="font-semibold text-gray-900">December 22, 2024</span></p>
        </div>
      </div>

      <!-- Route -->
      <div class="bg-blue-50 p-4 rounded-lg border border-blue-200">
        <div class="flex items-center justify-between">
          <div class="flex-1">
            <p class="text-[10px] text-gray-600 uppercase mb-1">FROM</p>
            <p class="text-[12px] font-semibold text-gray-900">123 Oak Street, Whitefield</p>
            <p class="text-[10px] text-gray-600">Bangalore - 560066</p>
          </div>
          <div class="text-[24px] text-blue-600 mx-4">→</div>
          <div class="flex-1">
            <p class="text-[10px] text-gray-600 uppercase mb-1">TO</p>
            <p class="text-[12px] font-semibold text-gray-900">456 Maple Avenue, Indiranagar</p>
            <p class="text-[10px] text-gray-600">Bangalore - 560038</p>
          </div>
        </div>
        <div class="mt-3 pt-3 border-t border-blue-200 flex justify-between text-[11px]">
          <span class="text-gray-600">Distance: <span class="font-semibold text-gray-900">18.5 km</span></span>
          <span class="text-gray-600">Move Date: <span class="font-semibold text-gray-900">December 20, 2024</span></span>
        </div>
      </div>

      <!-- Total Amount Box -->
      <div class="bg-gradient-to-r from-green-600 to-green-500 text-white p-6 rounded-lg text-center">
        <p class="text-[12px] opacity-90 mb-1">TOTAL QUOTATION AMOUNT</p>
        <p class="text-[42px] font-bold">₹4,500</p>
        <p class="text-[11px] opacity-90 mt-1">All inclusive • No hidden charges</p>
      </div>

      <!-- Detailed Breakdown -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">PRICE BREAKDOWN</h3>
        <table class="w-full text-[11px]">
          <thead>
            <tr class="bg-gray-200 text-gray-700">
              <th class="text-left p-2 border border-gray-300">Service Component</th>
              <th class="text-left p-2 border border-gray-300">Description</th>
              <th class="text-right p-2 border border-gray-300">Amount</th>
            </tr>
          </thead>
          <tbody class="text-gray-800">
            <tr>
              <td class="p-2 border border-gray-300 font-semibold">Transport Charges</td>
              <td class="p-2 border border-gray-300">14 ft truck, 18.5 km distance</td>
              <td class="text-right p-2 border border-gray-300">₹1,800</td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300 font-semibold">Labor Charges</td>
              <td class="p-2 border border-gray-300">4 skilled workers (loading & unloading)</td>
              <td class="text-right p-2 border border-gray-300">₹1,600</td>
            </tr>
            <tr>
              <td class="p-2 border border-gray-300 font-semibold">Packing Materials</td>
              <td class="p-2 border border-gray-300">28 boxes, bubble wrap, tape, etc.</td>
              <td class="text-right p-2 border border-gray-300">₹700</td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300 font-semibold">Packing Service</td>
              <td class="p-2 border border-gray-300">Professional packing by our team</td>
              <td class="text-right p-2 border border-gray-300">₹400</td>
            </tr>
            <tr>
              <td class="p-2 border border-gray-300 font-semibold">GST (18%)</td>
              <td class="p-2 border border-gray-300">Tax on total service amount</td>
              <td class="text-right p-2 border border-gray-300">₹0</td>
            </tr>
            <tr class="bg-blue-100 font-bold text-[12px]">
              <td class="p-2 border border-gray-300" colspan="2">GRAND TOTAL</td>
              <td class="text-right p-2 border border-gray-300">₹4,500</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Services Included -->
      <div class="grid grid-cols-2 gap-3">
        <div class="bg-green-50 p-3 rounded border border-green-200">
          <p class="text-[10px] font-bold text-green-800 mb-2">✓ INCLUDED SERVICES</p>
          <ul class="text-[10px] text-gray-700 space-y-1">
            <li>• Door-to-door pickup & delivery</li>
            <li>• Professional packing team</li>
            <li>• Transit insurance coverage</li>
            <li>• Real-time GPS tracking</li>
          </ul>
        </div>
        <div class="bg-amber-50 p-3 rounded border border-amber-200">
          <p class="text-[10px] font-bold text-amber-800 mb-2">⚠ TERMS & CONDITIONS</p>
          <ul class="text-[10px] text-gray-700 space-y-1">
            <li>• 30% advance payment required</li>
            <li>• Final price may vary by ±10%</li>
            <li>• Subject to physical verification</li>
            <li>• Valid for single floor only</li>
          </ul>
        </div>
      </div>

      <!-- Book Now Section -->
      <div class="bg-gradient-to-r from-blue-900 to-blue-700 text-white p-5 rounded-lg text-center">
        <h3 class="text-[14px] font-bold mb-2">READY TO BOOK?</h3>
        <p class="text-[11px] opacity-90 mb-3">Confirm your booking now and get 5% discount on advance payment</p>
        <div class="flex gap-3 justify-center">
          <div class="bg-white text-blue-900 px-6 py-2 rounded font-semibold text-[11px]">
            📞 CALL: 1800-CARGO-00
          </div>
          <div class="bg-green-500 text-white px-6 py-2 rounded font-semibold text-[11px]">
            ✓ BOOK ONLINE
          </div>
        </div>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup>
import DocumentLayout from './DocumentLayout.vue';
</script>
