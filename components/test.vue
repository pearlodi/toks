<template>
  <div class="flex justify-between bg-white h-[700px]">
    <query-sidebar />

    <div class="w-[800px] mt-8">
       <!-- Add a button to trigger the status selection -->
       <button @click="showStatusPopup = true" class="bg-blue-500 text-white py-2 px-4 rounded-lg mb-4">Select Status</button>

<!-- Status selection popup -->
<div v-if="showStatusPopup" class="fixed top-0 left-0 w-full h-full bg-black bg-opacity-50 flex justify-center items-center">
  <div class="bg-white p-4 rounded-lg shadow-lg">
    <h2 class="text-lg font-semibold mb-2">Select Status</h2>
    <ul>
      <!-- Loop through status options -->
      <li v-for="option in statusOptions" :key="option" @click="selectStatus(option)" class="cursor-pointer py-2 px-4 hover:bg-gray-200">{{ option }}</li>
    </ul>
    <button @click="showStatusPopup = false" class="mt-4 bg-gray-300 text-gray-700 py-2 px-4 rounded-lg">Close</button>
  </div>
</div>

      <!-- Table -->
      <table
        class="min-w-full bg-white border border-[#4e4c4c] shadow rounded-lg overflow-hidden"
      >
        <thead class="bg-gray-200 text-gray-700">
          <tr>
            <th class="text-left text-gray-500 pl-6 pr-2 py-2">ID</th>
            <th class="text-left text-gray-500 p-4">Name</th>
            <th class="text-left text-gray-500 p-4">Description</th>
            <th class="text-left text-gray-500 p-4">Status</th>
            <th class="text-right text-gray-500 p-4">Column 5</th>
            <th class="text-right text-gray-500 p-4">Column 6</th>
            <th class="text-right text-gray-500 pr-6 pl-4 px-4">Column 7</th>
          </tr>
        </thead>
        <tbody>
          <tr
          v-for="(row, index) in filteredTableData"
            :key="index"
            :class="{ 'bg-gray-100': index % 2 === 0 }"
          >
            <td class="ml-4 pl-8 pr-2 py-2">{{ row.id }}</td>
            <td class="p-2">
              <p class="font-medium">{{ row.name }}</p>
              <p>{{ row.phoneNumber }}</p>
            </td>
            <td class="p-2 w-[220px]">{{ row.description }}</td>
            <td class="p-2">
              <span
                class="rounded-2xl px-2 py-[1px] font-medium inline-block bg-[#aea6a653]"
                :class="{
                  'text-red-500': row.status === 'Due',
                  'text-green-600 bg-green-100': row.status === 'Paid',
                  'text-[gray]': row.status === 'Inactive',
                  'text-[blue]': row.status === 'Open',
                }"
              >
                {{ row.status }}
              </span>
            </td>
            <td class="p-2 text-right">
              <p>{{ formatCurrency(row.column5) }}</p>
              <p>CAD</p>
            </td>
            <td class="p-2 text-right">
              <p
                :class="{
                  'text-red-500': row.column6 < 0,
                  'text-green-500': row.column6 >= 0,
                }"
              >
                {{ formatCurrency(row.column6) }}
              </p>
              <p>CAD</p>
            </td>
            <td class="p-2 text-right pr-8 pl-2 px-2">
              <p>{{ formatCurrency(row.column7) }}</p>
              <p>CAD</p>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <setting-sidebar />
  </div>
</template>

<script>
import querySidebar from "./querySidebar.vue";
import QuerySidebar from "./querySidebar.vue";
import SettingSidebar from "./settingSidebar.vue";

export default {
  components: { querySidebar },
  data() {
    return {
      components: {
        SettingSidebar,
        QuerySidebar,
      },
      showStatusPopup: false, // Flag to control the status selection popup
      selectedStatus: "", // Store the selected status
    tableData: [
        {
          id: 1,
          name: "Ann Culhane",
          phoneNumber: "5684236526",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Open",
          column5: 70.0,
          column6: -270.0,
          column7: 500.0,
        },
        {
          id: 2,
          name: "Ahmad Rosser",
          phoneNumber: "5684236527",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Paid",
          column5: 70.0,
          column6: 270.0,
          column7: 500.0,
        },
        {
          id: 3,
          name: "Zain Calzoni",
          phoneNumber: "5684236528",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Open",
          column5: 70.0,
          column6: -20.0,
          column7: 500.0,
        },
        {
          id: 4,
          name: "Leo Stanton",
          phoneNumber: "5684236529",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Inactive",
          column5: 70.0,
          column6: 600.0,
          column7: 500.0,
        },
        {
          id: 5,
          name: "Kaiya Vetrovs",
          phoneNumber: "5684236530",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Open",
          column5: 70.00,
          column6: -350.0,
          column7: 500.0,
        },
        {
          id: 6,
          name: "Ryan Westervelt",
          phoneNumber: "5684236531",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Paid",
          column5: 70.0,
          column6: -270.0,
          column7: 500.0,
        },
        {
          id: 7,
          name: "Corey Stanton",
          phoneNumber: "5684236532",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Due",
          column5: 70.0,
          column6: 30.0,
          column7: 500.0,
        },
        {
          id: 8,
          name: "Adison Aminoff",
          phoneNumber: "5684236533",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Open",
          column5: 70.0,
          column6: -270.0,
          column7: 500.0,
        },
      ],
    };
  },
  computed: {
    filteredTableData() {
      // Filter the table data based on the selected status
      return this.selectedStatus
        ? this.tableData.filter((row) => row.status === this.selectedStatus)
        : this.tableData;
    },
    statusOptions() {
      // Get unique status options for the popup
      const statuses = new Set(this.tableData.map((row) => row.status));
      return Array.from(statuses);
    },
  },
  methods: {
    formatCurrency(value) {
      const formattedValue = Math.abs(value).toFixed(2);
      return `${value < 0 ? "-" : ""}$${formattedValue}`;
    },
    selectStatus(status) {
      // Set the selected status and close the popup
      this.selectedStatus = status;
      this.showStatusPopup = false;
    },
  },
};
</script>

<style scoped>
.table {
  border-radius: 0.5rem;
  border: 5px solid rgb(84, 83, 83);
  font-size: 14px;
}
th {
  font-size: 12px;
  height: 50px;
}
td {
  font-size: 13px;
}
</style>
