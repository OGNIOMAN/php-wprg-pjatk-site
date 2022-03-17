<template>
  <div>
        <v-col
          cols="12"
          sm="6"
        >
        <v-form>
          <v-text-field v-for="(input, index) in inputs" :key="index"
            v-model="inputParams.values[index]"
            :label="input.placeholder"
            outlined
          ></v-text-field>
        </v-form>
        <v-btn @click="test" color="" rounded outlined >
            testuj!
        </v-btn>
        </v-col>
  </div>
</template>

<script>
import axios from "axios";
export default {
    data: () => ({
        inputParams: {
            values:[]
        },
        dummyData: 'PROSZE DZIALAJ KROPKA JOTPEGIE'
    }),
    props:{
        inputs: {
            type: Array
        }
    },
    methods:{
        test(){
            // this.inputParams.values.forEach(element => {
            //     console.log(element)
            // })
            // console.log(this.inputParams.values)
                axios.post("http://localhost/file.php", this.inputParams.values).then(response => {
                    console.log(response.data)
                }).catch(error => {
                    console.log(error)
                })
        }
    }
}
</script>

<style>

</style>