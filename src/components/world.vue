<template>
    <form  @submit.prevent="newpeople">
        <fieldset>
            <legend>New People</legend>
            名字:<input type="text" v-model="thename"/>
            <br>
            年龄:<input type="text" v-model="theage"/>
            <br>
            <input type="submit" value="添加"/>
        </fieldset>
    </form>
    <select>
        <option v-for="people in peoples" :key="people.id" :value="people.id">
            {{people.id}}:{{people.name}}-{{people.age}}
        </option>
    </select>
    <form @submit.prevent="deletepeople">
        <fieldset>
            <legend>Delete People</legend>
            序号:<input type="text" v-model="theid"/>
            <br>
            <input type="submit" value="删除"/>
        </fieldset>
    </form>
</template>
<script>
export default {
    data(){
        return {
            peoples:[],
            thename:"",
            theage:10,
            theid:0
        }
    },
    methods:{
        newpeople(){
            this.peoples.push({id:this.peoples.length,
            name:this.thename,
            age:this.theage
            })
        },
        deletepeople(){
            this.peoples.splice(this.$data.theid,1)
        }
    }
}
</script>
<style>
select{
    width:5cm
};
</style>