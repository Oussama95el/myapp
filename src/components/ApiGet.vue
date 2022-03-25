<template >
    <div class="content">
        <h1>Conssomation Api methode GET</h1>

        <!-- <div class="mb-3">
        <label for="">enter patient id </label>
        <input class="form-control" type="number">
        <button class="btn btn-danger m-2">submit</button>
        </div> -->

        <div class="mb-3">
        <label for="">Enter doctors id </label>
        <input class="form-control" v-model="med" type="number" name="medcin">
        <button class="btn btn-danger m-2" @click="handleMedSubmit" >submit</button>
        </div>

        <!-- <div class="mb-3">
        <label for="">enter visits id </label>
        <input class="form-control" type="number">
        <button class="btn btn-danger m-2">submit</button>
        </div> -->
        
        <div v-if="currentMed" class="display-result">
        <ul>
        <div>
            <li>Medcin ID :
            <pre>{{JSON.stringify(currentMed[0])}}</pre>
            </li>
            <li>First name :
            <pre>{{JSON.stringify(currentMed[1])}}</pre>
            </li>
            <li>Last name :
            <pre>{{JSON.stringify(currentMed[2])}}</pre>
            </li>
            <li>Birthday :
            <pre>{{JSON.stringify(currentMed[3])}}</pre>
            </li>
            <li>Speciality :
            <pre>{{JSON.stringify(currentMed[4])}}</pre>
            </li>
        </div>
        </ul>
        </div>
    </div>
</template>
<script>
export default {
    name: 'ApiGet',
    data(){
        return{
            display: false,
            medcins:[],
            patients:[],
            visits:[],
            med: "",
            currentMed: undefined
        }
    },
    mounted(){
        this.getData();
    },
    methods: {
        getDisplay(){
            this.display = !this.display;
        },
        getData(){
        fetch(`http://localhost/Rahbani_clinic/Api`).then((r) => r.json()).then(data => {
            this.medcins = data;
        })
    
     },
         handleMedSubmit(){  
        if(!this.med) return alert='this ID is not valid';
            const medcin = this.medcins.find(medcin => medcin["0"] === parseInt(this.med, 10))
           this.currentMed = medcin;
        }

        
    },
}
</script>
<style lang="">
    li{
        display: flex;
        align-items: center;
        justify-content: center;
    }
    div{
        display: block;
    }
    .content {
    margin: auto;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
</style>