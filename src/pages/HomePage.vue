<template>
  <div class=" m-3 align-items-center justify-content-center">
    <div class="row">
      <div class="col-md-4 m-3  d-flex justify-content-center">
        <form>
          <div class="form-group">
            <label for="">Runner 1 pace</label>
            <input type="number" class="form-control" v-model="runner1" aria-describedby="" placeholder="">
            <small id="" class="form-text "></small>
          </div>
          <div class="form-group">
            <label for="">Runner 2 pace</label>
            <input type="number" v-model="runner2" class="form-control" placeholder="">
          </div>
          <div class="form-group">
            <label for="">Runner 3 pace</label>
            <input type="number" v-model="runner3" class="form-control" placeholder="">
          </div>
          <div class="form-group">
            <label for="">Runner 4 pace</label>
            <input type="number" class="form-control" v-model="runner4" aria-describedby="" placeholder="">
            <small id="" class="form-text "></small>
          </div>
          <div class="form-group">
            <label for="">Runner 5 pace</label>
            <input type="number" v-model="runner5" class="form-control" placeholder="">
          </div>
          <div class="form-group">
            <label for="">Runner 6 pace</label>
            <input type="number" v-model="runner6" class="form-control" placeholder="">
          </div>
          <div class="form-group">
            <label for="">Runner 7 pace</label>
            <input type="number" v-model="runner7" class="form-control" placeholder="">
          </div>
          <div class="form-group">
            <label for="">Runner 8 pace</label>
            <input type="number" v-model="runner8" class="form-control" placeholder="">
          </div>



          <button type="submit" class="btn btn-primary m-2" @click="calculateTime()">Submit</button>
        </form>
      </div>
      <div class="col-md-4 m-3 d-flex justify-content-center">
        <h2>It will take this many hours to complete</h2>
      </div>
    </div>

  </div>
</template>

<script>
import { computed, ref } from '@vue/reactivity'
import { AppState } from '../AppState'
export default {
  setup() {
    const runner1 = ref('')
    const runner2 = ref('')
    const runner3 = ref('')
    const runner4 = ref('')
    const runner5 = ref('')
    const runner6 = ref('')
    const runner7 = ref('')
    const runner8 = ref('')
  
    


    return {
      runner1,
      runner2,
      runner3,
      runner4,
      runner5,
      runner6,
      runner7,
      runner8,
      calculateTime() {
      let runners = [runner1.value, runner2.value, runner3.value, runner4.value, runner5.value, runner6.value, runner7.value, runner8.value]
       AppState.runners = runners
        console.log(AppState.runners)
        let totalTime = 0

        for (let i = 0; i < runners.length, i++;) {
         totalTime+= (runners[i]*15.1)
       } console.log(totalTime)
  }

}
  }
,
}
</script>

<style scoped lang="scss">
.home {
  display: grid;
  height: 80vh;
  place-content: center;
  text-align: center;
  user-select: none;

  .home-card {
    width: 50vw;

    >img {
      height: 200px;
      max-width: 200px;
      width: 100%;
      object-fit: contain;
      object-position: center;
    }
  }
}
</style>
