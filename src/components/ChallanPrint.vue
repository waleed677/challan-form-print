<script setup lang="ts">
defineProps<{
  studentName: string
  fatherName: string
  rollNo: string
  program: string
  challanNo: string
}>()

// Dummy static data
const staticData = {
  abl: '0010000336340801',
  fwbl: '0036010745610001',
  mcb: '0586704541007031',
  ubl: 'MCA A/C 262489296',
  nbp: 'NBP (Cash Management System)',
  issueDate: '01/03/2025',
  validityDate: '16/03/2025',
  fee: 6750,
  bankOptions: 'EasyPaisa Upaisa Bank Jazz Cash',
}
</script>

<template>
  <div class="print-area">
    <!-- Copy 1 - For AIOU -->
    <div class="challan-copy">
      <div class="text-center font-bold text-xl mb-4">Allama Iqbal Open University</div>
      <div class="text-center mb-4">Copy No. 1 (For AIOU)</div>

      <div class="grid grid-cols-2 gap-4 mb-4">
        <div>
          <div>ABL: {{ staticData.abl }}</div>
          <div>FWBL: {{ staticData.fwbl }}</div>
          <div>MCB: {{ staticData.mcb }}</div>
        </div>
        <div class="text-right">
          <div>UBL: {{ staticData.ubl }}</div>
          <div>{{ staticData.nbp }}</div>
        </div>
      </div>

      <div class="grid grid-cols-2 gap-4 mb-4">
        <div>
          <div>Challan#: {{ challanNo }}</div>
          <div>Student Name: {{ studentName }}</div>
          <div>Father Name: {{ fatherName }}</div>
          <div>Program/Description: {{ program }}</div>
        </div>
        <div>
          <div>Issue Date: {{ staticData.issueDate }}</div>
          <div>Roll No: {{ rollNo }}</div>
          <div>Validity Date: {{ staticData.validityDate }}</div>
          <div>Fee Payable: Rs. {{ staticData.fee }}/-</div>
        </div>
      </div>

      <div class="grid grid-cols-2 gap-4 mb-4">
        <div>Amount (in words): _____________</div>
        <div>Contact No: _____________</div>
      </div>

      <div class="mb-4">
        <div>Transaction ID: _____________</div>
        <div class="text-sm">{{ staticData.bankOptions }}</div>
      </div>

      <div class="grid grid-cols-2 gap-4">
        <div>Depositor Name/Sign/Cell#: _____________</div>
        <div class="text-right">Bank official sign: _____________</div>
      </div>
    </div>

    <!-- Dotted line separator -->
    <div class="border-dashed border-t-2 border-black my-8"></div>

    <!-- Copy 2 - For Student (Same structure as Copy 1) -->
    <div class="challan-copy">
      <!-- Same structure as above with "Copy No. 2 (For Student)" -->
      <div class="text-center font-bold text-xl mb-4">Allama Iqbal Open University</div>
      <div class="text-center mb-4">Copy No. 2 (For Student)</div>
      <!-- Rest of the content same as Copy 1 -->
      <!-- ... -->
    </div>

    <!-- Dotted line separator -->
    <div class="border-dashed border-t-2 border-black my-8"></div>

    <!-- Copy 3 - For Bank (Same structure as Copy 1) -->
    <div class="challan-copy">
      <!-- Same structure as above with "Copy No. 3 (For Bank)" -->
      <div class="text-center font-bold text-xl mb-4">Allama Iqbal Open University</div>
      <div class="text-center mb-4">Copy No. 3 (For Bank)</div>
      <!-- Rest of the content same as Copy 1 -->
      <!-- ... -->
    </div>
  </div>
</template>

<style scoped>
.print-area {
  background: white;
  padding: 20px;
  margin: 20px auto;
  max-width: 800px;
}

.challan-copy {
  padding: 20px;
  border: 1px solid #ddd;
  margin-bottom: 20px;
}

@media print {
  .print-area {
    margin: 0;
    padding: 0;
  }

  .challan-copy {
    page-break-inside: avoid;
  }
}
</style>
