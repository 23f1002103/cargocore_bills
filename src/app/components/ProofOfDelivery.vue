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
            <p class="text-[15px] font-bold">{{ order.id }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Delivery Date</p>
            <p class="text-[13px] font-semibold">{{ order.deliveryDate }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Delivery Time</p>
            <p class="text-[13px] font-semibold">{{ order.deliveryTime }}</p>
          </div>
        </div>
        <div class="mt-3 pt-3 border-t border-white/20 grid grid-cols-2 gap-4">
          <div>
            <p class="text-[10px] opacity-80 uppercase mb-1">Customer</p>
            <p class="text-[13px] font-semibold">{{ customer.name }} | {{ customer.phone }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase mb-1">Driver</p>
            <p class="text-[13px] font-semibold">{{ driver.name }} ({{ driver.employeeId }})</p>
          </div>
        </div>
      </div>

      <!-- Delivery Address -->
      <div class="bg-blue-50 p-4 rounded-lg border border-blue-200">
        <h3 class="text-[11px] font-bold text-blue-900 mb-2">📍 DELIVERY ADDRESS</h3>
        <p class="text-[13px] font-semibold text-gray-900">{{ deliveryAddress.address }}</p>
        <p class="text-[11px] text-gray-700">{{ deliveryAddress.city }}, {{ deliveryAddress.state }} - {{ deliveryAddress.pincode }}</p>
        <div class="mt-2 pt-2 border-t border-blue-200 grid grid-cols-2 gap-2 text-[10px]">
          <div>Floor: <span class="font-semibold">{{ deliveryAddress.floor }}</span></div>
          <div>Lift Available: <span class="font-semibold">{{ deliveryAddress.liftAvailable }}</span></div>
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
            <p class="font-semibold text-gray-900">{{ gps.coordinates }}</p>
          </div>
          <div>
            <p class="text-gray-600">Location Accuracy:</p>
            <p class="font-semibold text-green-600">{{ gps.accuracy }}</p>
          </div>
          <div>
            <p class="text-gray-600">Timestamp:</p>
            <p class="font-semibold text-gray-900">{{ gps.timestamp }}</p>
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
            <tr v-for="(item, index) in items" :key="index" :class="index % 2 !== 0 ? 'bg-gray-50' : ''">
              <td class="p-2 border border-gray-300">{{ item.description }}</td>
              <td class="text-center p-2 border border-gray-300">{{ item.qty }}</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">{{ item.condition }}</td>
              <td class="text-center p-2 border border-gray-300 text-green-600">✓</td>
            </tr>
            <tr class="bg-green-100 font-bold">
              <td class="p-2 border border-gray-300">TOTAL ITEMS</td>
              <td class="text-center p-2 border border-gray-300">{{ items.reduce((s, i) => s + i.qty, 0) }}</td>
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
            <p class="text-[9px] text-gray-500">Name: {{ customer.name }}</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 mb-2">Date & Time:</p>
            <div class="border-b-2 border-gray-400 h-[30px] mb-2 flex items-end">
              <span class="text-[11px] font-semibold text-gray-900">{{ order.deliveryDate }} - {{ order.deliveryTime }}</span>
            </div>
            <div class="flex items-center gap-3 mt-2">
              <p class="text-[9px] text-gray-500">Driver:</p>
              <div class="w-[80px] h-[80px]">
                <svg viewBox="0 0 150 150" class="w-full h-full">
                  <circle cx="75" cy="75" r="72" fill="none" stroke="#3D5A99" stroke-width="3"/>
                  <circle cx="75" cy="75" r="60" fill="none" stroke="#3D5A99" stroke-width="1"/>
                  <text x="75" y="20" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
                  <text x="75" y="135" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
                  <text x="20" y="78" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
                  <text x="130" y="78" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
                  <path id="podSealTopArc" d="M 30,75 A 45,45 0 0,1 120,75" fill="none"/>
                  <text font-size="11" fill="#3D5A99" font-weight="bold">
                    <textPath href="#podSealTopArc" text-anchor="middle" startOffset="50%">CARGOCORE</textPath>
                  </text>
                  <path id="podSealBottomArc" d="M 120,75 A 45,45 0 0,1 30,75" fill="none"/>
                  <text font-size="9" fill="#3D5A99" font-weight="600">
                    <textPath href="#podSealBottomArc" text-anchor="middle" startOffset="50%">LOGISTICS PVT. LTD.</textPath>
                  </text>
                  <image :href="logoSrc" x="55" y="55" width="40" height="40" opacity="0.7"/>
                  <text x="75" y="105" font-size="10" fill="#DC2626" font-weight="bold" text-anchor="middle">OFFICIAL SEAL</text>
                </svg>
              </div>
            </div>
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

<script setup>
import DocumentLayout from './DocumentLayout.vue';
import logoSrc from '../../assets/f27e35eb84d6e7810aa280143872a57f44f6325d.png'

const props = defineProps({
  order: {
    type: Object,
    default: () => ({ id: 'CC-12345', deliveryDate: 'December 20, 2024', deliveryTime: '01:45 PM' })
  },
  customer: {
    type: Object,
    default: () => ({ name: 'Sarah Khan', phone: '+91 98765 43210' })
  },
  driver: {
    type: Object,
    default: () => ({ name: 'Prakash Reddy', employeeId: 'DRV-8765' })
  },
  deliveryAddress: {
    type: Object,
    default: () => ({
      address: '456 Maple Avenue, Indiranagar',
      city: 'Bangalore',
      state: 'Karnataka',
      pincode: '560038',
      floor: '2nd Floor',
      liftAvailable: 'Yes'
    })
  },
  gps: {
    type: Object,
    default: () => ({
      coordinates: '12.9716° N, 77.5946° E',
      accuracy: '± 5 meters (High)',
      timestamp: 'Dec 20, 2024 01:45:23 PM'
    })
  },
  items: {
    type: Array,
    default: () => [
      { description: 'Large Cardboard Boxes (Sealed)', qty: 15, condition: 'Good' },
      { description: 'Medium Cardboard Boxes (Sealed)', qty: 13, condition: 'Good' },
      { description: 'Furniture Items (Protected)', qty: 8, condition: 'Good' },
      { description: 'Appliances (Bubble Wrapped)', qty: 4, condition: 'Good' }
    ]
  }
})
</script>
