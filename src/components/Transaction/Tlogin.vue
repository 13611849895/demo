<template>
    <div>
        <v-header></v-header>
        <div class="main">
            <v-nav></v-nav>
            <h1 class="title">请输入私钥进行操作</h1>
            <input type="text" value="请输入您的私钥" class="inp" v-model="secret">
            <input type="submit" value="确认" class="sub" @click="login">
        </div>
        <v-footer></v-footer>
    </div>
    
</template>

<script>
import VHeader from '../Header'
import VFooter from '../footer'
import VNav from '../vnav'
export default {
    data () {
        return {
            secret: ''
        }
    },
    methods : {
        login () {
            if (this.secret === '' ) {
                alert('请输入私钥')
            } else {
            this.$router.push('/transaction/' + this.secret)
            }
        }
    },
    components: {
        VNav,
        VHeader,
        VFooter
    }
}
</script>   

<style>
   .main {
        margin: 30px;
        background-color: bisque;
        min-width: 960px;
        min-height: 500px;
        text-align: center;
    
    }
    .title {
        margin-top: 25px;
    }
    .tips {
        margin-top: 50px;
        font-weight: 700;
    }
    .inp {
        margin-top: 25px;
        width: 500px;
        height: 30px;
    }
    .chose {
        margin-top: 120px;
        vertical-align: top;
    }
    .sub {
        display: block;
        margin: 30px auto 0;
        border-radius: 3px;
        /* border: none; */
        background: skyblue;
        width: 150px;
        height: 30px;
    }
 
</style>
