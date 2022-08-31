<template>
  <div>
    <input type="text" placeholder="cerca" v-model="imputText">
            <button @click="$emit('search,imputText')">Search</button> <!--emit in app?-->
  </div>
</template>

<script>
    
export default {
name:"MyHeader",
data(){
    return{
        imputText:''
    }
}
}


</script>

<style>

</style>