<template>
    <h1>hi</h1>
    <div>
        <div  v-for="(item, index) in timeArray" :key="index" class="timeDiv">
            <div class="timeList">{{item}}</div><div class="itemDiv" :class="test2"  ></div><div class="itemDiv"></div>
        </div>
    </div>
    <button v-on:click="test">클릭{{data}}</button>

<!--         
    <draggable v-model="myList">
        <div v-for="item in myList" :key="item.no">
            {{ item.name }}
        </div>
    </draggable> -->


</template>

<script>
import draggable from 'vuedraggable'


export default ({
    setup() {
        const test = () => {
            data = "hi";
        }
        const test2 = () => {
            console.log('test');
        }
        return{
            test, test2
        }
    },   
    components: {
        draggable,
    },

  
    data () {
        return {
        data: "Data", // [데이터 정의]
        timeArray:[ // [데이터 정의]
            // "0 ~ 1",
            // "1 ~ 2",
            // "2 ~ 3",
            // "3 ~ 4",
            // "4 ~ 5",
            // "5 ~ 6",
            // "6 ~ 7",
            // "7 ~ 8",
            // "8 ~ 9",
            // "10 ~ 11",
            // "11 ~ 12",
            // "12 ~ 13",
            // "13 ~ 14",
            // "14 ~ 15",
            // "15 ~ 16",
            // "16 ~ 17",
            // "17 ~ 18",
            // "18 ~ 19",
            // "19 ~ 20",
            // "20 ~ 21",
            // "21 ~ 22",
            // "22 ~ 23",
            // "23 ~ 24",
            "0","1","2","3","4","5","6","7","8","9","10","11","12","13","14","15","16","17","18","19","20","21","22","23","24"
            ], 

        json:[ // [데이터 정의]
            {name:"홍길동", age:15},
            {name:"임꺾정", age:18}
        ],
        }    
    },
    
   

})
var timeArray = ["0","1","2","3","4","5","6","7","8","9","10","11","12","13","14","15","16","17","18","19","20","21","22","23","24"]
for(var i = 0; i<timeArray.length; i++){
    console.log(timeArray[i]);
}
</script>
<style scoped>
.timeDiv {
    border: 1px solid black;
    height: 20px;
    width: 40%;
}
.timeList{
    border: 1px solid black;
    float:left;

    height: 100%;
    width: 40%;
}
.itemDiv{
    border: 1px solid black;
    float:left;
    height: 100%;
    width: 20%;

}
</style>