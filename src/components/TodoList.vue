<template>
    <div>
        <div>
            <input type="text" v-model="inputValue" />
            <button @click="addItem">추가하기</button>
        </div>
      <ul>
        <ListItem v-for="{value, index} in listArray" :key="index" :text="value" />
      </ul>
    </div>
</template>
<script>
import ListItem from "./ListItem";

export default {
  data(){
    return{
      inputValue:"",
      listArray:[]
    }
  },
  components:{
    ListItem
  },
  methods: {
    addItem() {
      this.listArray.push(this.inputValue);
      this.inputValue = "";
    }
  }
}
</script>
<style>

</style>