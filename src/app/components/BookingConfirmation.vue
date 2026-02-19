<template>
  <DocumentLayout>
    <div class="space-y-6">
      <!-- Title -->
      <div class="text-center border-b-2 border-green-600 pb-3">
        <h1 class="text-[22px] font-bold text-green-700 tracking-wide">BOOKING CONFIRMATION</h1>
        <p class="text-[11px] text-gray-600 mt-1">Your move has been successfully confirmed</p>
      </div>

      <!-- Status Badge -->
      <div class="text-center">
        <div class="inline-block bg-green-100 border-2 border-green-500 px-6 py-3 rounded-full">
          <span class="text-[16px] font-bold text-green-700">✓ CONFIRMED</span>
        </div>
      </div>

      <!-- Order Details -->
      <div class="bg-gradient-to-r from-blue-900 to-blue-700 text-white p-5 rounded-lg">
        <div class="grid grid-cols-2 gap-4">
          <div>
            <p class="text-[10px] opacity-80 uppercase">Order ID</p>
            <p class="text-[18px] font-bold">CC-12345</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Booking Date</p>
            <p class="text-[13px] font-semibold">December 16, 2024</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Move Date</p>
            <p class="text-[13px] font-semibold">December 20, 2024</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Time Slot</p>
            <p class="text-[13px] font-semibold">09:00 AM - 12:00 PM</p>
          </div>
        </div>
      </div>

      <!-- Customer Details -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">CUSTOMER INFORMATION</h3>
        <div class="grid grid-cols-2 gap-4 bg-gray-50 p-4 rounded-lg">
          <div>
            <p class="text-[10px] text-gray-600 uppercase mb-1">Full Name</p>
            <p class="text-[13px] font-semibold text-gray-900">Sarah Khan</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 uppercase mb-1">Contact Number</p>
            <p class="text-[13px] font-semibold text-gray-900">+91 98765 43210</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 uppercase mb-1">Email Address</p>
            <p class="text-[13px] font-semibold text-gray-900">sarah.khan@email.com</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 uppercase mb-1">Alternate Number</p>
            <p class="text-[13px] font-semibold text-gray-900">+91 87654 32109</p>
          </div>
        </div>
      </div>

      <!-- Address Details -->
      <div class="grid grid-cols-2 gap-4">
        <div class="bg-blue-50 p-4 rounded-lg border border-blue-200">
          <p class="text-[11px] font-bold text-blue-800 mb-2">📍 PICKUP ADDRESS</p>
          <p class="text-[12px] font-semibold text-gray-900">123 Oak Street, Whitefield</p>
          <p class="text-[11px] text-gray-600">Bangalore, Karnataka - 560066</p>
          <p class="text-[10px] text-gray-600 mt-2">Floor: Ground | Lift: Available</p>
        </div>
        <div class="bg-green-50 p-4 rounded-lg border border-green-200">
          <p class="text-[11px] font-bold text-green-800 mb-2">📍 DELIVERY ADDRESS</p>
          <p class="text-[12px] font-semibold text-gray-900">456 Maple Avenue, Indiranagar</p>
          <p class="text-[11px] text-gray-600">Bangalore, Karnataka - 560038</p>
          <p class="text-[10px] text-gray-600 mt-2">Floor: 2nd | Lift: Available</p>
        </div>
      </div>

      <!-- Services Booked -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">SERVICES BOOKED</h3>
        <div class="grid grid-cols-2 gap-3">
          <div class="flex items-center gap-2 bg-gray-50 p-3 rounded">
            <div class="text-green-600 text-[18px]">✓</div>
            <div>
              <p class="text-[11px] font-semibold text-gray-900">Professional Packing</p>
              <p class="text-[9px] text-gray-600">Complete packing service</p>
            </div>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-3 rounded">
            <div class="text-green-600 text-[18px]">✓</div>
            <div>
              <p class="text-[11px] font-semibold text-gray-900">Loading & Unloading</p>
              <p class="text-[9px] text-gray-600">4 skilled workers</p>
            </div>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-3 rounded">
            <div class="text-green-600 text-[18px]">✓</div>
            <div>
              <p class="text-[11px] font-semibold text-gray-900">Transportation</p>
              <p class="text-[9px] text-gray-600">14 ft covered truck</p>
            </div>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-3 rounded">
            <div class="text-green-600 text-[18px]">✓</div>
            <div>
              <p class="text-[11px] font-semibold text-gray-900">Transit Insurance</p>
              <p class="text-[9px] text-gray-600">Up to ₹50,000 coverage</p>
            </div>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-3 rounded">
            <div class="text-green-600 text-[18px]">✓</div>
            <div>
              <p class="text-[11px] font-semibold text-gray-900">GPS Tracking</p>
              <p class="text-[9px] text-gray-600">Real-time location updates</p>
            </div>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-3 rounded">
            <div class="text-green-600 text-[18px]">✓</div>
            <div>
              <p class="text-[11px] font-semibold text-gray-900">Unpacking Service</p>
              <p class="text-[9px] text-gray-600">Basic unpacking included</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Payment Summary -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">PAYMENT SUMMARY</h3>
        <table class="w-full text-[11px]">
          <tbody class="text-gray-800">
            <tr class="border-b border-gray-200">
              <td class="py-2">Total Service Amount</td>
              <td class="text-right py-2 font-semibold">₹4,500</td>
            </tr>
            <tr class="border-b border-gray-200 bg-green-50">
              <td class="py-2 text-green-700">Advance Paid (30%)</td>
              <td class="text-right py-2 font-semibold text-green-700">₹1,350</td>
            </tr>
            <tr class="border-b border-gray-200">
              <td class="py-2">Payment Mode</td>
              <td class="text-right py-2 font-semibold">UPI / Online Transfer</td>
            </tr>
            <tr class="border-b border-gray-200">
              <td class="py-2">Transaction ID</td>
              <td class="text-right py-2 font-semibold">TXN20241216789456</td>
            </tr>
            <tr class="bg-amber-50 font-bold">
              <td class="py-2 text-amber-800">Balance Due (at delivery)</td>
              <td class="text-right py-2 text-amber-800">₹3,150</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Important Instructions -->
      <div class="bg-blue-50 border-l-4 border-blue-600 p-4">
        <p class="text-[11px] font-bold text-blue-900 mb-2">📋 IMPORTANT INSTRUCTIONS:</p>
        <ul class="text-[10px] text-gray-700 space-y-1">
          <li>• Please keep all valuable items (jewelry, documents, cash) separately</li>
          <li>• Our team will arrive 30 minutes before the scheduled time</li>
          <li>• Ensure parking space is available for the truck</li>
          <li>• Balance payment can be made via Cash/UPI/Card after delivery</li>
          <li>• For any queries, contact: 1800-CARGO-00 or support@cargocore.com</li>
        </ul>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup lang="ts">
import DocumentLayout from './DocumentLayout.vue';
</script>
