<template>
  <footer :style="{backgroundColor: curMenu.bgColor }">
    <div
      v-for=" menu in menuList "
      :key="menu.path"
      @click="switchMenu(menu)"
    >
      <router-link :to="menu.path">{{menu.name}}</router-link>
    </div>
  </footer>
</template>

<script>
import { mapState, mapMutations } from "vuex";
export default {
  computed: {
    ...mapState(["curMenu"]),
  },
  data() {
    return {
      menuList: [
        { path: "/", name: "剧集", bgColor: "#f99999" },
        { path: "/music", name: "音乐", bgColor: "#555555" },
        { path: "/book", name: "书籍", bgColor: "#7700ff" },
        { path: "/chat", name: "聊天", bgColor: "#f07889" },
      ],
    };
  },
  methods: {
    ...mapMutations(["setCurMenu"]),
    switchMenu(menu) {
      this.setCurMenu(menu)
    },
  },
};
</script>

<style lang="scss" scoped>
footer {
  display: flex;
  justify-content: space-around;
  position: fixed;
  bottom: -0.02rem;
  width: 100%;
  height: 1rem;
  line-height: 1rem;
  text-align: center;
  background: rgb(126, 23, 23);
  span {
    position: absolute;
    left: 0;
  }
}
</style>