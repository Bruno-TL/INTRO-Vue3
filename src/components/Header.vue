<template>
    <div class="header">
        <h1 :class="{'title':isHome}">Curso Vue 3</h1>
        <p :class="pClass">Lorem ipsum dolor sit amet consectetur, adipisicing elit. Aspernatur voluptas tempora necessitatibus mollitia ratione officiis deleniti similique beatae nemo, laborum quibusdam at totam optio vel ab! Pariatur tenetur illum error?
        </p>
        <p :style="{'color': 'blue'}">
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur amet, harum, excepturi optio corporis tempore alias repellendus sunt a est facere id qui nesciunt autem accusamus expedita earum quo ipsum.
        </p>
        <div 
            v-for="(obj, index) in todo" 
            :key="obj.id"
            class="todos-item"
            >
            <img 
                v-if="obj.imgSrc"
                :src="obj.imgSrc" 
                :alt="obj.altImg">
            {{ index }} = {{ obj.title }}

        </div>
    </div>

</template>

<script>
export default {
    // name: 'App'
    data() {
        return {
            isHome: true,
            pClass: ['title','parag'],
            todo: [
                {
                    "userId": 1,
                    "id": 1,
                    "title": "Recheado de chocolate",
                    "completed": false,
                    "imgSrc": "https://via.placeholder.com/150",
                    "altImg": "img de alguma coisa "
                },
                {
                    "userId": 1,
                    "id": 2,
                    "title": "Coca cola espumante sem gás",
                    "completed": false,
                    "imgSrc": "https://via.placeholder.com/150",
                    "altImg": "img de alguma coisa "
                },
                {
                    "userId": 1,
                    "id": 3,
                    "title": "Bolacha de recheado sem recheo",
                    "completed": false
                },
                {
                    "userId": 1,
                    "id": 4,
                    "title": "Porco assado sem fogo frio",
                    "completed": true
                },
                {
                    "userId": 1,
                    "id": 5,
                    "title": "Desenvolvedor full stack de algum coisa",
                    "completed": false
                }
            ]
        }

    }
}
</script>

<style>
.header {
    border: 1px solid red;
    border-radius: 5px;
}
.todos-item{
    width: 60%;
    margin: 5px auto;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 10px;
    display: flex;
    justify-content:  left;
    align-items: center;
}
.title{
    color: green;
}
.parag {
    font-size: 2em;
}
</style>