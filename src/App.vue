<script setup lang="ts">
import { ref } from 'vue'
import ChallanPrint from './components/ChallanPrint.vue'

const rollNo = ref('')
const name = ref('')
const fatherName = ref('')
const program = ref('')
const showPrintView = ref(false)

const programFees = [
  {
    id: 'ssc',
    name: 'SSC',
    fee: 5000,
    duration: '2 Years',
    description: 'Secondary School Certificate',
  },
  {
    id: 'hssc',
    name: 'HSSC',
    fee: 8000,
    duration: '2 Years',
    description: 'Higher Secondary School Certificate',
  },
  {
    id: 'bachelors',
    name: 'Bachelors',
    fee: 15000,
    duration: '4 Years',
    description: "Bachelor's Degree Program",
  },
  {
    id: 'postgraduate',
    name: 'POST GRADUATE',
    fee: 20000,
    duration: '2 Years',
    description: 'Post Graduate Program',
  },
]

const generateChallanNo = () => {
  return '251712642924' // Dummy challan number for now
}

const printChallan = () => {
  showPrintView.value = true
  // Use setTimeout to ensure the print dialog opens after the view is rendered
  setTimeout(() => {
    window.print()
  }, 100)
}
</script>

<template>
  <div v-if="!showPrintView" class="min-h-screen flex items-center justify-center">
    <div class="w-full max-w-3xl mx-auto">
      <div class="bg-white rounded-xl shadow-lg overflow-hidden">
        <!-- Header Section -->
        <div class="bg-blue-600 px-6 py-8">
          <h1 class="text-4xl font-bold text-white text-center tracking-wide">
            ONLINE CHALLAN FORM
          </h1>
        </div>

        <!-- Form Section -->
        <div class="px-8 py-10">
          <form @submit.prevent="printChallan" class="space-y-8">
            <div class="grid grid-cols-1 gap-8">
              <!-- Roll No Field -->
              <div class="flex flex-col gap-2">
                <label for="rollNo" class="text-base font-bold">Roll No</label>
                <input
                  type="text"
                  id="rollNo"
                  v-model="rollNo"
                  class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:ring-2 focus:ring-blue-500 focus:border-blue-500 transition-colors duration-200"
                  placeholder="Enter your roll number"
                  required
                />
              </div>

              <!-- Name Field -->
              <div class="flex flex-col gap-2">
                <label for="name" class="text-base font-bold">Name</label>
                <input
                  type="text"
                  id="name"
                  v-model="name"
                  class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:ring-2 focus:ring-blue-500 focus:border-blue-500 transition-colors duration-200"
                  placeholder="Enter your full name"
                  required
                />
              </div>

              <!-- Father Name Field -->
              <div class="flex flex-col gap-2">
                <label for="fatherName" class="text-base font-bold">Father Name</label>
                <input
                  type="text"
                  id="fatherName"
                  v-model="fatherName"
                  class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:ring-2 focus:ring-blue-500 focus:border-blue-500 transition-colors duration-200"
                  placeholder="Enter your father's name"
                  required
                />
              </div>

              <!-- Program Selection -->
              <div class="flex flex-col gap-2">
                <label for="program" class="text-base font-bold">Select Program</label>
                <select
                  id="program"
                  v-model="program"
                  class="w-full px-4 py-3 rounded-lg border border-gray-300 focus:ring-2 focus:ring-blue-500 focus:border-blue-500 transition-colors duration-200 bg-white"
                  required
                >
                  <option value="" disabled>Select a program</option>
                  <option v-for="prog in programFees" :key="prog.id" :value="prog.id">
                    {{ prog.name }}
                  </option>
                </select>
              </div>
            </div>

            <!-- Submit Button -->
            <div class="pt-6">
              <button
                type="submit"
                class="w-full bg-blue-600 text-white py-4 px-6 rounded-lg font-semibold text-lg hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-offset-2 transition-colors duration-200 shadow-lg hover:shadow-xl"
              >
                Print Challan
              </button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>

  <!-- Print View -->
  <div v-else>
    <ChallanPrint
      :student-name="name"
      :father-name="fatherName"
      :roll-no="rollNo"
      :program="program"
      :challan-no="generateChallanNo()"
    />
    <div class="no-print text-center mt-4">
      <button
        @click="showPrintView = false"
        class="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700"
      >
        Back to Form
      </button>
    </div>
  </div>
</template>

<style scoped>
/* Override any conflicting styles */
.flex {
  display: flex;
}

.flex-col {
  flex-direction: column;
}

.gap-2 {
  gap: 0.5rem;
}

/* Additional label styles */
label {
  font-weight: 600 !important;
  font-size: 1rem !important;
  color: #1f2937 !important;
}

@media print {
  .no-print {
    display: none;
  }
}
</style>
