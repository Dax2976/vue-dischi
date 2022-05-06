<template>
  <div class="filter">
      <select @change="filterByGen()" v-model="selectedValue" name="" id="">
          <option value="">All</option>
          <option value="Rock">Rock 🎸</option>
          <option value="Jazz">Jazz 🎷</option>
          <option value="Metal">Metal 🤟</option>
          <option value="Pop">Pop 🕺</option>
      </select>
  </div>
</template>

<script>
export default {
    name: 'GenderBox',
    data: function(){
        return{
            selectedValue:''
        }
    },
    methods:{
        filterByGen(){
        this.$emit('selectionChange', this.selectedValue)
        }
    }
}
</script>

<style lang="scss" scoped>
    select{
        background-color: #1E2D3B;
        color: white;
        border-color: #1E2D3B;
    }
</style>