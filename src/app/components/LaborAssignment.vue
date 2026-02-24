<template>
  <DocumentLayout>
    <div class="space-y-6">
      <!-- Title -->
      <div class="text-center border-b-2 border-blue-900 pb-3">
        <h1 class="text-[22px] font-bold text-blue-900 tracking-wide">LABOR ASSIGNMENT SHEET</h1>
        <p class="text-[11px] text-gray-600 mt-1">Workforce Allocation & Task Assignment</p>
      </div>

      <!-- Order Details -->
      <div class="bg-gradient-to-r from-blue-900 to-blue-700 text-white p-5 rounded-lg">
        <div class="grid grid-cols-3 gap-4">
          <div>
            <p class="text-[10px] opacity-80 uppercase">Order ID</p>
            <p class="text-[15px] font-bold">{{ order.id }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Assignment Date</p>
            <p class="text-[13px] font-semibold">{{ order.assignmentDate }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Shift Time</p>
            <p class="text-[13px] font-semibold">{{ order.shiftTime }}</p>
          </div>
        </div>
        <div class="mt-3 pt-3 border-t border-white/20">
          <p class="text-[10px] opacity-80 uppercase mb-1">Customer</p>
          <p class="text-[13px] font-semibold">{{ customer.name }} | {{ customer.phone }}</p>
        </div>
      </div>

      <!-- Route Summary -->
      <div class="grid grid-cols-2 gap-4">
        <div class="bg-blue-50 p-3 rounded border border-blue-200">
          <p class="text-[10px] font-bold text-blue-800 mb-1">PICKUP LOCATION</p>
          <p class="text-[11px] font-semibold text-gray-900">{{ pickup.address }}</p>
          <p class="text-[10px] text-gray-600">{{ pickup.city }} - {{ pickup.pincode }}</p>
        </div>
        <div class="bg-green-50 p-3 rounded border border-green-200">
          <p class="text-[10px] font-bold text-green-800 mb-1">DELIVERY LOCATION</p>
          <p class="text-[11px] font-semibold text-gray-900">{{ delivery.address }}</p>
          <p class="text-[10px] text-gray-600">{{ delivery.city }} - {{ delivery.pincode }}</p>
        </div>
      </div>

      <!-- Assigned Workers -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">ASSIGNED WORKERS ({{ workers.length }} MEMBERS)</h3>
        <template v-for="(worker, index) in workers" :key="index">
          <div :class="['p-4 rounded', worker.isTeamLead ? 'mb-4 bg-amber-50 border-l-4 border-amber-500' : 'mb-3 bg-gray-50 border border-gray-200']">
            <div class="flex items-start gap-4">
              <div class="flex-1">
                <div class="flex items-center gap-2 mb-1">
                  <p class="text-[13px] font-bold text-gray-900">{{ worker.name }}</p>
                  <span v-if="worker.isTeamLead" class="bg-amber-500 text-white text-[9px] px-2 py-0.5 rounded">TEAM LEAD</span>
                </div>
                <div class="grid grid-cols-3 gap-2 text-[10px]">
                  <div>
                    <p class="text-gray-600">Employee ID</p>
                    <p class="font-semibold text-gray-900">{{ worker.employeeId }}</p>
                  </div>
                  <div>
                    <p class="text-gray-600">Experience</p>
                    <p class="font-semibold text-gray-900">{{ worker.experience }}</p>
                  </div>
                  <div>
                    <p class="text-gray-600">Contact</p>
                    <p class="font-semibold text-gray-900">{{ worker.contact }}</p>
                  </div>
                </div>
                <p class="text-[10px] text-gray-700 mt-2"><span class="font-semibold">Role:</span> {{ worker.role }}</p>
              </div>
            </div>
          </div>
        </template>
      </div>

      <!-- Task Checklist -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">TASK CHECKLIST</h3>
        <div class="grid grid-cols-2 gap-3">
          <div class="flex items-center gap-2 bg-gray-50 p-2 rounded border border-gray-200">
            <input type="checkbox" class="w-4 h-4">
            <span class="text-[11px] text-gray-800">Pre-move inspection completed</span>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-2 rounded border border-gray-200">
            <input type="checkbox" class="w-4 h-4">
            <span class="text-[11px] text-gray-800">All materials collected from warehouse</span>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-2 rounded border border-gray-200">
            <input type="checkbox" class="w-4 h-4">
            <span class="text-[11px] text-gray-800">Customer briefing done</span>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-2 rounded border border-gray-200">
            <input type="checkbox" class="w-4 h-4">
            <span class="text-[11px] text-gray-800">Packing completed & labeled</span>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-2 rounded border border-gray-200">
            <input type="checkbox" class="w-4 h-4">
            <span class="text-[11px] text-gray-800">Loading completed safely</span>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-2 rounded border border-gray-200">
            <input type="checkbox" class="w-4 h-4">
            <span class="text-[11px] text-gray-800">Unloading completed at destination</span>
          </div>
          <div class="flex items-center gap-2 bg-gray-50 p-2 rounded border border-gray-200">
            <input type="checkbox" class="w-4 h-4">
            <span class="text-[11px] text-gray-800">Customer signature obtained</span>
          </div>
        </div>
      </div>

      <!-- SMS Confirmation -->
      <div class="bg-green-50 border-2 border-green-400 p-4 rounded-lg">
        <p class="text-[11px] font-bold text-green-800 mb-2">📱 SMS SENT TO WORKERS</p>
        <div class="bg-white p-3 rounded border border-green-200 text-[10px] text-gray-700 font-mono">
          <p class="mb-1">Dear Team Member,</p>
          <p>You are assigned to Order {{ order.id }} on {{ order.assignmentDate }} at {{ order.shiftTime.split(' - ')[0] }}.</p>
          <p>Pickup: {{ pickup.address }}. Report to Team Lead {{ workers.find(w => w.isTeamLead)?.name }}.</p>
          <p class="mt-1">- CargoCore Operations</p>
        </div>
      </div>

      <!-- Notes -->
      <div class="bg-amber-50 border-l-4 border-amber-500 p-3">
        <p class="text-[10px] font-bold text-amber-800 mb-1">⚠ SPECIAL INSTRUCTIONS:</p>
        <ul class="text-[10px] text-gray-700 space-y-1">
          <li v-for="(instruction, i) in specialInstructions" :key="i">• {{ instruction }}</li>
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
    default: () => ({
      id: 'CC-12345',
      assignmentDate: 'December 20, 2024',
      shiftTime: '09:00 AM - 05:00 PM'
    })
  },
  customer: {
    type: Object,
    default: () => ({ name: 'Sarah Khan', phone: '+91 98765 43210' })
  },
  pickup: {
    type: Object,
    default: () => ({ address: '123 Oak Street, Whitefield', city: 'Bangalore', pincode: '560066' })
  },
  delivery: {
    type: Object,
    default: () => ({ address: '456 Maple Avenue, Indiranagar', city: 'Bangalore', pincode: '560038' })
  },
  workers: {
    type: Array,
    default: () => [
      { name: 'Rajesh Kumar', employeeId: 'EMP-2541', experience: '8 Years', contact: '+91 98765 11111', role: 'Supervise team, coordinate with customer, ensure quality control', isTeamLead: true },
      { name: 'Vijay Sharma', employeeId: 'EMP-3782', experience: '5 Years', contact: '+91 98765 22222', role: 'Packing specialist, handle fragile items', isTeamLead: false },
      { name: 'Arun Patel', employeeId: 'EMP-4156', experience: '4 Years', contact: '+91 98765 33333', role: 'Loading/unloading, heavy lifting', isTeamLead: false },
      { name: 'Mohammed Rafi', employeeId: 'EMP-5234', experience: '3 Years', contact: '+91 98765 44444', role: 'Furniture disassembly/assembly, general support', isTeamLead: false }
    ]
  },
  specialInstructions: {
    type: Array,
    default: () => [
      'Customer has antique furniture - handle with extra care',
      '2nd floor delivery - ensure lift is operational',
      'All workers must wear company uniform and ID card'
    ]
  }
})
</script>
