<template>
    <v-app>
        <SideBar @selectPages=selectPages></SideBar>
        <v-main>
            <chooseClass v-if="pageSelected==0"></chooseClass>
            <delClass v-if="pageSelected==1"></delClass>
            <queryClass v-if="pageSelected==2"></queryClass>
        </v-main>
    </v-app>
</template>

<script>
import SideBar from './components/SideBar.vue';
import chooseClass from './components/chooseClass.vue';
import delClass from './components/delClass.vue';
import queryClass from './components/queryClass.vue';
export default {
    name: 'App',

    components: {
        SideBar,
        chooseClass,
        delClass,
        queryClass
    },

    data() {
        return {
            pageSelected: 0
        };
    },
    methods: {
        selectPages(pageidx) {
            console.log(pageidx)
            this.pageSelected = pageidx
            console.log(this.pageSelected)
        }

    }
}
</script>
<!-- 
<script>
    export default{
        data(){
            return {
                msg:'Hello组件'
            }
        },
        methods:{
            changeMsg(){
               return this.msg+='a'
            }
        },
    }
</script> -->
