<script>
import { mapState } from "pinia";
import { useTestPiniaStore } from "@/store";

export default {
  computed: {
    ...mapState(useTestPiniaStore, ["name"]),
    ...mapState(useTestPiniaStore, ["job"]),
  },
};
</script>

<template>
  <pre>name: {{ job }}</pre>
</template>

<!-- import { createPinia, defineStore } from 'pinia'

export const useTestPiniaStore = defineStore('testStore', {
  state: () => {
    return {
      name: 'bob',
      job: 'programer',
    }
  },
})

const store = createPinia()

export default store -->
