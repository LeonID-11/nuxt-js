<template>
    <section class="container">
        <h1>{{title}}</h1>

        <ul>
            <li v-for=" user of users" :key="user.id">
                <a href="#" @click.prevent="openUser(user)">
                    {{user.name}}
                </a>
            </li>
        </ul>
    </section>
</template>

<script>
export default {
    middleware: ['auth'],
    async fetch({store}){
        if(store.getters['users/users'].length === 0){
            await store.dispatch('users/fetch');
        }
    },
    data: ()=>({
        title: "Page users"
    }),
    computed: {
        users(){
            return this.$store.getters['users/users'];
        }
    },
    methods:{
        openUser(user){
            this.$router.push('/users/'+ user.id);
        }
    }
}
</script>
