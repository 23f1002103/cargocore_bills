<template>
  <DocumentLayout>
    <div class="space-y-6">
      <!-- Title -->
      <div class="text-center border-b-2 border-green-700 pb-3">
        <h1 class="text-[22px] font-bold text-green-700 tracking-wide">PROOF OF DELIVERY</h1>
        <p class="text-[11px] text-gray-600 mt-1">Delivery Completion & Customer Acceptance</p>
      </div>

      <!-- Delivery Status -->
      <div class="text-center">
        <div class="inline-block bg-green-100 border-2 border-green-600 px-8 py-3 rounded-full">
          <span class="text-[18px] font-bold text-green-700">✓ DELIVERED SUCCESSFULLY</span>
        </div>
      </div>

      <!-- Order & Delivery Info -->
      <div class="bg-gradient-to-r from-green-700 to-green-600 text-white p-5 rounded-lg">
        <div class="grid grid-cols-3 gap-4">
          <div>
            <p class="text-[10px] opacity-80 uppercase">Order ID</p>
            <p class="text-[15px] font-bold">CC-12345</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Delivery Date</p>
            <p class="text-[13px] font-semibold">December 20, 2024</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Delivery Time</p>
            <p class="text-[13px] font-semibold">01:45 PM</p>
          </div>
        </div>
        <div class="mt-3 pt-3 border-t border-white/20 grid grid-cols-2 gap-4">
          <div>
            <p class="text-[10px] opacity-80 uppercase mb-1">Customer</p>
            <p class="text-[13px] font-semibold">Sarah Khan | +91 98765 43210</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase mb-1">Driver</p>
            <p class="text-[13px] font-semibold">Prakash Reddy (DRV-8765)</p>
          </div>
        </div>
      </div>

      <!-- Delivery Address -->
      <div class="bg-blue-50 p-4 rounded-lg border border-blue-200">
        <h3 class="text-[11px] font-bold text-blue-900 mb-2">📍 DELIVERY ADDRESS</h3>
        <p class="text-[13px] font-semibold text-gray-900">456 Maple Avenue, Indiranagar</p>
        <p class="text-[11px] text-gray-700">Bangalore, Karnataka - 560038</p>
        <div class="mt-2 pt-2 border-t border-blue-200 grid grid-cols-2 gap-2 text-[10px]">
          <div>Floor: <span class="font-semibold">2nd Floor</span></div>
          <div>Lift Available: <span class="font-semibold">Yes</span></div>
        </div>
      </div>

      <!-- Delivery Photos -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">DELIVERY PHOTO DOCUMENTATION</h3>
        <div class="grid grid-cols-3 gap-3">
          <div class="border-2 border-gray-300 rounded p-3 text-center bg-gray-50">
            <div class="w-full h-[100px] bg-gray-200 rounded flex items-center justify-center mb-2">
              <span class="text-[35px]">📷</span>
            </div>
            <p class="text-[10px] text-gray-700 font-semibold">Before Unloading</p>
            <p class="text-[9px] text-gray-500">12:05 PM</p>
          </div>
          <div class="border-2 border-gray-300 rounded p-3 text-center bg-gray-50">
            <div class="w-full h-[100px] bg-gray-200 rounded flex items-center justify-center mb-2">
              <span class="text-[35px]">📷</span>
            </div>
            <p class="text-[10px] text-gray-700 font-semibold">Items at Location</p>
            <p class="text-[9px] text-gray-500">01:20 PM</p>
          </div>
          <div class="border-2 border-gray-300 rounded p-3 text-center bg-gray-50">
            <div class="w-full h-[100px] bg-gray-200 rounded flex items-center justify-center mb-2">
              <span class="text-[35px]">📷</span>
            </div>
            <p class="text-[10px] text-gray-700 font-semibold">After Placement</p>
            <p class="text-[9px] text-gray-500">01:42 PM</p>
          </div>
        </div>
      </div>

      <!-- GPS Verification -->
      <div class="bg-purple-50 border-2 border-purple-300 p-4 rounded-lg">
        <h3 class="text-[11px] font-bold text-purple-900 mb-3">📍 GPS LOCATION STAMP</h3>
        <div class="grid grid-cols-2 gap-4 text-[11px]">
          <div>
            <p class="text-gray-600">GPS Coordinates:</p>
            <p class="font-semibold text-gray-900">12.9716° N, 77.5946° E</p>
          </div>
          <div>
            <p class="text-gray-600">Location Accuracy:</p>
            <p class="font-semibold text-green-600">± 5 meters (High)</p>
          </div>
          <div>
            <p class="text-gray-600">Timestamp:</p>
            <p class="font-semibold text-gray-900">Dec 20, 2024 01:45:23 PM</p>
          </div>
          <div>
            <p class="text-gray-600">Location Verified:</p>
            <p class="font-semibold text-green-600">✓ Match Confirmed</p>
          </div>
        </div>
      </div>

      <!-- Items Delivered -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">ITEMS DELIVERED</h3>
        <table class="w-full text-[11px]">
          <thead>
            <tr class="bg-gray-200 text-gray-700">
              <th class="text-left p-2 border border-gray-300">Description</th>
              <th class="text-center p-2 border border-gray-300 w-[80px]">Quantity</th>
              <th class="text-center p-2 border border-gray-300 w-[100px]">Condition</th>
              <th class="text-center p-2 border border-gray-300 w-[60px]">Status</th>
            </tr>
          </thead>
          <tbody class="text-gray-800">
            <tr>
              <td class="p-2 border border-gray-300">Large Cardboard Boxes (Sealed)</td>
              <td class="text-center p-2 border border-gray-300">15</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">✓</td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">Medium Cardboard Boxes (Sealed)</td>
              <td class="text-center p-2 border border-gray-300">13</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">✓</td>
            </tr>
            <tr>
              <td class="p-2 border border-gray-300">Furniture Items (Protected)</td>
              <td class="text-center p-2 border border-gray-300">8</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">✓</td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">Appliances (Bubble Wrapped)</td>
              <td class="text-center p-2 border border-gray-300">4</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">Good</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">✓</td>
            </tr>
            <tr class="bg-green-100 font-bold">
              <td class="p-2 border border-gray-300">TOTAL ITEMS</td>
              <td class="text-center p-2 border border-gray-300">40</td>
              <td class="text-center p-2 border border-gray-300 text-green-700">All Good</td>
              <td class="text-center p-2 border border-gray-300 text-green-700">✓</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Services Completed -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">SERVICES COMPLETED</h3>
        <div class="grid grid-cols-2 gap-3">
          <div class="flex items-center gap-2 bg-green-50 p-3 rounded border border-green-200">
            <div class="text-green-600 text-[20px]">✓</div>
            <div>
              <p class="text-[11px] font-semibold text-gray-900">Safe Unloading</p>
              <p class="text-[9px] text-gray-600">All items handled carefully</p>
            </div>
          </div>
          <div class="flex items-center gap-2 bg-green-50 p-3 rounded border border-green-200">
            <div class="text-green-600 text-[20px]">✓</div>
            <div>
              <p class="text-[11px] font-semibold text-gray-900">Placement in Rooms</p>
              <p class="text-[9px] text-gray-600">As per customer instructions</p>
            </div>
          </div>
          <div class="flex items-center gap-2 bg-green-50 p-3 rounded border border-green-200">
            <div class="text-green-600 text-[20px]">✓</div>
            <div>
              <p class="text-[11px] font-semibold text-gray-900">Basic Unpacking</p>
              <p class="text-[9px] text-gray-600">Boxes opened as requested</p>
            </div>
          </div>
          <div class="flex items-center gap-2 bg-green-50 p-3 rounded border border-green-200">
            <div class="text-green-600 text-[20px]">✓</div>
            <div>
              <p class="text-[11px] font-semibold text-gray-900">Furniture Assembly</p>
              <p class="text-[9px] text-gray-600">Bed, wardrobe assembled</p>
            </div>
          </div>
        </div>
      </div>

      <!-- Customer Feedback -->
      <div class="bg-blue-50 p-4 rounded-lg border border-blue-200">
        <h3 class="text-[11px] font-bold text-blue-900 mb-2">💬 CUSTOMER FEEDBACK</h3>
        <div class="bg-white p-3 rounded border border-blue-200">
          <div class="flex gap-1 mb-2">
            <span class="text-[18px] text-yellow-500">★★★★★</span>
            <span class="text-[11px] font-semibold text-gray-700 ml-2">5.0 / 5.0</span>
          </div>
          <p class="text-[10px] text-gray-700 italic">"Excellent service! The team was professional, careful with our belongings, and completed the move ahead of schedule. Highly recommended!"</p>
        </div>
      </div>

      <!-- Customer Signature -->
      <div class="border-2 border-gray-300 rounded-lg p-4 bg-amber-50">
        <h3 class="text-[11px] font-bold text-gray-800 mb-3">CUSTOMER ACKNOWLEDGMENT</h3>
        <div class="bg-white p-3 rounded mb-3">
          <p class="text-[10px] text-gray-700 mb-2">I acknowledge that:</p>
          <ul class="text-[9px] text-gray-600 space-y-1 ml-4">
            <li>✓ All items have been delivered in good condition</li>
            <li>✓ No items are missing or damaged</li>
            <li>✓ All agreed services have been completed satisfactorily</li>
            <li>✓ I authorize the final payment as per invoice</li>
          </ul>
        </div>
        <div class="grid grid-cols-2 gap-4">
          <div>
            <p class="text-[10px] text-gray-600 mb-2">Customer Signature:</p>
            <div class="border-2 border-gray-400 rounded h-[60px] bg-white mb-2"></div>
            <p class="text-[9px] text-gray-500">Name: Sarah Khan</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 mb-2">Date & Time:</p>
            <div class="border-b-2 border-gray-400 h-[30px] mb-2 flex items-end">
              <span class="text-[11px] font-semibold text-gray-900">December 20, 2024 - 01:45 PM</span>
            </div>
            <p class="text-[9px] text-gray-500 mt-4">Driver Signature: _______________</p>
          </div>
        </div>
      </div>

      <!-- Important Note -->
      <div class="bg-green-50 border-l-4 border-green-600 p-3">
        <p class="text-[10px] font-bold text-green-800 mb-1">✓ DELIVERY COMPLETE:</p>
        <p class="text-[10px] text-gray-700">This document serves as official proof of successful delivery. Customer has accepted all items and services. Thank you for choosing CargoCore Logistics!</p>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup lang="ts">
import DocumentLayout from './DocumentLayout.vue';
</script>
