<template>
    <div id="all">
        <h1>Rick And Morty</h1>
        <div id="characters">
            <div class="container"  v-for="character in characters.results " :key = "character.id">
                <img :src="character.image" :alt="character.name">
                <div class="info">
                    <a href="">{{character.name}}</a>
                    <span id="status" :class="character.status"></span>
                    <p> Status:</p>
                    <span>{{character.status}}</span>
                    <p>Last known location:</p>
                    <SPan>{{character.location.name}}</SPan>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    namme: "rickAndMorty",
    data() {
        return {
            characters:[]
        }
    },
    methods: {
        callingAPI (){
            fetch("https://rickandmortyapi.com/api/character").then(res => res.json().then((data)=>{
                this.characters = data
            }))
        }
    },
    mounted() {
        this.callingAPI()
    },
}
</script>


<style scoped>

.container {
    display: flex;
    margin: 5% 5% 0% 5%;
    height: auto;
    width: 525px;
    border: black 2px solid;
    border-radius: 20px;
    background-color: #54b534;
}

.container:hover{
    background-color: #41ff01 20px solid;
}

img{
    display: flex;
    height: 250px;
    width: 220;
    border-radius: 20px;
}

.info{
    width: 300px;
    color: white;
    display: block;
    justify-content: center;
    align-items: center;
}

#characters{
    display: flex;
    flex-flow: row wrap;
    width: auto;
    /* border: black 2px solid; */
    justify-content: space-around;
    background-color: transparent;
    margin: 0%;
    padding: 0%;
}

#all{
    background-color: rgb(57, 55, 90);
}

h1{
    color: white;
    background-color: transparent;
}

a{
    font-size: 30px;
}

#status{
    height: 10px;
    width: 10px;
    border-radius: 50%;
    display: inline-block;
}


.Alive{
    background-color: green;
}

.Dead{
    background-color: red;
}
.unknow{
    background-color: white;
}
</style>