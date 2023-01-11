<template>
    <input type="text" :value="count"/>
    <input type="button" value="+" @click="inc"/>
    <input type="button" value="-" @click="dec" v-if="count!=0"/>
</template>
<script>
export default {
    data(){
        return {
            count:0
        }
    },
    methods:{
        inc(){
            this.$data.count++
        },
        dec(){
            this.$data.count--
        }
    },
    watch:{
        count:function(newvalue,oldvalue){
            this.$emit("countupdate",newvalue);
        }
    }
}
</script>