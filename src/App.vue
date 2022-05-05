<template>
  <div>
    <pre v-if="todo">{{ todo }}</pre>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todo: false,
    };
  },
  async created() {
    try {
      const response = await this.axios(
        "https://jsonplaceholder.typicode.com/todos/1"
      );

      console.log(response);
      this.todo = response.data;
    } catch (error) {
      console.error("error >>", error);
    }
  },
};
</script>
