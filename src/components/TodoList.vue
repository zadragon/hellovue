<template>
    <div>
        <div>
            <input type="text" v-model="inputValue" />
            <button @click="addItem()">추가하기</button>
        </div>
      <ul>
        <ListItem
            v-for="(value, index) in listArray"
            :key="index"
            :index="index"
            :text="value === ''? undefined : value"
            @delete="catchDeleteItem"
        />
      </ul>
    </div>
</template>
<script>
import ListItem from "./ListItem";

export default {
  data() {
    return{
      inputValue: "",
      listArray: []
    };
  },
  components:{
    ListItem
  },
  methods: {
    addItem() {
      this.listArray.push(this.inputValue);
      this.inputValue = "";
    },
    catchDeleteItem(index){
      this.listArray.splice(index, 1)
    }
  }
}
</script>
<style>

</style>