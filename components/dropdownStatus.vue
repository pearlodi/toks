<template>
  <div class="status-dropdown">
    <button @click="toggleDropdown">{{ selectedStatus || 'Select Status' }}</button>
    <div v-if="isOpen" class="dropdown-menu">
      <div v-for="status in statuses" :key="status" @click="selectStatus(status)">
        {{ status }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
  props: {
    statuses: Array,
  },
  methods: {
    toggleDropdown() {
      this.isOpen = !this.isOpen;
    },
    selectStatus(status) {
      // Logic to handle the selection of a status
      this.$emit('status-selected', status);
      this.isOpen = false;
    },
  },
};
</script>

<style scoped>
.status-dropdown {
  position: relative;
}

.dropdown-menu {
  position: absolute;
  top: 100%;
  left: 0;
  background-color: #fff;
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 4px;
  z-index: 1000;
}

.dropdown-menu div {
  cursor: pointer;
  padding: 4px;
}

.dropdown-menu div:hover {
  background-color: #f0f0f0;
}
</style>
