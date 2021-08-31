<template>
  <div class="head">
    <h3>지금 결제하면 {{ percent }}% 할인</h3>
  </div>
</template>

<script>
export default {
  name: "Discount",
  data() {
    return {
      percent: 20 , 
    }
  },
  mounted() {
    const discount = ()=>{
      this.percent -= 1 ; 
        if (this.percent===0) {
          alert('종료')
          clearInterval(count)
        }
    }
    const count = setInterval(discount,1000)
  }

  

};

</script>

<style>
.head {
  background-color: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>
