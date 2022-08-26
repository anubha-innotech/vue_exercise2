  <template>
  <slot name="links"></slot>
  <div class="box">
  <div id="center" :class="{ sale: isValid }">
    <h1>{{ title }}</h1>
    <p>{{ content }}</p>
  </div>
</div>
</template>
  
<script>
export default {
  name:'Modal',
  data(){
    return{
      show:true
    }
  },
  props: {
    title: String,
    content: String,
    theme: String,
  },
  created() {
    if (this.theme == 'sale') {
      this.isValid = true
    }
  },
}

</script>

<style>
*{
  margin: 0px;
}
#center {
  width: 100%;
  padding: 45px;
  text-align: center;  
}

#center h1 {
  color: rgb(48, 184, 184);
}

.sale {
  background-color:orangered !important;
  color: white;
}

.sale h1 {
  color: white !important;
}
.box{
  display: flex;
  /* justify-content: center; */
  /* align-items: center; */
}


</style>