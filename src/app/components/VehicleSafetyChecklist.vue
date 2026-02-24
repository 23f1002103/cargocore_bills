<template>
  <DocumentLayout>
    <div class="space-y-6">
      <!-- Title -->
      <div class="text-center border-b-2 border-red-600 pb-3">
        <h1 class="text-[22px] font-bold text-red-600 tracking-wide">VEHICLE SAFETY CHECKLIST</h1>
        <p class="text-[11px] text-gray-600 mt-1">Mandatory Pre-Trip Safety Inspection • Compliance Document</p>
      </div>

      <!-- Trip & Vehicle Details -->
      <div class="grid grid-cols-3 gap-4 bg-gray-50 p-4 rounded-lg">
        <div>
          <p class="text-[10px] text-gray-600 uppercase">Trip ID</p>
          <p class="text-[13px] font-semibold text-gray-900">{{ tripInfo.id }}</p>
        </div>
        <div>
          <p class="text-[10px] text-gray-600 uppercase">Vehicle Number</p>
          <p class="text-[13px] font-semibold text-gray-900">{{ tripInfo.vehicleNumber }}</p>
        </div>
        <div>
          <p class="text-[10px] text-gray-600 uppercase">Inspection Date</p>
          <p class="text-[13px] font-semibold text-gray-900">{{ tripInfo.inspectionDate }}</p>
        </div>
        <div>
          <p class="text-[10px] text-gray-600 uppercase">Driver Name</p>
          <p class="text-[13px] font-semibold text-gray-900">{{ tripInfo.driverName }}</p>
        </div>
        <div>
          <p class="text-[10px] text-gray-600 uppercase">Vehicle Type</p>
          <p class="text-[13px] font-semibold text-gray-900">{{ tripInfo.vehicleType }}</p>
        </div>
        <div>
          <p class="text-[10px] text-gray-600 uppercase">Route</p>
          <p class="text-[13px] font-semibold text-gray-900">{{ tripInfo.route }}</p>
        </div>
      </div>

      <!-- Safety Inspection Checklist -->
      <div>
        <div class="bg-red-600 text-white px-4 py-2 font-semibold text-[12px] uppercase tracking-wide">
          Critical Safety Items
        </div>
        
        <!-- Table -->
        <table class="w-full border-collapse">
          <thead>
            <tr class="bg-gray-100 border-b border-gray-300">
              <th class="text-left px-4 py-2 text-[10px] font-semibold text-gray-700 uppercase w-[5%]">#</th>
              <th class="text-left px-4 py-2 text-[10px] font-semibold text-gray-700 uppercase w-[45%]">Inspection Item</th>
              <th class="text-center px-4 py-2 text-[10px] font-semibold text-gray-700 uppercase w-[15%]">Status</th>
              <th class="text-left px-4 py-2 text-[10px] font-semibold text-gray-700 uppercase w-[35%]">Remarks</th>
            </tr>
          </thead>
          <tbody class="text-[11px]">
            <tr v-for="(check, index) in safetyChecks" :key="index" class="border-b border-gray-200">
              <td class="px-4 py-2 text-center text-gray-600">{{ index + 1 }}</td>
              <td class="px-4 py-2 text-gray-900">{{ check.item }}</td>
              <td class="px-4 py-2 text-center">
                <span class="inline-block bg-green-100 text-green-700 px-3 py-1 rounded-full text-[10px] font-semibold">
                  {{ check.status }}
                </span>
              </td>
              <td class="px-4 py-2 text-gray-700">{{ check.remarks }}</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Additional Observations -->
      <div class="border border-gray-300 rounded-lg p-4">
        <p class="text-[11px] font-semibold text-gray-800 mb-2">Additional Observations / Issues:</p>
        <p class="text-[10px] text-gray-600 italic">No additional issues or concerns noted. Vehicle is in good operational condition and safe for trip.</p>
      </div>

      <!-- Odometer Readings -->
      <div class="grid grid-cols-2 gap-4">
        <div class="border border-gray-300 rounded-lg p-4">
          <p class="text-[10px] text-gray-600 uppercase mb-1">Pre-Trip Odometer</p>
          <p class="text-[16px] font-bold text-gray-900">{{ odometer.preTripReading }}</p>
        </div>
        <div class="border border-gray-300 rounded-lg p-4">
          <p class="text-[10px] text-gray-600 uppercase mb-1">Next Service Due</p>
          <p class="text-[16px] font-bold text-orange-600">{{ odometer.nextServiceDue }}</p>
        </div>
      </div>

      <!-- Compliance Declaration -->
      <div class="bg-red-50 border-l-4 border-red-600 p-4">
        <p class="text-[11px] text-gray-800 font-semibold mb-2">⚠️ COMPLIANCE DECLARATION</p>
        <p class="text-[10px] text-gray-700 leading-relaxed">
          I hereby certify that I have thoroughly inspected the above-mentioned vehicle and confirm that all safety systems 
          are functioning properly. The vehicle is roadworthy and meets all safety compliance standards. I understand that 
          operating an unsafe vehicle is a violation of company policy and traffic regulations.
        </p>
      </div>

      <!-- Signatures -->
      <div class="grid grid-cols-2 gap-6 pt-4">
        <div class="border-t-2 border-gray-300 pt-3">
          <p class="text-[11px] text-gray-900 font-semibold">Driver Signature</p>
          <p class="text-[9px] text-gray-600 mt-1">{{ tripInfo.driverName }}</p>
          <p class="text-[9px] text-gray-500">Date: {{ tripInfo.inspectionDate }}</p>
        </div>
        <div class="border-t-2 border-gray-300 pt-3">
          <p class="text-[11px] text-gray-900 font-semibold">Inspector Signature</p>
          <p class="text-[9px] text-gray-600 mt-1">{{ inspector.name }} ({{ inspector.title }})</p>
          <p class="text-[9px] text-gray-500">Date: {{ tripInfo.inspectionDate }}</p>
        </div>
      </div>

      <!-- Important Notes -->
      <div class="bg-yellow-50 border border-yellow-300 rounded-lg p-4">
        <p class="text-[10px] font-semibold text-gray-800 mb-2">📋 IMPORTANT NOTES:</p>
        <ul class="text-[9px] text-gray-700 space-y-1 ml-4 list-disc">
          <li>This inspection must be completed before EVERY trip departure</li>
          <li>Any item marked as "Not OK" must be resolved before vehicle can depart</li>
          <li>Driver must carry this checklist during the trip for compliance verification</li>
          <li>Original copy to be submitted to fleet manager within 24 hours</li>
          <li>Failure to complete this inspection may result in disciplinary action</li>
        </ul>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup>
import DocumentLayout from './DocumentLayout.vue';

const props = defineProps({
  tripInfo: {
    type: Object,
    default: () => ({
      id: 'TRP-7891',
      vehicleNumber: 'KA-51-MN-2347',
      inspectionDate: 'December 17, 2024 • 06:30 AM',
      driverName: 'Rajesh Kumar',
      vehicleType: '24 Feet Closed Body Truck',
      route: 'Bangalore → Chennai'
    })
  },
  odometer: {
    type: Object,
    default: () => ({ preTripReading: '47,852 KM', nextServiceDue: '50,000 KM' })
  },
  inspector: {
    type: Object,
    default: () => ({ name: 'Suresh Sharma', title: 'Operations Supervisor' })
  },
  safetyChecks: {
    type: Array,
    default: () => [
      { item: 'Engine oil level & condition', status: '✓ OK', remarks: 'Level normal, no leaks' },
      { item: 'Coolant level & radiator condition', status: '✓ OK', remarks: 'Topped up, no issues' },
      { item: 'Brake fluid level', status: '✓ OK', remarks: 'Within range' },
      { item: 'Tire pressure (all wheels)', status: '✓ OK', remarks: 'Front: 90 PSI, Rear: 95 PSI' },
      { item: 'Tire tread depth & wear', status: '✓ OK', remarks: 'All tires above minimum' },
      { item: 'Brake system functionality', status: '✓ OK', remarks: 'Foot & hand brakes tested' },
      { item: 'Headlights (high & low beam)', status: '✓ OK', remarks: 'All functioning' },
      { item: 'Tail lights & brake lights', status: '✓ OK', remarks: 'Working properly' },
      { item: 'Turn signals & hazard lights', status: '✓ OK', remarks: 'Left & right tested' },
      { item: 'Horn & reverse alarm', status: '✓ OK', remarks: 'Audible & clear' },
      { item: 'Windshield & wiper condition', status: '✓ OK', remarks: 'Clean, wipers functional' },
      { item: 'Side & rear view mirrors', status: '✓ OK', remarks: 'Adjusted & intact' },
      { item: 'Seat belts & safety harness', status: '✓ OK', remarks: 'Driver & co-driver checked' },
      { item: 'Fire extinguisher', status: '✓ OK', remarks: 'Valid till: Mar 2025' },
      { item: 'First aid kit', status: '✓ OK', remarks: 'Complete & accessible' },
      { item: 'Warning triangle & reflectors', status: '✓ OK', remarks: '2 triangles available' },
      { item: 'Fuel level & tank condition', status: '✓ OK', remarks: 'Full tank, no leaks' },
      { item: 'Battery condition & terminals', status: '✓ OK', remarks: 'Secure, no corrosion' },
      { item: 'Cargo securing equipment', status: '✓ OK', remarks: 'Ropes & straps checked' },
      { item: 'Emergency exit & door locks', status: '✓ OK', remarks: 'All operational' }
    ]
  }
})
</script>
