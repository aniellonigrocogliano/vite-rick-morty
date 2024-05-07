<script>
import { store } from "../store";
export default {
  data() {
    return {
      store,
      status: ["All", "Alive", "Dead", "Unknown"],
    };
  },
};
</script>

<template>
  <div class="container py-4">
    <div class="d-flex justify-content-between">
      <div>
        <select @change="$emit('filter')" v-model="store.selectedStatus">
          <option :value="status" v-for="status in status">
            {{ status }}
          </option>
        </select>
      </div>

      <!-- <p>Ci sono {{ store.cardsList.length }} personaggi mostrati</p> -->
    </div>
  </div>
</template>