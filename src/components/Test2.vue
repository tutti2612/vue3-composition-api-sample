<template>
  <p>{{ user }}</p>
  <p>{{ fullName }}</p>
</template>

<script lang="ts">
import { computed, defineComponent } from "vue";

const useUser = () => {
  const user = {
    id: 1,
    firstName: "Kohei",
    lastName: "Tsuchiya",
  };

  const fullName = computed(() => {
    return user.firstName + " " + user.lastName;
  });

  return { user, fullName };
};

export default defineComponent({
  setup() {
    const { user, fullName } = useUser();
    return { user, fullName };
  },
});
</script>