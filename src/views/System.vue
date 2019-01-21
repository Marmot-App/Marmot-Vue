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
      name: "system",
      items: [
        {
          title: "brightness - 设置屏幕亮度",
          id: "brightness.set",
          level: 0,
          demo:
            "mt.system.brightness(0.5).post()\n.then(value => {})\n.catch(error => {})",
          result: ""
        },
        {
          title: "brightness - 获取屏幕亮度",
          id: "brightness.get",
          demo:
            "mt.system.brightness().post()\n.then(value => {})\n.catch(error => {})",
          result: ""
        },
        {
          title: "volume - 设置系统音量",
          id: "volume.set",
          level: 0,
          demo:
            "mt.system.volume(0.5).post()\n.then(value => {})\n.catch(error => {})",
          result: ""
        },
        {
          title: "volume - 获取系统音量",
          id: "volume.get",
          demo:
            "mt.system.volume().post()\n.then(value => {})\n.catch(error => {})",
          result: ""
        },
        {
          title: "call - 拨打电话",
          id: "call",
          demo: "mt.system.call('10086').post()",
          result: ""
        },
        {
          title: "sms - 发送短信",
          id: "sms",
          demo:
            "mt.system.sms('10086').post()\n.then(value => {})\n.catch(error => {})",
          result: ""
        },
        {
          title: "mailto - 发送邮件",
          id: "mailto",
          demo:
            "mt.system.mailto('is.linhey@outlook.com').post()\n.then(value => {})\n.catch(error => {})",
          result: ""
        },
        {
          title: "facetime - FaceTime",
          id: "facetime",
          demo:
            "mt.system.facetime('is.linhey@outlook.com').post()\n.then(value => {})\n.catch(error => {})",
          result: ""
        }
      ]
    };
  },
  methods: {
    runEvent(index) {
      const item = this.items[index];
      switch (item.id) {
        case "brightness.set":
          mt.system
            .brightness(item.level)
            .post()
            .then(value => {
              this.items[index].result = value;
            })
            .catch(error => {
              this.items[index].result = error.message;
            });
          break;
        case "brightness.get":
          mt.system
            .brightness()
            .post()
            .then(value => {
              this.items[index].result = value;
            })
            .catch(error => {
              this.items[index].result = error.message;
            });
          break;
        case "volume.set":
          mt.system
            .volume(item.level)
            .post()
            .then(value => {
              this.items[index].result = value;
            })
            .catch(error => {
              this.items[index].result = error.message;
            });
          break;
        case "volume.get":
          mt.system
            .volume()
            .post()
            .then(value => {
              this.items[index].result = value;
            })
            .catch(error => {
              this.items[index].result = error.message;
            });
          break;
        case "call":
          mt.system
            .call("10086")
            .post()
            .then(value => {
              this.items[index].result = value;
            })
            .catch(error => {
              this.items[index].result = error.message;
            });
          break;
        case "sms":
          mt.system
            .sms("10086")
            .post()
            .then(value => {
              this.items[index].result = value;
            })
            .catch(error => {
              this.items[index].result = error.message;
            });
          break;
        case "mailto":
          mt.system
            .mailto("is.linhey@outlook.com")
            .post()
            .then(value => {
              this.items[index].result = value;
            })
            .catch(error => {
              this.items[index].result = error.message;
            });
          break;

        case "facetime":
          mt.system
            .facetime("is.linhey@outlook.com")
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
