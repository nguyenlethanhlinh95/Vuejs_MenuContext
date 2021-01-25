<template>
  <div class="hello">
   <VContext ref="menu">
      <ul oncontextmenu="return false;">
         <li @contextmenu="onClickSaveAs($event)"><a href="#">Save as</a></li>
      </ul>
</VContext>
<button @click='openContextMenu'>activate context menu</button>

  </div>
</template>

<script>
import VContext from "./Vcontext";
export default {
  name: "HelloWorld",
  components: {
    VContext
  },
  methods: {
    openContextMenu(e) {
         this.$refs.menu.open(e);
    },
    onClickSaveAs: function(e) {
        e.preventDefault();
        console.log(123);
        this.$refs.menu.close();
     }
  },
};
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}
li {
      display: flex;
    justify-content: center;
    align-items: center;
    padding: .5rem 0;
    width: 11rem;
    border-bottom: 1px solid #d1d1d1;
}
li:hover {
  background: #d1d1d1;
  transition: .3s;
  opacity: .8;
}
a {
  color: #393737;
  text-decoration: none;
  font-size: .8rem;
}
</style>
