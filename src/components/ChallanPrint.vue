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

    <!-- Copy 2 - For Student -->
    <div class="challan-copy">
      <div class="text-center font-bold text-xl mb-4">Allama Iqbal Open University</div>
      <div class="text-center mb-4">Copy No. 2 (For Student)</div>

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

    <!-- Copy 3 - For Bank -->
    <div class="challan-copy">
      <div class="text-center font-bold text-xl mb-4">Allama Iqbal Open University</div>
      <div class="text-center mb-4">Copy No. 3 (For Bank)</div>

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
  </div>
</template>

<style scoped>
.print-area {
  background: white;
  padding: 15px;
  margin: 15px auto;
  max-width: 1200px;
  width: 100%;
  box-sizing: border-box;
}

.challan-copy {
  padding: 10px 20px;
  border: 1px solid #ddd;
  margin-bottom: 10px;
  width: 100%;
  box-sizing: border-box;
}

.text-xl {
  font-size: 1rem !important;
  margin-bottom: 0.25rem !important;
}

.mb-4 {
  margin-bottom: 0.5rem !important;
}

.gap-4 {
  gap: 0.5rem !important;
}

.grid {
  margin-bottom: 0.5rem !important;
}

/* Reduce spacing between copies */
.border-dashed {
  margin: 0.5rem 0 !important;
}

@media print {
  .print-area {
    margin: 0;
    padding: 5px;
    width: 100% !important;
    max-width: none !important;
  }

  .challan-copy {
    padding: 8px 15px;
    border: none;
    border-bottom: 1px dashed #000;
    margin-bottom: 8px;
    page-break-inside: avoid;
  }

  .challan-copy:last-child {
    border-bottom: none;
  }

  .border-dashed {
    display: none;
  }

  @page {
    size: A4 landscape;
    margin: 8mm;
  }
}
</style>
