<template>
    <div> 
        <navbar/>
        <div class="auth-layout p-5 d-flex justify-content-center align-items-center">
            
            <div class="auth-content p-5">
                <h1 class="text-center"> EDIT </h1>
                <div class="form-group mt-2">
                    <label style="font-weight: bold;" for="postTitle">new Name</label>
                    <input class="form-control" id="name" name="name"  >
                </div> 
                <div class="form-group mt-2">
                    <label style="font-weight: bold;" for="postTitle">Job</label>
                    <input class="form-control" id="job" name="job"  >
                </div> 
                <div class="text-center">
                    <button @click="updateUser()" id="btnSubmit" class="btn btn-outline-primary form-control">Save</button>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
import navbar from '../components/navbar'
import axios from 'axios'


    export default{
        name: 'updateUser',
        data(){

            return{
                posts:[],
                

            }
        },
        
        components:{
            navbar
        },
        methods:{
            
            empty(){
                if(document.getElementById('name').value=='' || document.getElementById('job').value==''){
                    return true;
                }
                
            },
            updateUser(){
                if(this.empty()){
                    alert('enter your data');
                }
                else{
                var id = this.$route.params.id;
                var link = 'https://reqres.in/api/users/2/'+id
                axios.put(link, {
                body: JSON.stringify({
                    name: document.getElementById('name').value,
                    job: document.getElementById('job').value
                })
                })
                .then(response => {
                    alert("response.status = " + response.status);
                },
                err =>{
                     console.log(err)
                })
                }
                
            },

            accessPage(){
                if(localStorage.getItem("loginToken") ==null)
                {
                    this.$router.push('../login');
                }
            }
        },
        beforeMount(){
            this.accessPage()
        }

        
    }
</script>

<style>
.auth-content
{
    background-color:whitesmoke;
    width: 40%;
    
    border-radius: 0.5rem;
}
</style>