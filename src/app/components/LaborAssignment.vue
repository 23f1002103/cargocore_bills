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
            <p class="text-[15px] font-bold">CC-12345</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Assignment Date</p>
            <p class="text-[13px] font-semibold">December 20, 2024</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Shift Time</p>
            <p class="text-[13px] font-semibold">09:00 AM - 05:00 PM</p>
          </div>
        </div>
        <div class="mt-3 pt-3 border-t border-white/20">
          <p class="text-[10px] opacity-80 uppercase mb-1">Customer</p>
          <p class="text-[13px] font-semibold">Sarah Khan | +91 98765 43210</p>
        </div>
      </div>

      <!-- Route Summary -->
      <div class="grid grid-cols-2 gap-4">
        <div class="bg-blue-50 p-3 rounded border border-blue-200">
          <p class="text-[10px] font-bold text-blue-800 mb-1">PICKUP LOCATION</p>
          <p class="text-[11px] font-semibold text-gray-900">123 Oak Street, Whitefield</p>
          <p class="text-[10px] text-gray-600">Bangalore - 560066</p>
        </div>
        <div class="bg-green-50 p-3 rounded border border-green-200">
          <p class="text-[10px] font-bold text-green-800 mb-1">DELIVERY LOCATION</p>
          <p class="text-[11px] font-semibold text-gray-900">456 Maple Avenue, Indiranagar</p>
          <p class="text-[10px] text-gray-600">Bangalore - 560038</p>
        </div>
      </div>

      <!-- Assigned Workers -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">ASSIGNED WORKERS (4 MEMBERS)</h3>
        
        <!-- Team Lead -->
        <div class="mb-4 bg-amber-50 border-l-4 border-amber-500 p-4 rounded">
          <div class="flex items-start gap-4">
            <div class="w-[70px] h-[70px] bg-gray-300 rounded-lg flex items-center justify-center text-gray-600 text-[10px]">
              📷<br>Photo
            </div>
            <div class="flex-1">
              <div class="flex items-center gap-2 mb-1">
                <p class="text-[13px] font-bold text-gray-900">Rajesh Kumar</p>
                <span class="bg-amber-500 text-white text-[9px] px-2 py-0.5 rounded">TEAM LEAD</span>
              </div>
              <div class="grid grid-cols-3 gap-2 text-[10px]">
                <div>
                  <p class="text-gray-600">Employee ID</p>
                  <p class="font-semibold text-gray-900">EMP-2541</p>
                </div>
                <div>
                  <p class="text-gray-600">Experience</p>
                  <p class="font-semibold text-gray-900">8 Years</p>
                </div>
                <div>
                  <p class="text-gray-600">Contact</p>
                  <p class="font-semibold text-gray-900">+91 98765 11111</p>
                </div>
              </div>
              <p class="text-[10px] text-gray-700 mt-2"><span class="font-semibold">Role:</span> Supervise team, coordinate with customer, ensure quality control</p>
            </div>
          </div>
        </div>

        <!-- Worker 2 -->
        <div class="mb-3 bg-gray-50 p-4 rounded border border-gray-200">
          <div class="flex items-start gap-4">
            <div class="w-[70px] h-[70px] bg-gray-300 rounded-lg flex items-center justify-center text-gray-600 text-[10px]">
              📷<br>Photo
            </div>
            <div class="flex-1">
              <p class="text-[13px] font-bold text-gray-900 mb-1">Vijay Sharma</p>
              <div class="grid grid-cols-3 gap-2 text-[10px]">
                <div>
                  <p class="text-gray-600">Employee ID</p>
                  <p class="font-semibold text-gray-900">EMP-3782</p>
                </div>
                <div>
                  <p class="text-gray-600">Experience</p>
                  <p class="font-semibold text-gray-900">5 Years</p>
                </div>
                <div>
                  <p class="text-gray-600">Contact</p>
                  <p class="font-semibold text-gray-900">+91 98765 22222</p>
                </div>
              </div>
              <p class="text-[10px] text-gray-700 mt-2"><span class="font-semibold">Role:</span> Packing specialist, handle fragile items</p>
            </div>
          </div>
        </div>

        <!-- Worker 3 -->
        <div class="mb-3 bg-gray-50 p-4 rounded border border-gray-200">
          <div class="flex items-start gap-4">
            <div class="w-[70px] h-[70px] bg-gray-300 rounded-lg flex items-center justify-center text-gray-600 text-[10px]">
              📷<br>Photo
            </div>
            <div class="flex-1">
              <p class="text-[13px] font-bold text-gray-900 mb-1">Arun Patel</p>
              <div class="grid grid-cols-3 gap-2 text-[10px]">
                <div>
                  <p class="text-gray-600">Employee ID</p>
                  <p class="font-semibold text-gray-900">EMP-4156</p>
                </div>
                <div>
                  <p class="text-gray-600">Experience</p>
                  <p class="font-semibold text-gray-900">4 Years</p>
                </div>
                <div>
                  <p class="text-gray-600">Contact</p>
                  <p class="font-semibold text-gray-900">+91 98765 33333</p>
                </div>
              </div>
              <p class="text-[10px] text-gray-700 mt-2"><span class="font-semibold">Role:</span> Loading/unloading, heavy lifting</p>
            </div>
          </div>
        </div>

        <!-- Worker 4 -->
        <div class="mb-3 bg-gray-50 p-4 rounded border border-gray-200">
          <div class="flex items-start gap-4">
            <div class="w-[70px] h-[70px] bg-gray-300 rounded-lg flex items-center justify-center text-gray-600 text-[10px]">
              📷<br>Photo
            </div>
            <div class="flex-1">
              <p class="text-[13px] font-bold text-gray-900 mb-1">Mohammed Rafi</p>
              <div class="grid grid-cols-3 gap-2 text-[10px]">
                <div>
                  <p class="text-gray-600">Employee ID</p>
                  <p class="font-semibold text-gray-900">EMP-5234</p>
                </div>
                <div>
                  <p class="text-gray-600">Experience</p>
                  <p class="font-semibold text-gray-900">3 Years</p>
                </div>
                <div>
                  <p class="text-gray-600">Contact</p>
                  <p class="font-semibold text-gray-900">+91 98765 44444</p>
                </div>
              </div>
              <p class="text-[10px] text-gray-700 mt-2"><span class="font-semibold">Role:</span> Furniture disassembly/assembly, general support</p>
            </div>
          </div>
        </div>
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
            <span class="text-[11px] text-gray-800">Transit photos uploaded</span>
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
          <p>You are assigned to Order CC-12345 on Dec 20, 2024 at 09:00 AM.</p>
          <p>Pickup: 123 Oak Street, Whitefield. Report to Team Lead Rajesh Kumar.</p>
          <p class="mt-1">- CargoCore Operations</p>
        </div>
      </div>

      <!-- Notes -->
      <div class="bg-amber-50 border-l-4 border-amber-500 p-3">
        <p class="text-[10px] font-bold text-amber-800 mb-1">⚠ SPECIAL INSTRUCTIONS:</p>
        <ul class="text-[10px] text-gray-700 space-y-1">
          <li>• Customer has antique furniture - handle with extra care</li>
          <li>• 2nd floor delivery - ensure lift is operational</li>
          <li>• All workers must wear company uniform and ID card</li>
        </ul>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup>
import DocumentLayout from './DocumentLayout.vue';
</script>
