<template>
  <mt-base :name="name" :items="items" @runEvent="runEvent"></mt-base>
</template>

<script>
import MtBase from "../components/MTBase.vue";
export default {
  components: {
    MtBase
  },
  data() {
    return {
      message: undefined,
      name: "events",
      items: [
        {
          title: "shakeDetected - 监听摇一摇",
          id: "shakeDetected",
          demo:
            "mt.events.shakeDetected()\n.post()\n.then(value => {})\n.catch(error => {});",
          result: ""
        }
      ]
    };
  },
  methods: {
    runEvent(index) {
      const item = this.items[index];
      switch (item.id) {
        case "shakeDetected":
          mt.events
            .shakeDetected(this.message)
            .post()
            .then(value => {
              this.items[index].result = value;
            })
            .catch(error => {
              this.items[index].result = error.message;
            });
          break;
      }
    }
  }
};
</script>

<style scoped>
</style>
