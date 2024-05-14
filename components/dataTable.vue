<template>
  <div class="table-comp flex justify-between bg-white h-[700px]">
    <query-sidebar />

    <div class="w-[800px] mt-8">
      <input
        type="text"
        v-model="searchQuery"
        placeholder="Search..."
        class="border border-gray-300 rounded-md px-3 py-1 mb-4"
      />
      <table
        class="min-w-full bg-white border border-[#4e4c4c] shadow rounded-lg overflow-hidden"
      >
        <thead class="bg-gray-200 text-gray-700">
          <tr>
            <th class="text-left text-gray-500 pl-6 pr-2 py-2 flex items-center">
              #
              <button @click="sortByColumn('id')">
                <div class="w-3">
                  <img
                    src="../assets/images/sort.png"
                    alt="sort"
                    class="w-full"
                  />
                </div>
              </button>
            </th>
            <th class="text-left text-[#464F60] p-4">NAME</th>
            <th class="text-left text-[#464F60] p-4 w-[230px]">DESCRIPTION</th>
            <th class="text-left text-[#464F60] p-4 flex items-center">
              Status
              <button @click="showStatusPopup = true">
                <div class="w-3">
                  <img
                    src="../assets/images/sort.png"
                    alt="sort"
                    class="w-full"
                  />
                </div>
              </button>
              <div v-if="showStatusPopup" class="fixed">
                <div class="bg-white p-4 rounded-lg flex flex-col items-center">
                  <h2 class="text-md font-bold mb-2">Select Status</h2>
                  <ul>
                    <li
                      v-for="option in statusOptions"
                      :key="option"
                      @click="selectStatus(option)"
                      class="cursor-pointer hover:bg-gray-200 text-sm pb-2 text-center font-normal hover:rounded-sm"
                    >
                      {{ option }}
                    </li>
                  </ul>
                  <button
                    @click="showStatusPopup = false"
                    class="mt-2 bg-gray-300 text-gray-700 py-1 px-2 rounded-lg"
                  >
                    Close
                  </button>
                </div>
              </div>
            </th>
            <th class="text-right text-[#464F60] p-4">RATE</th>
            <th class="text-right text-[#464F60]">BALANCE</th>
            <th class="text-right text-[#464F60] p-4">DEPOSIT</th>
            <th class="text-right text-[#464F60] pr-8 pl-4 px-4"></th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="(row, index) in filteredTableData"
            :key="index"
            :class="{ 'bg-gray-100': index % 2 === 0 }"
          >
            <td class="ml-4 pl-8 pr-2 py-2 font-medium">{{ row.id }}</td>

            <td class="">
              <div>
                <div>
                  <p class="font-medium" v-if="!isEditing(row)">
                    {{ row.name }}
                  </p>
                  <input
                    v-model="row.name"
                    v-else
                    class=" border border-gray-300 "
                  />
                </div>
              </div>
              <div class="mt-1">
                  <p v-if="!isEditing(row)" class="text-[#687182] font-normal text-[12px]" >
                    {{ row.phoneNumber }}
                  </p>
                  <input
                    v-model="row.phoneNumber"
                    v-else
                    class=" border border-gray-300"
                  />
                </div>
            </td>
            <td class="p-2">
              <div >
                  <p  v-if="!isEditing(row)" class="w-[230px] text-[#464F60] textt-[13px] font-normal">
                    {{ row.description }}
                  </p>
                  <input
                    v-model="row.description"
                    v-else
                    class="w-full h-full  border border-gray-300"
                  />
                </div>  
            </td>
            <td class="p-2">
              <span
                class="rounded-2xl px-2 py-[1px] font-medium inline-block bg-[#aea6a653] text-[12px]"
                :class="{
                  'text-[##D12953] bg-[#FAF0F3]': row.status === 'Due',
                  'text-[#14804A] bg-[#E1FCEF]': row.status === 'Paid',
                  'text-[#5A6376] bg-[#E9EDF5]': row.status === 'Inactive',
                  'text-[#4F5AED] bg-[#F0F1FA]': row.status === 'Open',
                }"
              >
                {{ row.status }}
              </span>
            </td>
            <td class="p-2 text-right">
              <p class="text-[#464F60] text-[13px]">{{ formatCurrency(row.rate) }}</p>
              <p class="text-[#687182] text-[11.6px]">CAD</p>
            </td>
            <td class="p-2 text-right">
              <p
                :class="{
                  'text-red-500': row.balance < 0,
                  'text-green-500': row.balance >= 0,
                }"
              >
                {{ formatCurrency(row.balance) }}
              </p>
                <p class="text-[#687182] text-[11.6px]">CAD</p>
            </td>
            <td class="p-2 text-right pr-8 pl-2 px-2">
               <p class="text-[#464F60] text-[13px]">{{ formatCurrency(row.column7) }}</p>
              <p class="text-[#687182] text-[11.6px]">CAD</p>
            </td>
            <td class="flex flex-col">
              <button @click="editRow(row)" v-if="!isEditing(row)" class="py-3 text-[blue] font-medium">
                Edit
              </button>
              <!-- Save button -->
              <button @click="saveChanges(row)" v-else class="text-[green] font-medium">Save</button>
              <button @click="cancelEdit(row)" v-if="isEditing(row)" class="text-[red] font-medium ">
                Cancel
              </button>
            </td>
          </tr>
        </tbody>
      </table>
      <div></div>
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
      showStatusPopup: false,
      selectedStatus: "",
      searchQuery: "",
      tableData: [
        {
          id: 1,
          name: "Ann Culhane",
          phoneNumber: "5684236526",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Open",
          rate: 70.0,
          balance: -270.0,
          column7: 500.0,
        },
        {
          id: 2,
          name: "Ahmad Rosser",
          phoneNumber: "5684236527",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Paid",
          rate: 70.0,
          balance: 270.0,
          column7: 500.0,
        },
        {
          id: 3,
          name: "Zain Calzoni",
          phoneNumber: "5684236528",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Open",
          rate: 70.0,
          balance: -20.0,
          column7: 500.0,
        },
        {
          id: 4,
          name: "Leo Stanton",
          phoneNumber: "5684236529",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Inactive",
          rate: 70.0,
          balance: 600.0,
          column7: 500.0,
        },
        {
          id: 5,
          name: "Kaiya Vetrovs",
          phoneNumber: "5684236530",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Open",
          rate: 70.0,
          balance: -350.0,
          column7: 500.0,
        },
        {
          id: 6,
          name: "Ryan Westervelt",
          phoneNumber: "5684236531",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Paid",
          rate: 70.0,
          balance: -270.0,
          column7: 500.0,
        },
        {
          id: 7,
          name: "Corey Stanton",
          phoneNumber: "5684236532",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Due",
          rate: 70.0,
          balance: 30.0,
          column7: 500.0,
        },
        {
          id: 8,
          name: "Adison Aminoff",
          phoneNumber: "5684236533",
          description:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla...",
          status: "Open",
          rate: 70.0,
          balance: -270.0,
          column7: 500.0,
        },
      ],
    };
  },

  computed: {
    filteredTableData() {
      // Filter the table data based on both status and search query
      return this.tableData.filter((row) => {
        const statusMatch =
          !this.selectedStatus ||
          this.selectedStatus === "All" ||
          row.status === this.selectedStatus;
        const searchMatch =
          !this.searchQuery ||
          Object.values(row).some((value) => {
            if (typeof value === "string") {
              return value
                .toLowerCase()
                .includes(this.searchQuery.toLowerCase());
            }
            return false;
          });
        return statusMatch && searchMatch;
      });
    },

    statusOptions() {
      const statuses = new Set(this.tableData.map((row) => row.status));
      return ["All", ...Array.from(statuses)];
    },
  },
  methods: {
    formatCurrency(value) {
      const formattedValue = Math.abs(value).toFixed(2);
      return `${value < 0 ? "-" : ""}$${formattedValue}`;
    },
    selectStatus(status) {
      this.selectedStatus = status;
      this.showStatusPopup = false;
    },
    sortByColumn(column) {
      this.sortOrder = this.sortOrder === "asc" ? "desc" : "asc";

      this.tableData.sort((a, b) => {
        const aValue =
          typeof a[column] === "string" ? a[column].toLowerCase() : a[column];
        const bValue =
          typeof b[column] === "string" ? b[column].toLowerCase() : b[column];

        if (this.sortOrder === "asc") {
          return aValue < bValue ? -1 : aValue > bValue ? 1 : 0;
        } else {
          return aValue > bValue ? -1 : aValue < bValue ? 1 : 0;
        }
      });
    },
    editRow(row) {
      this.$set(row, "editing", true);
      this.$set(row, "originalData", { ...row });
    },

    saveChanges(row) {
      this.$set(row, "editing", false);
      this.persistData();
    },

    cancelEdit(row) {
      // Cancel the editing process and revert the changes
      // Restore the original data from the copy
      this.$set(row, "name", row.originalData.name);
      this.$set(row, "description", row.originalData.description);
      this.$set(row, "status", row.originalData.status);
      this.$set(row, "rate", row.originalData.rate);
      this.$set(row, "balance", row.originalData.balance);
      this.$set(row, "column7", row.originalData.column7);
      // Exit edit mode
      this.$set(row, "editing", false);
    },

    isEditing(row) {
      return row.editing;
    },
    persistData() {
      localStorage.setItem("tableData", JSON.stringify(this.tableData));
    },
    loadData() {
      const data = localStorage.getItem("tableData");
      if (data) {
        this.tableData = JSON.parse(data);
      }
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
