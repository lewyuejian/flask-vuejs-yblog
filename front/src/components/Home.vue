<template>
  <div class="container">
    <alert 
      v-for="(alert, index) in alerts" :key="index"
      showAlert
      v-bind:variant="alert.alertVariant"
      v-bind:message="alert.alertMessage">
    </alert>
    <button type="button" class="btn btn-primary">HomePage</button>
  </div>
</template>

<script>
import Alert from './Alert'

export default {
  name: 'Home',  //this is the name of the component
  components: {
    alert: Alert
  },
  data () {
    return {
      alerts: [
        {

          alertVariant: 'danger',
          alertMessage: 0
        },
        {

          alertVariant: 'info',
          alertMessage: 1
        },
        {

          alertVariant: 'dark',
          alertMessage: 2
        }
      ]
    }
  },
  // v-for 与 v-if 不能混用，使用computed计算属性代替v-if(showAlert=true)
  computed: {
    showAlert:function(){
        return true
    }
  }
}
</script>