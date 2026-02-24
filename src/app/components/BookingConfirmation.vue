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
            <p class="text-[18px] font-bold">{{ order.id }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Booking Date</p>
            <p class="text-[13px] font-semibold">{{ order.bookingDate }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Move Date</p>
            <p class="text-[13px] font-semibold">{{ order.moveDate }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Time Slot</p>
            <p class="text-[13px] font-semibold">{{ order.timeSlot }}</p>
          </div>
        </div>
      </div>

      <!-- Customer Details -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">CUSTOMER INFORMATION</h3>
        <div class="grid grid-cols-2 gap-4 bg-gray-50 p-4 rounded-lg">
          <div>
            <p class="text-[10px] text-gray-600 uppercase mb-1">Full Name</p>
            <p class="text-[13px] font-semibold text-gray-900">{{ customer.name }}</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 uppercase mb-1">Contact Number</p>
            <p class="text-[13px] font-semibold text-gray-900">{{ customer.phone }}</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 uppercase mb-1">Email Address</p>
            <p class="text-[13px] font-semibold text-gray-900">{{ customer.email }}</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 uppercase mb-1">Alternate Number</p>
            <p class="text-[13px] font-semibold text-gray-900">{{ customer.alternatePhone }}</p>
          </div>
        </div>
      </div>

      <!-- Address Details -->
      <div class="grid grid-cols-2 gap-4">
        <div class="bg-blue-50 p-4 rounded-lg border border-blue-200">
          <p class="text-[11px] font-bold text-blue-800 mb-2">📍 PICKUP ADDRESS</p>
          <p class="text-[12px] font-semibold text-gray-900">{{ pickup.address }}</p>
          <p class="text-[11px] text-gray-600">{{ pickup.city }}, {{ pickup.state }} - {{ pickup.pincode }}</p>
          <p class="text-[10px] text-gray-600 mt-2">Floor: {{ pickup.floor }} | Lift: {{ pickup.lift }}</p>
        </div>
        <div class="bg-green-50 p-4 rounded-lg border border-green-200">
          <p class="text-[11px] font-bold text-green-800 mb-2">📍 DELIVERY ADDRESS</p>
          <p class="text-[12px] font-semibold text-gray-900">{{ delivery.address }}</p>
          <p class="text-[11px] text-gray-600">{{ delivery.city }}, {{ delivery.state }} - {{ delivery.pincode }}</p>
          <p class="text-[10px] text-gray-600 mt-2">Floor: {{ delivery.floor }} | Lift: {{ delivery.lift }}</p>
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
              <td class="text-right py-2 font-semibold">{{ payment.total }}</td>
            </tr>
            <tr class="border-b border-gray-200 bg-green-50">
              <td class="py-2 text-green-700">Advance Paid ({{ payment.advancePct }})</td>
              <td class="text-right py-2 font-semibold text-green-700">{{ payment.advance }}</td>
            </tr>
            <tr class="border-b border-gray-200">
              <td class="py-2">Payment Mode</td>
              <td class="text-right py-2 font-semibold">{{ payment.mode }}</td>
            </tr>
            <tr class="border-b border-gray-200">
              <td class="py-2">Transaction ID</td>
              <td class="text-right py-2 font-semibold">{{ payment.transactionId }}</td>
            </tr>
            <tr class="bg-amber-50 font-bold">
              <td class="py-2 text-amber-800">Balance Due (at delivery)</td>
              <td class="text-right py-2 text-amber-800">{{ payment.balance }}</td>
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
            <path id="bcSealTopArc" d="M 30,75 A 45,45 0 0,1 120,75" fill="none"/>
            <text font-size="11" fill="#3D5A99" font-weight="bold">
              <textPath href="#bcSealTopArc" text-anchor="middle" startOffset="50%">CARGOCORE</textPath>
            </text>
            <path id="bcSealBottomArc" d="M 120,75 A 45,45 0 0,1 30,75" fill="none"/>
            <text font-size="9" fill="#3D5A99" font-weight="600">
              <textPath href="#bcSealBottomArc" text-anchor="middle" startOffset="50%">LOGISTICS PVT. LTD.</textPath>
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
  order: {
    type: Object,
    default: () => ({
      id: 'CC-12345',
      bookingDate: 'December 16, 2024',
      moveDate: 'December 20, 2024',
      timeSlot: '09:00 AM - 12:00 PM'
    })
  },
  customer: {
    type: Object,
    default: () => ({
      name: 'Sarah Khan',
      phone: '+91 98765 43210',
      email: 'sarah.khan@email.com',
      alternatePhone: '+91 87654 32109'
    })
  },
  pickup: {
    type: Object,
    default: () => ({
      address: '123 Oak Street, Whitefield',
      city: 'Bangalore',
      state: 'Karnataka',
      pincode: '560066',
      floor: 'Ground',
      lift: 'Available'
    })
  },
  delivery: {
    type: Object,
    default: () => ({
      address: '456 Maple Avenue, Indiranagar',
      city: 'Bangalore',
      state: 'Karnataka',
      pincode: '560038',
      floor: '2nd',
      lift: 'Available'
    })
  },
  services: {
    type: Array,
    default: () => [
      { name: 'Professional Packing', description: 'Complete packing service' },
      { name: 'Loading & Unloading', description: '4 skilled workers' },
      { name: 'Transportation', description: '14 ft covered truck' },
      { name: 'Transit Insurance', description: 'Up to ₹50,000 coverage' },
      { name: 'GPS Tracking', description: 'Real-time location updates' },
      { name: 'Unpacking Service', description: 'Basic unpacking included' }
    ]
  },
  payment: {
    type: Object,
    default: () => ({
      total: '₹4,500',
      advance: '₹1,350',
      advancePct: '30%',
      mode: 'UPI / Online Transfer',
      transactionId: 'TXN20241216789456',
      balance: '₹3,150'
    })
  }
})
</script>
