<template>
    <div>
        <div class="form-group">
            <label for="username">Username:
                <input type="text" id="username" class="form-control" v-model="user.username">
            </label>
        </div>

        <div class="form-group">
            <label for="email">Email:
                <input type="text" id="email" class="form-control" v-model="user.email">
            </label>
        </div>
        <button class="btn btn-primary" @click="submit" type="submit">Submit</button>
    </div>
</template>

<script>
export default {
    data(){
        return{
            user: {
                username: "username",
                email: "email"
            }
        }
    },
    methods: {
        submit: function(){
            this.$http("https://vueresources-a75b3.firebaseio.com/data.json", this.user)
            .then(response => {
                console.log(response), 
                error => console.log(error)
            })
        }
    }
}
</script>