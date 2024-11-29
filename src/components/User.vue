<template>

<div  class="user">
   <h3>{{ uuuser.name }}</h3>
   <p>{{ uuuser.email }} - <b>{{ uuuser.password }}</b></p>
  </div>
    
</template>

<script> 

export default {
    props: {
        uuuser: {
            type: Object,
            required: true
        }


    }
    
}

</script>


<style>


</style>