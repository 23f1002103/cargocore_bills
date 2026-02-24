<template>
  <div class="min-h-screen bg-gray-100 py-12 px-4">
    <div class="max-w-[850px] mx-auto space-y-12">
      <div class="text-center mb-8">
        <h1 class="text-3xl font-bold text-gray-900 mb-2">CargoCore Document Suite</h1>
        <p class="text-gray-600">Complete set of 11 operational documents for Order CC-12345</p>
      </div>

      <!-- Document 1 -->
      <div class="shadow-2xl">
        <AIVolumeEstimate />
      </div>

      <!-- Document 2 -->
      <div class="shadow-2xl">
        <InstantQuotation />
      </div>

      <!-- Document 3 -->
      <div class="shadow-2xl">
        <BookingConfirmation />
      </div>

      <!-- Document 4 -->
      <div class="shadow-2xl">
        <LaborAssignment />
      </div>

      <!-- Document 5 -->
      <div class="shadow-2xl">
        <DigitalPickList />
      </div>

      <!-- Document 6 -->
      <div class="shadow-2xl">
        <AssetCheckout />
      </div>

      <!-- Document 7 -->
      <div class="shadow-2xl">
        <TripManifest />
      </div>

      <!-- Document 8 -->
      <div class="shadow-2xl">
        <ProofOfDelivery />
      </div>

      <!-- Document 9 -->
      <div class="shadow-2xl">
        <FinalTaxInvoice />
      </div>

      <!-- Document 10 -->
      <div class="shadow-2xl">
        <VehicleSafetyChecklist />
      </div>

      <!-- Document 11 -->
      <div class="shadow-2xl">
        <SalarySlip />
      </div>

      <!-- Footer -->
      <div class="text-center text-gray-600 text-sm py-8">
        <p>All documents generated with CargoCore brand guidelines</p>
        <p class="text-xs mt-1">(c) 2024 CargoCore Logistics Pvt. Ltd. | Bangalore, Karnataka</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import AIVolumeEstimate from './components/AIVolumeEstimate.vue'
import InstantQuotation from './components/InstantQuotation.vue'
import BookingConfirmation from './components/BookingConfirmation.vue'
import LaborAssignment from './components/LaborAssignment.vue'
import DigitalPickList from './components/DigitalPickList.vue'
import AssetCheckout from './components/AssetCheckout.vue'
import TripManifest from './components/TripManifest.vue'
import ProofOfDelivery from './components/ProofOfDelivery.vue'
import FinalTaxInvoice from './components/FinalTaxInvoice.vue'
import VehicleSafetyChecklist from './components/VehicleSafetyChecklist.vue'
import SalarySlip from './components/SalarySlip.vue'
</script>
