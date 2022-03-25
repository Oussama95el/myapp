<template>
    <div class="content">
        <h1>API methode POST</h1>

        <form @submit.prevent="handleSubmit" class="form m-4" id="form" method="post">
            <h3 class="text-justify">Enter Form Values</h3>
            <div class="row two-in-one-field">
                <div class="col">
                    <input v-model="form.Fname" type="text" class="form-control" placeholder="First name" aria-label="First name">
                </div>
                <div class="col">
                    <input v-model="form.Lname" type="text" class="form-control" placeholder="Last name" aria-label="Last name">
                </div>
            </div>
                <div class="col my-3">
                <input v-model="form.email" type="email" class="form-control" placeholder="Email" aria-label="Email">
                </div>
        
                <div class="col">
                <input v-model="form.password" type="password" class="form-control" placeholder="Password" aria-label="Password">
                </div>

                 <div class="col">
                <input type="submit" class="btn btn-danger m-2" value="submit" >
                </div>
         </form>

            <!-- <div>
                <pre>{{this.data}}</pre>
            </div> -->

    </div>
</template>
<script>
export default {
    name: 'ApiPost',
    data(){
        return{
            data: "",
            form:{

            Fname: "",
            Lname: "",
            email: "",
            password: "",
            }

        }
    },
    methods:{
        handleSubmit(){
           fetch("https://jsonplaceholder.typicode.com/posts",{
               method: "POST",
               body:JSON.stringify(this.form),
               headers:{"content-type":"application/json"}
           }).then(function(response){
               return response.json()
           }).then(function(data){
               console.log(data)
           })
        }

    }
}
</script>
<style lang="">
    
</style>