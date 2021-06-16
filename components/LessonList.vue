<template>
    <view>
        <view class="todo" v-for="lesson in lessons" :key="lesson.id">
            <text>{{lesson.title}}</text>
            <Ionicons name="remove-circle-sharp"  color="red" />
        </view>
    </view>
</template>


<script>
 import { Ionicons } from '@expo/vector-icons';
export default {
   
    setup() {
        
    },
    props:['lessons'],
    components:{
        Ionicons
    }
}
</script>

<style>
.todo{
 margin-left: 20px;
 padding:20px;
 margin-top: 5px;
 background-color: #E8E7E9;
 color: #262D2F;
 width: 370px;
 display: flex;
 flex-direction: row;
 justify-content: space-between;
 align-items: center;
}
</style>