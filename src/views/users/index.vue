<template>
    <div class="user-container">
        <div class="user-info">
            <img src="../../assets/images/3.jpg" alt="">
            <div class="meta">
                <h4 class="name">xa</h4>
                <span>
                    文明驾驶分
                    <strong>0</strong>
                </span>
            </div>
        </div>
        <ul class="group-links">
            <router-link to="/my" tag="a" class="arrow">
                <i class="icon icon-user-link-1"></i>
                我的帐户
            </router-link>
             <router-link to="/order" tag="a" class="arrow">
                <i class="icon icon-user-link-2"></i>
                租车订单
            </router-link>
             <router-link to="/authentication" tag="a" class="arrow">
                <i class="icon icon-user-link-3"></i>
                实名认证
            </router-link>
             <router-link to="/safe" tag="a" class="arrow">
                <i class="icon icon-user-link-4"></i>
                安全设置
            </router-link>
             <router-link to="aa" tag="a" class="arrow">
                <i class="icon icon-user-link-5"></i>
                帮助中心
            </router-link>
        </ul>
        <button class="logout" @click="logout">登出</button>
    </div>
</template>
<script>
// cookies
import { removeToken, removeUsername } from "@/utils/cookiesCars";
export default {
    name: "User",
    components: {},
    data(){
        return {
            // usename: this.$store.state.account.username
        }
    },
    methods: {
        logout(){
            this.$store.dispatch("account/logoutAction").then(() => {
                this.$router.replace({
                    name: "Index"
                })
            })
           
        }
    }
    
}
</script>
<style lang="scss">
@import "./index.scss";
.logout {
    position: absolute;
    left: 50%;
    bottom: 60px;
    width: 165px;
    height: 58px;
    margin-left: -82px;
    background-color: #2d3339;
    border-radius: 100px;
    text-align: center;
    line-height: 58px;
    color: #fff;
    font-size: 18px;
    border: none;
    outline: none;
}
</style>