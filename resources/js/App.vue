<template>
    <div>
 hello from vue
    </div>
</template>



<script>

export default {

 data(){
     return{
         posts: [],
         post: {
             id: '',
             title: '',
             content: '',
         }

     }

 },
    mounted() {
        axios
            .get('/api/posts')
            .then(response => {
                this.posts = response.data.data
            })
            .catch(error => {
                console.log(error)
                this.errored = true;
            })
            .finally(() => this.loading = false)
    }

}
</script>

