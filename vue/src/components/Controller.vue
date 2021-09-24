<template>
  <div>
    <div class="controls-box">
      <section>
        <el-row>
          <div v-for="(item,key) in properties" :key="key" style="width: 50px; line-height: 50px; display: flex">
            <div>
              <span class="vertice-span">{{item.name}}</span>
              <el-slider v-model="item.value" :min="item.min" :max="item.max" :step="item.step"></el-slider>
              <span class="vertice-span">{{item.value}}</span>
            </div>
          </div>
        </el-row>
      </section>
    </div>
  </div>
</template>

<script>
export default {
  name: "Controller",
  data () {
    return {
      msg: 'Hello',
      properties: {
        properties1: {
          name: 'X: ',
          value: 1,
          min: 0,
          max: 40,
          step: 1
        },
        properties2: {
          name: 'Y: ',
          value: 1,
          min: 0,
          max: 40,
          step: 1
        },
        properties3: {
          name: 'Z: ',
          value: 2,
          min: 0,
          max: 40,
          step: 1
        },
      },
    }
  }
}
</script>

<style scoped>

</style>