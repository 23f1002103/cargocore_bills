<template>
  <DocumentLayout>
    <div class="space-y-6">
      <!-- Title -->
      <div class="text-center border-b-2 border-blue-900 pb-3">
        <h1 class="text-[22px] font-bold text-blue-900 tracking-wide">TAX INVOICE</h1>
        <p class="text-[11px] text-gray-600 mt-1">Original Copy • For Recipient</p>
      </div>

      <!-- PAID Status -->
      <div class="text-center">
        <div class="inline-block bg-green-600 text-white px-8 py-3 rounded-lg">
          <span class="text-[18px] font-bold">✓ PAID IN FULL</span>
        </div>
      </div>

      <!-- Invoice Details -->
      <div class="grid grid-cols-2 gap-4">
        <div class="bg-blue-50 p-4 rounded-lg border border-blue-200">
          <h3 class="text-[11px] font-bold text-blue-900 mb-3">INVOICE DETAILS</h3>
          <div class="space-y-2 text-[11px]">
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Invoice No:</span>
              <span class="font-semibold text-gray-900">INV-2024-12-0567</span>
            </div>
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Invoice Date:</span>
              <span class="font-semibold text-gray-900">December 20, 2024</span>
            </div>
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Order ID:</span>
              <span class="font-semibold text-gray-900">CC-12345</span>
            </div>
            <div class="grid grid-cols-2">
              <span class="text-gray-600">Payment Status:</span>
              <span class="font-semibold text-green-600">PAID</span>
            </div>
          </div>
        </div>
        <div class="bg-gray-50 p-4 rounded-lg border border-gray-300">
          <h3 class="text-[11px] font-bold text-gray-800 mb-3">COMPANY DETAILS</h3>
          <div class="text-[10px] text-gray-700 space-y-1">
            <p class="font-semibold text-[11px] text-gray-900">CargoCore Logistics Pvt. Ltd.</p>
            <p>Koramangala, Bangalore</p>
            <p>Karnataka - 560034, India</p>
            <p class="mt-2"><span class="font-semibold">GSTIN:</span> 29AABCC1234F1Z5</p>
            <p><span class="font-semibold">PAN:</span> AABCC1234F</p>
            <p><span class="font-semibold">CIN:</span> U63030KA2020PTC135678</p>
          </div>
        </div>
      </div>

      <!-- Customer Details -->
      <div class="bg-gray-50 p-4 rounded-lg border border-gray-300">
        <h3 class="text-[11px] font-bold text-gray-800 mb-2">BILL TO</h3>
        <div class="text-[11px]">
          <p class="font-semibold text-gray-900">Sarah Khan</p>
          <p class="text-gray-700">456 Maple Avenue, Indiranagar</p>
          <p class="text-gray-700">Bangalore, Karnataka - 560038</p>
          <p class="text-gray-700 mt-1">Phone: +91 98765 43210</p>
          <p class="text-gray-700">Email: sarah.khan@email.com</p>
        </div>
      </div>

      <!-- Service Details -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">SERVICE DETAILS</h3>
        <table class="w-full text-[11px]">
          <thead>
            <tr class="bg-gray-200 text-gray-700">
              <th class="text-left p-2 border border-gray-300">Description</th>
              <th class="text-center p-2 border border-gray-300 w-[60px]">SAC</th>
              <th class="text-right p-2 border border-gray-300 w-[80px]">Amount (₹)</th>
            </tr>
          </thead>
          <tbody class="text-gray-800">
            <tr>
              <td class="p-2 border border-gray-300">
                <p class="font-semibold">Transportation Service</p>
                <p class="text-[9px] text-gray-600">14 ft covered truck, 18.5 km distance</p>
                <p class="text-[9px] text-gray-600">From: 123 Oak Street, Whitefield to 456 Maple Avenue, Indiranagar</p>
              </td>
              <td class="text-center p-2 border border-gray-300">996791</td>
              <td class="text-right p-2 border border-gray-300">1,800.00</td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">
                <p class="font-semibold">Labor Charges</p>
                <p class="text-[9px] text-gray-600">4 skilled workers for loading & unloading</p>
              </td>
              <td class="text-center p-2 border border-gray-300">998511</td>
              <td class="text-right p-2 border border-gray-300">1,600.00</td>
            </tr>
            <tr>
              <td class="p-2 border border-gray-300">
                <p class="font-semibold">Packing Materials</p>
                <p class="text-[9px] text-gray-600">28 boxes, bubble wrap, tape, foam sheets, etc.</p>
              </td>
              <td class="text-center p-2 border border-gray-300">998511</td>
              <td class="text-right p-2 border border-gray-300">700.00</td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">
                <p class="font-semibold">Professional Packing Service</p>
                <p class="text-[9px] text-gray-600">Complete packing by trained team</p>
              </td>
              <td class="text-center p-2 border border-gray-300">998511</td>
              <td class="text-right p-2 border border-gray-300">400.00</td>
            </tr>
            <tr>
              <td class="p-2 border border-gray-300">
                <p class="font-semibold">Transit Insurance</p>
                <p class="text-[9px] text-gray-600">Coverage up to ₹50,000</p>
              </td>
              <td class="text-center p-2 border border-gray-300">997211</td>
              <td class="text-right p-2 border border-gray-300">0.00</td>
            </tr>
            <tr class="bg-blue-50 font-semibold">
              <td class="p-2 border border-gray-300" colspan="2">SUBTOTAL (Before Tax)</td>
              <td class="text-right p-2 border border-gray-300">4,500.00</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- GST Breakdown -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">GST BREAKDOWN</h3>
        <table class="w-full text-[11px]">
          <thead>
            <tr class="bg-gray-200 text-gray-700">
              <th class="text-left p-2 border border-gray-300">Tax Type</th>
              <th class="text-center p-2 border border-gray-300 w-[80px]">Rate</th>
              <th class="text-right p-2 border border-gray-300 w-[100px]">Taxable Amt</th>
              <th class="text-right p-2 border border-gray-300 w-[80px]">Tax Amount</th>
            </tr>
          </thead>
          <tbody class="text-gray-800">
            <tr>
              <td class="p-2 border border-gray-300">CGST (Central GST)</td>
              <td class="text-center p-2 border border-gray-300">0%</td>
              <td class="text-right p-2 border border-gray-300">4,500.00</td>
              <td class="text-right p-2 border border-gray-300">0.00</td>
            </tr>
            <tr class="bg-gray-50">
              <td class="p-2 border border-gray-300">SGST (State GST)</td>
              <td class="text-center p-2 border border-gray-300">0%</td>
              <td class="text-right p-2 border border-gray-300">4,500.00</td>
              <td class="text-right p-2 border border-gray-300">0.00</td>
            </tr>
            <tr class="bg-blue-100 font-semibold">
              <td class="p-2 border border-gray-300" colspan="3">TOTAL GST (18%)</td>
              <td class="text-right p-2 border border-gray-300">0.00</td>
            </tr>
          </tbody>
        </table>
        <p class="text-[9px] text-gray-600 mt-2 italic">* Small transporters exemption applied as per GST Notification 11/2017</p>
      </div>

      <!-- Amount Summary -->
      <div class="bg-gradient-to-r from-blue-900 to-blue-700 text-white p-5 rounded-lg">
        <div class="space-y-3 text-[13px]">
          <div class="flex justify-between pb-2 border-b border-white/20">
            <span>Subtotal</span>
            <span class="font-semibold">₹4,500.00</span>
          </div>
          <div class="flex justify-between pb-2 border-b border-white/20">
            <span>GST (18%)</span>
            <span class="font-semibold">₹0.00</span>
          </div>
          <div class="flex justify-between items-center pt-2">
            <span class="text-[15px] font-bold">GRAND TOTAL</span>
            <span class="text-[24px] font-bold">₹4,500.00</span>
          </div>
          <p class="text-[10px] opacity-90 text-center pt-2 border-t border-white/20">
            Amount in words: <span class="font-semibold">Four Thousand Five Hundred Rupees Only</span>
          </p>
        </div>
      </div>

      <!-- Estimated vs Actual -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">QUOTATION vs ACTUAL COMPARISON</h3>
        <table class="w-full text-[11px]">
          <thead>
            <tr class="bg-gray-200 text-gray-700">
              <th class="text-left p-2 border border-gray-300">Item</th>
              <th class="text-right p-2 border border-gray-300 w-[100px]">Quoted (₹)</th>
              <th class="text-right p-2 border border-gray-300 w-[100px]">Actual (₹)</th>
              <th class="text-right p-2 border border-gray-300 w-[100px]">Difference</th>
            </tr>
          </thead>
          <tbody class="text-gray-800">
            <tr>
              <td class="p-2 border border-gray-300">Total Service Amount</td>
              <td class="text-right p-2 border border-gray-300">4,500.00</td>
              <td class="text-right p-2 border border-gray-300">4,500.00</td>
              <td class="text-right p-2 border border-gray-300 text-green-600 font-semibold">0.00</td>
            </tr>
          </tbody>
        </table>
        <p class="text-[10px] text-green-700 font-semibold mt-2">✓ Final amount matches the initial quotation - no additional charges</p>
      </div>

      <!-- Payment Details -->
      <div>
        <h3 class="text-[13px] font-bold text-gray-800 mb-3 pb-2 border-b border-gray-300">PAYMENT DETAILS</h3>
        <table class="w-full text-[11px]">
          <thead>
            <tr class="bg-gray-200 text-gray-700">
              <th class="text-left p-2 border border-gray-300">Payment Stage</th>
              <th class="text-center p-2 border border-gray-300 w-[100px]">Date</th>
              <th class="text-center p-2 border border-gray-300 w-[100px]">Mode</th>
              <th class="text-right p-2 border border-gray-300 w-[100px]">Amount (₹)</th>
            </tr>
          </thead>
          <tbody class="text-gray-800">
            <tr class="bg-green-50">
              <td class="p-2 border border-gray-300">Advance Payment (30%)</td>
              <td class="text-center p-2 border border-gray-300">Dec 16, 2024</td>
              <td class="text-center p-2 border border-gray-300">UPI</td>
              <td class="text-right p-2 border border-gray-300">1,350.00</td>
            </tr>
            <tr class="bg-green-50">
              <td class="p-2 border border-gray-300">Balance Payment (70%)</td>
              <td class="text-center p-2 border border-gray-300">Dec 20, 2024</td>
              <td class="text-center p-2 border border-gray-300">Cash</td>
              <td class="text-right p-2 border border-gray-300">3,150.00</td>
            </tr>
            <tr class="bg-green-200 font-bold">
              <td class="p-2 border border-gray-300" colspan="3">TOTAL PAID</td>
              <td class="text-right p-2 border border-gray-300">4,500.00</td>
            </tr>
          </tbody>
        </table>
      </div>

      <!-- Bank Details -->
      <div class="bg-blue-50 p-4 rounded-lg border border-blue-200">
        <h3 class="text-[11px] font-bold text-blue-900 mb-2">BANK DETAILS (For Future Reference)</h3>
        <div class="grid grid-cols-2 gap-3 text-[10px]">
          <div>
            <p class="text-gray-600">Bank Name:</p>
            <p class="font-semibold text-gray-900">HDFC Bank</p>
          </div>
          <div>
            <p class="text-gray-600">Account Name:</p>
            <p class="font-semibold text-gray-900">CargoCore Logistics Pvt Ltd</p>
          </div>
          <div>
            <p class="text-gray-600">Account Number:</p>
            <p class="font-semibold text-gray-900">50200012345678</p>
          </div>
          <div>
            <p class="text-gray-600">IFSC Code:</p>
            <p class="font-semibold text-gray-900">HDFC0001234</p>
          </div>
        </div>
      </div>

      <!-- Terms & Conditions -->
      <div class="bg-gray-50 p-4 rounded border border-gray-300">
        <h3 class="text-[11px] font-bold text-gray-800 mb-2">TERMS & CONDITIONS</h3>
        <ul class="text-[9px] text-gray-700 space-y-1">
          <li>1. This invoice is computer-generated and does not require a physical signature.</li>
          <li>2. All disputes subject to Bangalore jurisdiction only.</li>
          <li>3. Payment once made is non-refundable.</li>
          <li>4. Our liability is limited to the declared value of goods.</li>
          <li>5. Goods once delivered will not be taken back.</li>
          <li>6. E. & O.E. (Errors and Omissions Excepted)</li>
        </ul>
      </div>

      <!-- Authorization -->
      <div class="text-center pt-4">
        <p class="text-[11px] font-semibold text-gray-800 mb-1">For CargoCore Logistics Pvt. Ltd.</p>
        <div class="h-[50px] flex items-center justify-center">
          <p class="text-[10px] text-gray-600 italic">(Digitally Authorized)</p>
        </div>
        <p class="text-[10px] text-gray-700 font-semibold">Authorized Signatory</p>
      </div>

      <!-- Thank You Note -->
      <div class="bg-gradient-to-r from-green-600 to-green-500 text-white p-4 rounded-lg text-center">
        <p class="text-[13px] font-bold mb-1">Thank You For Your Business!</p>
        <p class="text-[10px] opacity-90">We look forward to serving you again. For queries: support@cargocore.com | 1800-CARGO-00</p>
      </div>
    </div>
  </DocumentLayout>
</template>

<script setup lang="ts">
import DocumentLayout from './DocumentLayout.vue';
</script>
