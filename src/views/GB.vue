<template>
    <div class="top_el_menu">
        <el-menu
            router
            :default-active="activeIndex" 
            class="el-menu-demo" 
            mode="horizontal"
            :background-color="($store.state.darkMode) ? '#222222' : '#EBEBEB'"
            :text-color="($store.state.darkMode) ? '#E1E1E1' : '#9F9F9F'"
            :active-text-color="($store.state.darkMode) ?'#FFFFFF':'#000000'">
            <el-menu-item index="GB28181">{{$t("message.GB.GB28181")}}</el-menu-item>
            <el-menu-item index="GBPlatform">{{$t("message.GB.GBPlatform")}}</el-menu-item>
            <el-menu-item index="GBService">{{$t("message.GB.GBService")}}</el-menu-item>
        </el-menu>
        <div>
            <router-view></router-view>
        </div>
    </div>
</template>

<script>
export default {
    name:'Avintercom',
    data(){
        return {
            activeIndex:'Advancepb',
        }
    },
    mounted(){
        this.menuList();
    },
    methods:{
        menuList(){ 
			let path = this.$route.meta.title
			// console.log(this.$route)
            this.activeIndex = path
        }
    }
}
</script>

<style lang="scss" scoped>

</style>