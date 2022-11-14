<template>
    <div>
        <h1>"My name"</h1>
        <input type="text" v-model="input">
        <ul>
            <li v-for="(name) in filteredNames" v-bind:key = "name">
                {{index}} {{name}}
            </li>
        </ul>
    </div>
</template>

<script>

export default{
    name :"userName",
    data(){
        return{
            names: [
                'Parth',
                'Eduard',
                'Frank',
                'Edger',
                'Max',
                'Chencho',
                'Demian',
                'Alexis',
                'Tali',
                'Luz',
                'Juan'
            ],
            input:''
        }
    },
    computed: {
        filteredNames() {
            return this.input !== '' ? this.names.filter(name => name.toLowerCase().includes(this.input.toLowerCase())) : ''
        },
    }
}
</script>

<style scoped>
template{
    display: flex;
}

div{
    width: 99%;
    height: 500px;
    background-color: rgb(180, 180, 180);
    margin: 0%;
    border: 5px solid black;

}

h1{
    width: 100%;
    text-align: center;
    font-size: 70px;
    background-color: rgb(73, 187, 73);
    margin-top: 0;
}

input{
    width: 50%;
    height: 50px;
    border: 3px solid rgb(38, 114, 158);
    font-size: 40px;
    text-align: center;
    outline: 5px solid white;
    border-radius: 2px;
}

ul li{
    font-size: 35px;
    height: 40px;
    width: 35%;
    background-color: rgb(73, 187, 73);
    margin: 0 auto;
    /* align-items: center; */
}
</style>