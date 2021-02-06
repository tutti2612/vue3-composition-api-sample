<template>
  <dl>
    <dd>users</dd>
    <dt>{{ users }}</dt>
    <dd>tasks</dd>
    <dt>{{ tasks }}</dt>
    <dd>sortedUsers</dd>
    <dt>{{ sortedUsers }}</dt>
    <dd>sortedTasks</dd>
    <dt>{{ sortedTasks }}</dt>
  </dl>
</template>

<script lang="ts">
import { computed, defineComponent, reactive } from "vue";

const useUsers = () => {
  const users = reactive([
    { id: 3, name: "suzuki" },
    { id: 1, name: "tsuchiya" },
    { id: 2, name: "tanaka" },
  ]);

  const sortedUsers = computed(() => {
    const copy = [...users];
    return copy.sort((a, b) => a.id - b.id);
  });

  return { users, sortedUsers };
};

const useTasks = () => {
  const tasks = reactive([
    { id: 3, name: "task3" },
    { id: 1, name: "task1" },
    { id: 2, name: "task2" },
  ]);

  const sortedTasks = computed(() => {
    const copy = [...tasks];
    return copy.sort((a, b) => a.id - b.id);
  });

  return { tasks, sortedTasks };
};

export default defineComponent({
  setup() {
    const { users, sortedUsers } = useUsers();
    const { tasks, sortedTasks } = useTasks();
    return { users, tasks, sortedUsers, sortedTasks };
  },
});
</script>