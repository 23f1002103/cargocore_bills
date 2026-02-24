<template>
  <div>
    <DocumentLayout>
        <div class="space-y-6">

          <!-- Document Title -->
          <div class="text-center space-y-1 mt-4 mb-4 pb-5 border-b-2 border-[#3D5A99]">
            <h2 class="font-bold text-[#3D5A99] text-[36pt] leading-tight">SALARY SLIP</h2>
            <p class="text-gray-600 text-[14pt]">For the month of {{ period }}</p>
          </div>

          <!-- Employee Details -->
          <div class="bg-gray-50 rounded-lg shadow-sm p-5">
            <div class="text-lg font-bold text-[#2C3E50] mb-3">{{ employee.name }}</div>
            <div class="grid grid-cols-2 gap-x-8 gap-y-2">
              <div class="text-sm">
                <span class="text-gray-600">Employee ID:</span>
                <span class="ml-2 font-medium">{{ employee.id }}</span>
              </div>
              <div class="text-sm">
                <span class="text-gray-600">Designation:</span>
                <span class="ml-2 font-medium">{{ employee.designation }}</span>
              </div>
              <div class="text-sm">
                <span class="text-gray-600">Department:</span>
                <span class="ml-2 font-medium">{{ employee.department }}</span>
              </div>
              <div class="text-sm">
                <span class="text-gray-600">Payment Date:</span>
                <span class="ml-2 font-medium">{{ employee.paymentDate }}</span>
              </div>
            </div>
          </div>

          <!-- Earnings & Deductions Tables -->
          <div class="grid grid-cols-2 gap-6">

            <!-- Earnings -->
            <div class="border border-gray-200 rounded-lg overflow-hidden shadow-sm">
              <table class="w-full">
                <thead>
                  <tr class="bg-[#3D5A99] text-white">
                    <th class="px-4 py-3 text-left font-semibold text-sm">EARNINGS</th>
                    <th class="px-4 py-3 text-right font-semibold text-sm">Amount (₹)</th>
                  </tr>
                </thead>
                <tbody>
                  <tr
                    v-for="(item, i) in earnings"
                    :key="i"
                    :class="['border-b border-gray-100', i % 2 !== 0 ? 'bg-gray-50' : '']"
                  >
                    <td class="px-4 py-2 text-left text-sm">{{ item.label }}</td>
                    <td class="px-4 py-2 text-right text-sm">{{ item.amount }}</td>
                  </tr>
                  <tr class="bg-[#4FC3F7] font-bold">
                    <td class="px-4 py-3 text-left text-sm">GROSS EARNINGS</td>
                    <td class="px-4 py-3 text-right text-sm">₹{{ totals.gross }}</td>
                  </tr>
                </tbody>
              </table>
            </div>

            <!-- Deductions -->
            <div class="border border-gray-200 rounded-lg overflow-hidden shadow-sm">
              <table class="w-full">
                <thead>
                  <tr class="bg-[#3D5A99] text-white">
                    <th class="px-4 py-3 text-left font-semibold text-sm">DEDUCTIONS</th>
                    <th class="px-4 py-3 text-right font-semibold text-sm">Amount (₹)</th>
                  </tr>
                </thead>
                <tbody>
                  <tr
                    v-for="(item, i) in deductions"
                    :key="i"
                    :class="['border-b border-gray-100', i % 2 !== 0 ? 'bg-gray-50' : '']"
                  >
                    <td class="px-4 py-2 text-left text-sm">{{ item.label }}</td>
                    <td class="px-4 py-2 text-right text-sm">{{ item.amount }}</td>
                  </tr>
                  <tr class="bg-red-50 text-red-600 font-bold">
                    <td class="px-4 py-3 text-left text-sm">TOTAL DEDUCTIONS</td>
                    <td class="px-4 py-3 text-right text-sm">₹{{ totals.deductions }}</td>
                  </tr>
                </tbody>
              </table>
            </div>
          </div>

          <!-- Net Payable Salary -->
          <div class="bg-gradient-to-r from-[#3D5A99] to-[#4FC3F7] text-white text-center p-6 rounded-xl shadow-lg">
            <div class="text-lg font-medium">NET PAYABLE SALARY</div>
            <div class="text-4xl font-bold mt-2">₹{{ totals.net }}</div>
          </div>

          <!-- Signature & Company Seal -->
          <div class="grid grid-cols-2 gap-12 mt-10 mb-4">
            <!-- Authorized Signature -->
            <div>
              <p class="text-sm text-gray-700 font-medium mb-10">Authorized Signature</p>
              <div class="border-t border-gray-400 w-[200px] pt-3">
                <p class="text-lg italic" style="font-family: 'Dancing Script', cursive;">{{ signatory.name }}</p>
                <p class="text-xs text-gray-500 mt-1">({{ signatory.title }})</p>
                <p class="text-xs text-gray-500 mt-1">Date: {{ signatory.date }}</p>
              </div>
            </div>

            <!-- Company Seal SVG -->
            <div class="flex items-center justify-center">
              <div class="w-[150px] h-[150px]">
                <svg viewBox="0 0 150 150" class="w-full h-full">
                  <circle cx="75" cy="75" r="72" fill="none" stroke="#3D5A99" stroke-width="3"/>
                  <circle cx="75" cy="75" r="60" fill="none" stroke="#3D5A99" stroke-width="1"/>
                  <text x="75" y="20" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
                  <text x="75" y="135" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
                  <text x="20" y="78" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
                  <text x="130" y="78" font-size="12" fill="#3D5A99" text-anchor="middle">★</text>
                  <path id="sealTopArc" d="M 30,75 A 45,45 0 0,1 120,75" fill="none"/>
                  <text font-size="11" fill="#3D5A99" font-weight="bold">
                    <textPath href="#sealTopArc" text-anchor="middle" startOffset="50%">CARGOCORE</textPath>
                  </text>
                  <path id="sealBottomArc" d="M 120,75 A 45,45 0 0,1 30,75" fill="none"/>
                  <text font-size="9" fill="#3D5A99" font-weight="600">
                    <textPath href="#sealBottomArc" text-anchor="middle" startOffset="50%">LOGISTICS PVT. LTD.</textPath>
                  </text>
                  <image
                    :href="logoSrc"
                    x="55" y="55" width="40" height="40"
                    opacity="0.7"
                  />
                  <text x="75" y="105" font-size="10" fill="#DC2626" font-weight="bold" text-anchor="middle">OFFICIAL SEAL</text>
                </svg>
              </div>
            </div>
          </div>

        </div>
    </DocumentLayout>
  </div>
</template>

<script setup>
import DocumentLayout from './DocumentLayout.vue'
import logoSrc from '../../assets/f27e35eb84d6e7810aa280143872a57f44f6325d.png'

const props = defineProps({
  period: {
    type: String,
    default: 'February 2026'
  },
  employee: {
    type: Object,
    default: () => ({
      name: 'Siddarth S',
      id: 'WM001',
      designation: 'Warehouse Manager',
      department: 'Operations',
      paymentDate: '28 February 2026'
    })
  },
  earnings: {
    type: Array,
    default: () => [
      { label: 'Basic Salary',           amount: '42,000' },
      { label: 'House Rent Allowance',   amount: '12,000' },
      { label: 'Transport Allowance',    amount: '2,500'  },
      { label: 'Special Allowance',      amount: '3,500'  }
    ]
  },
  deductions: {
    type: Array,
    default: () => [
      { label: 'Professional Tax',   amount: '200'   },
      { label: 'Income Tax (TDS)',   amount: '4,200' }
    ]
  },
  totals: {
    type: Object,
    default: () => ({
      gross:      '60,000',
      deductions: '4,400',
      net:        '55,600'
    })
  },
  signatory: {
    type: Object,
    default: () => ({
      name:  'Pruthvi Prasad S',
      title: 'Logistics Manager',
      date:  '28 Feb 2026'
    })
  }
})
</script>