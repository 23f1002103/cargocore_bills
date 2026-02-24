<template>
  <DocumentLayout>
    <div class="space-y-6">
      <!-- Title -->
      <div class="text-center border-b-2 border-blue-900 pb-3">
        <h1 class="text-[22px] font-bold text-blue-900 tracking-wide">TRIP MANIFEST</h1>
        <p class="text-[11px] text-gray-600 mt-1">Route Plan & Journey Documentation</p>
      </div>

      <!-- Trip Details -->
      <div class="bg-gradient-to-r from-blue-900 to-blue-700 text-white p-5 rounded-lg">
        <div class="grid grid-cols-3 gap-4">
          <div>
            <p class="text-[10px] opacity-80 uppercase">Trip ID</p>
            <p class="text-[15px] font-bold">{{ trip.id }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Order ID</p>
            <p class="text-[15px] font-bold">{{ order.id }}</p>
          </div>
          <div>
            <p class="text-[10px] opacity-80 uppercase">Trip Date</p>
            <p class="text-[13px] font-semibold">{{ trip.date }}</p>
          </div>
        </div>
      </div>

      <!-- Driver & Vehicle Info -->
      <div class="grid grid-cols-2 gap-4">
        <div class="bg-blue-50 p-4 rounded-lg border border-blue-200">
          <h3 class="text-[11px] font-bold text-blue-900 mb-3">👤 DRIVER INFORMATION</h3>
          <div class="space-y-2 text-[11px]">
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Name:</span>
              <span class="font-semibold text-gray-900">{{ driver.name }}</span>
            </div>
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Employee ID:</span>
              <span class="font-semibold text-gray-900">{{ driver.employeeId }}</span>
            </div>
            <div class="grid grid-cols-2">
              <span class="text-gray-600">License No:</span>
              <span class="font-semibold text-gray-900">{{ driver.licenseNo }}</span>
            </div>
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Contact:</span>
              <span class="font-semibold text-gray-900">{{ driver.phone }}</span>
            </div>
          </div>
        </div>
        <div class="bg-green-50 p-4 rounded-lg border border-green-200">
          <h3 class="text-[11px] font-bold text-green-900 mb-3">🚚 VEHICLE INFORMATION</h3>
          <div class="space-y-2 text-[11px]">
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Vehicle No:</span>
              <span class="font-semibold text-gray-900">{{ vehicle.number }}</span>
            </div>
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Type:</span>
              <span class="font-semibold text-gray-900">{{ vehicle.type }}</span>
            </div>
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Capacity:</span>
              <span class="font-semibold text-gray-900">{{ vehicle.capacity }}</span>
            </div>
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Fuel Start:</span>
              <span class="font-semibold text-gray-900">{{ vehicle.fuelStart }}</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Route Map Placeholder -->
      <div class="border-2 border-gray-300 rounded-lg p-4 bg-gray-50">
        <h3 class="text-[11px] font-bold text-gray-800 mb-3">🗺️ ROUTE MAP</h3>
        <div class="w-full h-[180px] bg-gradient-to-br from-blue-100 to-green-100 rounded border-2 border-dashed border-gray-400 flex items-center justify-center">
          <div class="text-center">
            <div class="text-[40px] mb-2">🗺️</div>
            <p class="text-[12px] text-gray-700 font-semibold">GPS Route: {{ route.from }} → {{ route.to }}</p>
            <p class="text-[10px] text-gray-600 mt-1">Distance: {{ route.distance }} | Est. Time: {{ route.estTime }}</p>
            <p class="text-[10px] text-gray-600">Via: {{ route.via }}</p>
          </div>
        </div>
      </div>

      <!-- Stop Schedule -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">STOP SCHEDULE & TIMELINE</h3>
        
        <!-- Stop 1 - Pickup -->
        <div class="mb-3 bg-blue-50 border-l-4 border-blue-600 p-4 rounded">
          <div class="flex items-start gap-3">
            <div class="bg-blue-600 text-white w-[30px] h-[30px] rounded-full flex items-center justify-center font-bold text-[14px]">1</div>
            <div class="flex-1">
              <div class="flex justify-between items-start mb-2">
                <div>
                  <p class="text-[12px] font-bold text-blue-900">PICKUP LOCATION</p>
                  <p class="text-[11px] text-gray-700">{{ pickup.address }}</p>
                </div>
                <div class="text-right">
                  <p class="text-[10px] text-gray-600">Scheduled Time</p>
                  <p class="text-[13px] font-bold text-blue-900">{{ pickup.scheduledTime }}</p>
                </div>
              </div>
              <div class="grid grid-cols-3 gap-2 text-[10px] bg-white p-2 rounded">
                <div>
                  <p class="text-gray-600">Contact Person</p>
                  <p class="font-semibold text-gray-900">{{ pickup.contact }}</p>
                </div>
                <div>
                  <p class="text-gray-600">Phone</p>
                  <p class="font-semibold text-gray-900">{{ pickup.phone }}</p>
                </div>
                <div>
                  <p class="text-gray-600">Est. Loading Time</p>
                  <p class="font-semibold text-gray-900">{{ pickup.loadingTime }}</p>
                </div>
              </div>
              <div class="mt-2 flex items-center gap-2">
                <span class="text-[10px] text-gray-600">Actual Arrival:</span>
                <div class="border-b border-blue-400 flex-1 h-[20px]"></div>
                <span class="text-[10px] text-gray-600">Departure:</span>
                <div class="border-b border-blue-400 flex-1 h-[20px]"></div>
              </div>
            </div>
          </div>
        </div>

        <!-- Stop 2 - Delivery -->
        <div class="mb-3 bg-green-50 border-l-4 border-green-600 p-4 rounded">
          <div class="flex items-start gap-3">
            <div class="bg-green-600 text-white w-[30px] h-[30px] rounded-full flex items-center justify-center font-bold text-[14px]">2</div>
            <div class="flex-1">
              <div class="flex justify-between items-start mb-2">
                <div>
                  <p class="text-[12px] font-bold text-green-900">DELIVERY LOCATION</p>
                  <p class="text-[11px] text-gray-700">{{ delivery.address }}</p>
                </div>
                <div class="text-right">
                  <p class="text-[10px] text-gray-600">Scheduled Time</p>
                  <p class="text-[13px] font-bold text-green-900">{{ delivery.scheduledTime }}</p>
                </div>
              </div>
              <div class="grid grid-cols-3 gap-2 text-[10px] bg-white p-2 rounded">
                <div>
                  <p class="text-gray-600">Contact Person</p>
                  <p class="font-semibold text-gray-900">{{ delivery.contact }}</p>
                </div>
                <div>
                  <p class="text-gray-600">Phone</p>
                  <p class="font-semibold text-gray-900">{{ delivery.phone }}</p>
                </div>
                <div>
                  <p class="text-gray-600">Est. Unloading Time</p>
                  <p class="font-semibold text-gray-900">{{ delivery.unloadingTime }}</p>
                </div>
              </div>
              <div class="mt-2 flex items-center gap-2">
                <span class="text-[10px] text-gray-600">Actual Arrival:</span>
                <div class="border-b border-green-400 flex-1 h-[20px]"></div>
                <span class="text-[10px] text-gray-600">Completion:</span>
                <div class="border-b border-green-400 flex-1 h-[20px]"></div>
              </div>
            </div>
          </div>
        </div>

        <!-- Stop 3 - Return to Depot -->
        <div class="bg-gray-50 border-l-4 border-gray-600 p-4 rounded">
          <div class="flex items-start gap-3">
            <div class="bg-gray-600 text-white w-[30px] h-[30px] rounded-full flex items-center justify-center font-bold text-[14px]">3</div>
            <div class="flex-1">
              <div class="flex justify-between items-start mb-2">
                <div>
                  <p class="text-[12px] font-bold text-gray-900">RETURN TO DEPOT</p>
                  <p class="text-[11px] text-gray-700">CargoCore Logistics Depot, Koramangala, Bangalore</p>
                </div>
                <div class="text-right">
                  <p class="text-[10px] text-gray-600">Expected Return</p>
                  <p class="text-[13px] font-bold text-gray-900">02:30 PM</p>
                </div>
              </div>
              <div class="mt-2 flex items-center gap-2">
                <span class="text-[10px] text-gray-600">Actual Return Time:</span>
                <div class="border-b border-gray-400 flex-1 h-[20px]"></div>
                <span class="text-[10px] text-gray-600">Odometer End:</span>
                <div class="border-b border-gray-400 flex-1 h-[20px]"></div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <!-- Trip Statistics -->
      <div class="grid grid-cols-4 gap-3">
        <div class="bg-gradient-to-br from-blue-600 to-blue-500 text-white p-3 rounded text-center">
          <p class="text-[10px] opacity-90">Total Distance</p>
          <p class="text-[20px] font-bold">{{ stats.totalDistance }}</p>
        </div>
        <div class="bg-gradient-to-br from-green-600 to-green-500 text-white p-3 rounded text-center">
          <p class="text-[10px] opacity-90">Est. Duration</p>
          <p class="text-[20px] font-bold">{{ stats.estDuration }}</p>
        </div>
        <div class="bg-gradient-to-br from-purple-600 to-purple-500 text-white p-3 rounded text-center">
          <p class="text-[10px] opacity-90">Fuel Estimate</p>
          <p class="text-[20px] font-bold">{{ stats.fuelEstimate }}</p>
        </div>
        <div class="bg-gradient-to-br from-orange-600 to-orange-500 text-white p-3 rounded text-center">
          <p class="text-[10px] opacity-90">Total Stops</p>
          <p class="text-[20px] font-bold">{{ stats.totalStops }}</p>
        </div>
      </div>

      <!-- Cargo Details -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">CARGO SUMMARY</h3>
        <div class="bg-gray-50 p-4 rounded border border-gray-300">
          <div class="grid grid-cols-3 gap-4 text-[11px]">
            <div>
              <p class="text-gray-600 mb-1">Total Boxes/Items</p>
              <p class="text-[16px] font-bold text-gray-900">{{ cargo.boxes }}</p>
            </div>
            <div>
              <p class="text-gray-600 mb-1">Estimated Weight</p>
              <p class="text-[16px] font-bold text-gray-900">{{ cargo.weight }}</p>
            </div>
            <div>
              <p class="text-gray-600 mb-1">Special Items</p>
              <p class="text-[16px] font-bold text-gray-900">{{ cargo.specialItems }}</p>
            </div>
          </div>
          <div class="mt-3 pt-3 border-t border-gray-300">
            <p class="text-[10px] font-semibold text-gray-700 mb-1">Notes:</p>
            <p class="text-[10px] text-gray-600">{{ cargo.notes }}</p>
          </div>
        </div>
      </div>

      <!-- Signatures -->
      <div class="border-2 border-gray-300 rounded-lg p-4">
        <h3 class="text-[11px] font-bold text-gray-800 mb-3">TRIP VERIFICATION</h3>
        <div class="grid grid-cols-2 gap-4">
          <div>
            <p class="text-[10px] text-gray-600 mb-2">Driver Signature (Start):</p>
            <div class="border-b-2 border-gray-400 h-[40px]"></div>
            <p class="text-[9px] text-gray-500 mt-1">Time: ___________ Odometer: ___________</p>
          </div>
          <div>
            <p class="text-[10px] text-gray-600 mb-2">Supervisor Signature:</p>
            <div class="border-b-2 border-gray-400 h-[40px]"></div>
            <p class="text-[9px] text-gray-500 mt-1">Name: ___________________</p>
          </div>
        </div>
      </div>

      <!-- Emergency Contact -->
      <div class="bg-red-50 border-l-4 border-red-500 p-3">
        <p class="text-[10px] font-bold text-red-800 mb-1">🚨 EMERGENCY CONTACTS:</p>
        <div class="grid grid-cols-2 gap-2 text-[10px] text-gray-700">
          <div>Operations Manager: <span class="font-semibold">+91 98765 00001</span></div>
          <div>Customer Support: <span class="font-semibold">1800-CARGO-00</span></div>
          <div>Roadside Assistance: <span class="font-semibold">+91 98765 00002</span></div>
          <div>Police/Emergency: <span class="font-semibold">100 / 112</span></div>
        </div>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup>
import DocumentLayout from './DocumentLayout.vue';

const props = defineProps({
  trip: {
    type: Object,
    default: () => ({ id: 'TRP-CC-12345', date: 'December 20, 2024' })
  },
  order: {
    type: Object,
    default: () => ({ id: 'CC-12345' })
  },
  driver: {
    type: Object,
    default: () => ({ name: 'Prakash Reddy', employeeId: 'DRV-8765', licenseNo: 'KA07-20210012345', phone: '+91 98765 55555' })
  },
  vehicle: {
    type: Object,
    default: () => ({ number: 'KA 01 MN 5678', type: '14 ft Covered Truck', capacity: '3.5 Tons', fuelStart: '85% (68 Liters)' })
  },
  route: {
    type: Object,
    default: () => ({
      from: 'Whitefield',
      to: 'Indiranagar',
      distance: '18.5 km',
      estTime: '45 minutes',
      via: 'Outer Ring Road → MG Road → Indiranagar Main Road'
    })
  },
  pickup: {
    type: Object,
    default: () => ({
      address: '123 Oak Street, Whitefield, Bangalore - 560066',
      scheduledTime: '09:00 AM',
      contact: 'Sarah Khan',
      phone: '+91 98765 43210',
      loadingTime: '90 minutes'
    })
  },
  delivery: {
    type: Object,
    default: () => ({
      address: '456 Maple Avenue, Indiranagar, Bangalore - 560038',
      scheduledTime: '12:00 PM',
      contact: 'Sarah Khan',
      phone: '+91 98765 43210',
      unloadingTime: '75 minutes'
    })
  },
  stats: {
    type: Object,
    default: () => ({ totalDistance: '18.5 km', estDuration: '5.5 hrs', fuelEstimate: '8 L', totalStops: 3 })
  },
  cargo: {
    type: Object,
    default: () => ({
      boxes: '28 boxes',
      weight: '850 kg',
      specialItems: '2 fragile',
      notes: '• Handle with care: Glass items, electronics • Antique furniture pieces • Priority delivery'
    })
  }
})
</script>
