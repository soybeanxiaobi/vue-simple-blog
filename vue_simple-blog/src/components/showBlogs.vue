<template>
    <div id="showBlogs">
        <h2>博客总览</h2>
        <div class="blogList" v-for="blogs in blogs">
            <p>{{ blogs.title }}</p>
            <p>{{ blogs.body }}</p>
        </div>

    </div>
</template>

<script>
    export default {
        data (){
            return {
                blogs:[],
            }
        },
        created (){
            this.$http.get('https://jsonplaceholder.typicode.com/posts')
            .then(function(data){
                // console.log(data)
                this.blogs = data.body.splice(0,10);
                console.log(this.blogs)
            },function(err){
                console.log(err);
            })
        }
    }
</script>

<style scode>
    .blogList{
        padding:15px;
        margin:10px;
        background-color: #ccc;
    }
</style>
