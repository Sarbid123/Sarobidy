<template>
    <header>
        <h1>{{title}}</h1>
        <hr>
    </header>
    <main>
        <div class="wrapper">
            <div class="card" v-for="user in users">
                <div class="profil">
                    <img :src="user.photo" :alt="user.name">
                </div>
                <div class="container">
                    <h3>{{user.name}}</h3>
                    <p>{{user.age}} ans</p>
                    <button @click="handClick(user)" v-if="!user.showBio">Click pour mieux en savoir</button>
                    <button @click="handClick(user)" v-else>Cacher</button>
                    <p v-show="user.showBio">{{user.bio}}</p>
                </div>
            </div>
        </div>
    </main>
</template>

<script>
    //import Components from 'src/components/Components';
    export default{
        data(){
            return{
                title: "Notre test",
                users: [
                    {
                        name: "Sylvano",
                        age: 25,
                        bio: "Informaticien Expert",
                        showBio: false, 
                        photo: "src/assets/1.png"
                    }, 
                    {
                        name: "Saif",
                        age: 24,
                        bio: "FullStack",
                        showBio: false,
                        photo: "src/assets/2.png"
                    }
                ]
            }
        },
        methods:{
            handClick(user){
                user.showBio = !user.showBio
            }
        }
    }
</script>

<style>
    *{
        text-align: center;
    }
    .card{
        margin: 10px 0 10px 0;
        background-color: aquamarine;
    }
</style>