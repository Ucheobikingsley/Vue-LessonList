<template>
  <view class="container">
    <View class="statusBar"></View>
    <Header header="LESSONLIST"/>
    <View class="container-1">
      <View class="input">
        <text-input
          :style="{height: 40, width: 300, borderColor: 'white', borderWidth: 1, borderRadius: 7,paddingLeft: 14}"
          v-model="text"
          placeholder="Type Lesson Here"
          
        />
      </View>
      <View>
        <touchable-opacity  class="add-btn" :on-press="newLesson">
          <!-- <text class="btn-text">ADD</text> -->
          <view class="icon">
            <Ionicons name="cart"  color="white" />
          </view>
          
        </touchable-opacity>
      </View>
    </View>
    <LessonList v-bind:lessons ="lessons" />
  </view>
</template>
<script>
  import LessonList from './components/LessonList'
  import { Ionicons } from '@expo/vector-icons';
  import Header from './components/Header.vue';
    export default {
        data: function() {
            return {
                text: '',
                lessons: [
                  {
                    id:1,
                    title: 'Mathematics',
                    done:'false'
                  },
                   {
                    id:2,
                    title: 'English',
                    done:'false'
                  }
                ]
            };
        },
        components:{
           Ionicons,
           LessonList,
           Header
        },

        methods:{
          newLesson: function (){
           this.lessons.push(
              {
              id:Math.floor(Math.random() * 1000),
              title:this.text,
              done: 'false'
             }
            )
            this.text = ''
          }
        },
        
    }
</script>
<style>
.container {
  background-color: #747a87;
  flex: 1;
}
.text-color-primary {
  color: blue;
}
.statusBar{
  
  height: 30px
}
.input{
  align-items: center;
  justify-content: center;
  margin-top: 20px;
  
}
.container-1{
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.add-btn{
  background-color: #6715B1;
  margin: 10;
  height: 40px;
  width: 60px;
  border-radius: 7;
  text-align: center;
  margin-top: 28;
}

.btn-text{
  padding: 10;
  color: #fff;
}

.todo{
 margin-left: 20px;
 padding:20px;
 margin-top: 5px;
 background-color: #E8E7E9;
 color: #262D2F;
 width: 370px;
}
.icon{
  padding: 12px;
  padding-left: 20px;
}
</style>
