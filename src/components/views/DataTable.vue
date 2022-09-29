<template>
<TableData :columns="columns" :entries="entries"/>
</template>

<script>
import TableData from '../components/table/TableData.vue'
export default{
    name:'DataTable',
    data() {
        return{
            columns:[
                {album: 'albumid',text: 'Name'},
                {id: 'name',text: 'id'},
                {title: 'position',text: 'Title'},
                {name: 'office',text: 'Office'},
                {name: 'extension',text: 'Extension'},
                {name: 'salary',text: 'Salary'}
            ],
            entries:[]
        }
    },
    components:{
        TableData
    },
    created(){
        this.getAllInfo().then(res =>{
            this.entries=res.data
        }
        )

    },
    methods:{
        async getAllInfo(){
            const response =await fetch('https://jsonplaceholder.typicode.com/photos/')
            return response.json()
        }
    }
}
</script>