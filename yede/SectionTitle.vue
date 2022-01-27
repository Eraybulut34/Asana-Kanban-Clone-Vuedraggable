<template>
      <div class="section-title">
            <div class="section-title-text">{{sectionName}}</div>
            <div class="section-right"><PlusCircle/><Trush /></div>
          </div>
</template>

<script>
import PlusCircle from "@/icons/PlusCircle.svg"
import Trush from "@/icons/Trush.svg";
export default {
    components:{
        PlusCircle,
        Trush
    },
    props:{
        sectionName : String,
    }
}
</script>