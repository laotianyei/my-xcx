<template>
  <div>
    <p class="a">
      <button @click="aaa(index)" v-for="(item,index) in listData" :key="index">{{item.title}}</button>
    </p>

    <div :class="{active:index1==index}" v-for="(item,index)in listData" :key="item.id">{{item.content}}
        {{index1}}
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
        index1:1,
      listData: [
        { id: 1, title: "apple", content: "苹果" },
        { id: 2, title: "orange", content: "橘子" },
        { id: 3, title: "lemon", content: "柠檬" }
      ]
    };
  },
  methods: {
    aaa(index) {
   
      this.index1 = index;
    }
  }
};
</script>

<style scoped>
.a {
  display: flex;
}
.a button {
  flex: 1;
}
div div {
  width: 200px;
  height: 200px;
  background: skyblue;
  display: none;
}
div .active {
  display: block;
}
</style>
