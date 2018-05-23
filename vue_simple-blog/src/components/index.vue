<template>
    <div class="container">
        <form role="form">
            <div class="group-form">
                <label for="username">用户名</label>
                <input type="text" id="username" class="form-control" v-model="iptUsername" placeholder="输入用户名">
            </div>
        
            <div class="group-form">
                <label for="age">年 龄</label>
                <input type="text" id="age" v-model="iptAge" class="form-control">
            </div>
        
       
            <div class="group-form">
                <label for="cont">内 容</label>
                <input type="text" id="cont" v-model="iptCont" class="form-control">
            </div>

            <div class="group-from" style="margin-top:20px;">
                <button class="btn btn-primary" @click="submit">提交</button>
                <button class="btn btn-danger">重置</button>
            </div>
        </form>
        <hr>
        <table class="table text-center table-bordered">
            <caption class="h2">用户信息表</caption>
            <tr>
                <th>序号</th>
                <th>用户名</th>
                <th>年龄</th>
                <th>内容</th>
                <th>其他</th>
            </tr>
            
            <tr v-for="(item,index) in userInfo">
                <th>{{ index }}</th>
                <th>{{ item.name }}</th>
                <th>{{ item.age }}</th>
                <th>{{ item.cont }}</th>
                <th><button class="btn btn-danger btn-sm" @click="deleteList(index)">删除</button></th>
            </tr>
        </table>
    </div>
</template>

<script>
    export default {
        name : 'index',
        data  (){
            return {
                authors:['soybean','xiaobi'],
                change:true,
                iptUsername:'',
                iptAge:'',
                iptCont:'',
                userInfo:[
                    {
                        name:'soy',
                        age:'21',
                        cont:'I am soy'
                    },
                    {
                        name:'xiaobi',
                        age:'21',
                        cont:'I am xiaobi'
                    }
                ]
            }
        },
        methods:{
            submit:function(e){
                //清除默认事件 preventDefault
                e.preventDefault();
                this.userInfo.push({
                    name:this.iptUsername,
                    age:this.iptAge,
                    cont:this.iptCont
                });
                console.log(this.userInfo);
            },
            deleteList:function(index){
                // console.log(index);
                this.userInfo.splice(index,1);
            }
        }
    }
    // jquery生效
    // $(function(){
    //     alert(123);
    // })

</script>

<style scode>
   .group-form{
       margin-top:20px;
   }
</style>
