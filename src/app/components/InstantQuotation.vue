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
          <p class="text-[13px] font-semibold text-gray-900">{{ customer.name }}</p>
          <p class="text-[11px] text-gray-600">Phone: {{ customer.phone }}</p>
          <p class="text-[11px] text-gray-600">Email: {{ customer.email }}</p>
        </div>
        <div class="bg-gray-50 p-4 rounded-lg">
          <h3 class="text-[11px] font-bold text-gray-700 mb-2">QUOTATION INFO</h3>
          <p class="text-[11px] text-gray-600">Quote ID: <span class="font-semibold text-gray-900">{{ quote.id }}</span></p>
          <p class="text-[11px] text-gray-600">Date: <span class="font-semibold text-gray-900">{{ quote.date }}</span></p>
          <p class="text-[11px] text-gray-600">Valid Until: <span class="font-semibold text-gray-900">{{ quote.validUntil }}</span></p>
        </div>
      </div>

      <!-- Route -->
      <div class="bg-blue-50 p-4 rounded-lg border border-blue-200">
        <div class="flex items-center justify-between">
          <div class="flex-1">
            <p class="text-[10px] text-gray-600 uppercase mb-1">FROM</p>
            <p class="text-[12px] font-semibold text-gray-900">{{ route.fromAddress }}</p>
            <p class="text-[10px] text-gray-600">Bangalore - {{ route.fromPincode }}</p>
          </div>
          <div class="text-[24px] text-blue-600 mx-4">→</div>
          <div class="flex-1">
            <p class="text-[10px] text-gray-600 uppercase mb-1">TO</p>
            <p class="text-[12px] font-semibold text-gray-900">{{ route.toAddress }}</p>
            <p class="text-[10px] text-gray-600">Bangalore - {{ route.toPincode }}</p>
          </div>
        </div>
        <div class="mt-3 pt-3 border-t border-blue-200 flex justify-between text-[11px]">
          <span class="text-gray-600">Distance: <span class="font-semibold text-gray-900">{{ route.distance }}</span></span>
          <span class="text-gray-600">Move Date: <span class="font-semibold text-gray-900">{{ route.moveDate }}</span></span>
        </div>
      </div>

      <!-- Total Amount Box -->
      <div class="bg-gradient-to-r from-green-600 to-green-500 text-white p-6 rounded-lg text-center">
        <p class="text-[12px] opacity-90 mb-1">TOTAL QUOTATION AMOUNT</p>
        <p class="text-[42px] font-bold">{{ totalAmount }}</p>
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
            <tr v-for="(item, index) in breakdown" :key="index" :class="index % 2 !== 0 ? 'bg-gray-50' : ''">
              <td class="p-2 border border-gray-300 font-semibold">{{ item.service }}</td>
              <td class="p-2 border border-gray-300">{{ item.description }}</td>
              <td class="text-right p-2 border border-gray-300">{{ item.amount }}</td>
            </tr>
            <tr class="bg-blue-100 font-bold text-[12px]">
              <td class="p-2 border border-gray-300" colspan="2">GRAND TOTAL</td>
              <td class="text-right p-2 border border-gray-300">{{ totalAmount }}</td>
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

      <!-- Authorization & Seal -->
      <div class="flex items-center justify-between pt-2">
        <div>
          <p class="text-[11px] font-semibold text-gray-800 mb-1">For CargoCore Logistics Pvt. Ltd.</p>
          <p class="text-[10px] text-gray-600 italic mt-6">(Authorized Signatory)</p>
        </div>
        <div class="w-[110px] h-[110px]">
          <svg viewBox="0 0 150 150" class="w-full h-full">
            <circle cx="75" cy="75" r="72" fill="none" stroke="#3D5A99" stroke-width="3"/>
            <circle cx="75" cy="75" r="60" fill="none" stroke="#3D5A99" stroke-width="1"/>
            <text x="75" y="20" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
            <text x="75" y="135" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
            <text x="20" y="78" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
            <text x="130" y="78" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
            <path id="iqSealTopArc" d="M 30,75 A 45,45 0 0,1 120,75" fill="none"/>
            <text font-size="11" fill="#3D5A99" font-weight="bold">
              <textPath href="#iqSealTopArc" text-anchor="middle" startOffset="50%">CARGOCORE</textPath>
            </text>
            <path id="iqSealBottomArc" d="M 120,75 A 45,45 0 0,1 30,75" fill="none"/>
            <text font-size="9" fill="#3D5A99" font-weight="600">
              <textPath href="#iqSealBottomArc" text-anchor="middle" startOffset="50%">LOGISTICS PVT. LTD.</textPath>
            </text>
            <image :href="logoSrc" x="55" y="55" width="40" height="40" opacity="0.7"/>
            <text x="75" y="105" font-size="10" fill="#DC2626" font-weight="bold" text-anchor="middle">OFFICIAL SEAL</text>
          </svg>
        </div>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup>
import DocumentLayout from './DocumentLayout.vue';
import logoSrc from '../../assets/f27e35eb84d6e7810aa280143872a57f44f6325d.png'

const props = defineProps({
  customer: {
    type: Object,
    default: () => ({ name: 'Sarah Khan', phone: '+91 98765 43210', email: 'sarah.khan@email.com' })
  },
  quote: {
    type: Object,
    default: () => ({ id: 'QT-2024-0567', date: 'December 15, 2024', validUntil: 'December 22, 2024' })
  },
  route: {
    type: Object,
    default: () => ({
      fromAddress: '123 Oak Street, Whitefield',
      fromPincode: '560066',
      toAddress: '456 Maple Avenue, Indiranagar',
      toPincode: '560038',
      distance: '18.5 km',
      moveDate: 'December 20, 2024'
    })
  },
  totalAmount: { type: String, default: '₹4,500' },
  breakdown: {
    type: Array,
    default: () => [
      { service: 'Transport Charges', description: '14 ft truck, 18.5 km distance', amount: '₹1,800' },
      { service: 'Labor Charges', description: '4 skilled workers (loading & unloading)', amount: '₹1,600' },
      { service: 'Packing Materials', description: '28 boxes, bubble wrap, tape, etc.', amount: '₹700' },
      { service: 'Packing Service', description: 'Professional packing by our team', amount: '₹400' },
      { service: 'GST (18%)', description: 'Tax on total service amount', amount: '₹0' }
    ]
  }
})
</script>
