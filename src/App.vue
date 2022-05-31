<template>
  <div>
    <p>Создать два счетчика, объявить один через ref, второй через reactive объект с свойством счетчика</p>
    <p>Сверстать 2 кнопки, значение счетчиков вывести в тексты соответствующих кнопок. При нажатии увеличивать на 1 нужный счетчик</p>
    <button @click="changeRef">{{count1}}</button>
    <button @click="changeReactive">{{countObj.count2}}</button>
  </div>
</template>

<script>
import {ref, reactive} from 'vue'
export default {
  setup() {
    const count1 = ref(0);
    const countObj = reactive({
      count2: 0
    })

    const changeRef = () => {
      count1.value++
    }

    const changeReactive = () => {
      countObj.count2++
    }

    return {
      count1, 
      countObj: countObj,
      changeRef,
      changeReactive
    }
  }
}
</script>
