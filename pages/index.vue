<template>
  <div>

    <div>
      <myBtn warning disable :click="openModal" text='Moya Knopka'></myBtn>
      <myBtn info :click="openModal" text='Moya Knopka'></myBtn>
      <myBtn danger loading :click="openModal" text='Moya Knopka'></myBtn>
      <myBtn success :click="openModal" text='Moya Knopka'></myBtn>
      <myBtn disable :click="openModal" text='Moya Knopka'></myBtn>
      <my-btn success>
        <div slot='content'>
          <p>cont</p>
          <strong>in slot</strong>
          <input type="button" @click="togleBtnModal()">
          <modal ref="my_modal_btn" title="Privet" content="контент">
            <template slot="title">
                Modalka in btn
            </template> 
            <div slot="content">
              <h1 style="color: black;">content before buttons</h1>
              <myBtn info :click="openModal" text='Moya Knopka'></myBtn>
              <myBtn danger loading :click="openModal" text='Moya Knopka'></myBtn>
            </div>
            <div slot='buttonCont'><my-btn warning disable loading :click='openModal'></my-btn></div>
            <div slot='footer'>
              <myBtn success :click="saveChanges" text='Save all'></myBtn>
              <myBtn danger :click="togleBtnModal" text='Discard'></myBtn>
              <myBtn :click="exitBtnModal" text='Exit'></myBtn>
            </div>
          </modal>
        </div>
      </my-btn>
    </div>

    <p style="margin: 2em;"></p>
    <modal ref="my_modal" title="Privet" content="контент">
        <template slot="title">
            Modalka 
        </template> 
        <div slot="content">
          <p>It's</p>
          <p>a new</p>
          <h1>Plashka</h1>
        </div>
        <div slot='buttonCont'><my-btn danger :click='togleBtnModal'></my-btn></div>
    </modal>
    
    <div>
      <tabs type='is-centered is-boxed '>
        <tab name='о нас' >
           о нас
           <code>&lt;div&gt;</code> 
        </tab>
        <tab name='Сапёр'>
          сапёр
        </tab>
        <tab name='Прогресс' selected class='forTab'>
          <progress-bar type='is-danger' :value="count" progressWidth='600px' progressHeight='600px'></progress-bar> 
          <progress-bar type='is-warning' :value="count2" progressWidth='14%' progressHeight='600px'></progress-bar> 
          <progress-bar type='is-success' :value="count" progressWidth='3%' progressHeight='900px'></progress-bar> 
          <progress-bar type='is-info' :value="count2" progressWidth='200px' progressHeight='50px'></progress-bar> 
          <p style="width: 100px;"></p>
        </tab>
      </tabs>
    </div>

  </div>
</template>

<script>
import Modal from '@/components/modal.vue'
import myBtn from '@/components/baton.vue'
import tabs from '@/components/tabs.vue'
import tab from '@/components/tab.vue'
import progressBar from '@/components/progressBar.vue'

export default {
  components: {
    Modal, myBtn, tabs, tab, progressBar,
  },
  methods:{
    openModal(){
      this.$refs.my_modal.show()
    },
    togleBtnModal(){
      this.$refs.my_modal_btn.togle()
    },
    exitBtnModal(){
      this.$refs.my_modal_btn.hide()
    },
    saveChanges(){
      this.$refs.my_modal_btn.saveChanges()
    },
  },
  data(){
    return{count: 0, flag: true, flag2: false, count2: 50}
  },
  mounted(){
    setInterval(()=>{
      if (this.flag && this.count == 100){this.flag = false}
      else if (!this.flag && this.count == 0){this.flag = true}

      if(this.flag){this.count += 10}
      else{this.count -= 10}


      /*if (this.flag2 && this.count2 == 100){this.flag2 = false}
      else if (!this.flag2 && this.count2 == 0){this.flag2 = true}

      if(this.flag2){this.count2 += 10}
      else{this.count2 -= 10}*/
    }, 1000)

    setInterval(()=>{
      if (this.flag2 && this.count2 == 100){this.flag2 = false}
      else if (!this.flag2 && this.count2 == 0){this.flag2 = true}

      if(this.flag2){this.count2 += 10}
      else{this.count2 -= 10}
    }, 100)
  }
}
</script>

<style lang="scss"> 
  body {
    background-color: white;
  }
  .forTab{
    display: flex;
    justify-content: space-between;
  }
</style>


