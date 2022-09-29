<template>
<table class="table table:border secondary-5:border">
    <thead>
        <tr>
            <th v-for="th in tableHeader" :key="th">
                <div v-for="th in tableHeader" :key="th" class= "between:flex center:items" >
                    <span>{{ th.text }}</span>
                    <span>
                        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-filter none:event" viewBox="0 0 16 16">
                        <path d="M6 10.5a.5.5 0 0 1 .5-.5h3a.5.5 0 0 1 0 1h-3a.5.5 0 0 1-.5-.5zm-2-3a.5.5 0 0 1 .5-.5h7a.5.5 0 0 1 0 1h-7a.5.5 0 0 1-.5-.5zm-2-3a.5.5 0 0 1 .5-.5h11a.5.5 0 0 1 0 1h-11a.5.5 0 0 1-.5-.5z"/>
                        </svg>
                    </span>
                </div>

            </th>
        </tr>
    </thead>
    <tbody>
     <tr v-for="td in tableData" :key="td">
        <td>{{td.albumid}}</td>
        <td>{{td.id}}</td>
        <td>{{td.title}}</td>
        <td>{{td.office}}</td>
        <td>{{td.extention}}</td>
        <td>{{td.startdate}}</td>
        <td>{{td.salary}}</td>
     </tr>
</tbody>

</table>
    
</template>

<script>
export default {
    name:"TableData",
    props:{
        columns:Array,
        entries:Array
    },
    computed:{
        tableHeader(){
            return this.columns || []
        },
        tableData(){
            return this.entries || []
        }
    }
}
</script>