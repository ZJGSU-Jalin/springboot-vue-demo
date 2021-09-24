<template>
  <div>
    <div id="three" style="height: 600px;width: 100%;"></div>
  </div>

</template>

<script>
import * as THREE from 'three'
import {OrbitControls} from 'three/examples/jsm/controls/OrbitControls'
import Controller from "./Controller";
export default {
  name: 'Envir3D',
  data () {
    return {
      msg: 'Hello',
    }
  },
  mounted(){
    this.build_it()
  },
  methods: {
    build_it () {
      const conter = document.getElementById("three")
      let scren = new THREE.Scene() // 场景
      // 灯光
      {
        const color = 0xFFFFFF;
        const intensity = 1;
        const light = new THREE.DirectionalLight(color, intensity);
        light.position.set(1, 1, 2);//x,y,z
        scren.add(light);
      }
      let camera = new THREE.PerspectiveCamera(50, conter.clientWidth / conter.clientHeight, 1, 1000)
      let render = new THREE.WebGL1Renderer()
      render.setClearColor("rgba(0,255,166,0.94)")
      render.setSize(conter.clientWidth, conter.clientHeight)
      conter.appendChild(render.domElement)

      //move
      const controls = new OrbitControls(camera,render.domElement);
      controls.screenSpacePanning = true
      controls.update();

      const loader = new THREE.TextureLoader()

      const geome = new THREE.PlaneBufferGeometry(20,20)
      const mate = new THREE.MeshPhongMaterial({ map: loader.load('https://threejsfundamentals.org/threejs/resources/images/wall.jpg'), side:THREE.DoubleSide})
      let mesh = new THREE.Mesh(geome,mate)
      mesh.rotation.x = -1.57
      mesh.rotation.z = -1.57
      mesh.position.y = -2.3
      scren.add(mesh)

      let geometry = new THREE.BoxGeometry(0.5,0.5,0.5)
      let material = new THREE.MeshPhongMaterial({color:0xffff00})
      let cub = new THREE.Mesh(geometry, material)
      cub.position.z = -2
      cub.position.y = 2

      let geometry2 = new THREE.DodecahedronBufferGeometry (0.5, 1)
      let material5 = new THREE.MeshPhongMaterial({color:0xff0fff })
      let ball = new THREE.Mesh(geometry2, material5)//网格
      let material6 = new THREE.MeshPhongMaterial({color:0x0000ff })
      let ball1 = new THREE.Mesh(geometry2, material6)
      let material7 = new THREE.MeshPhongMaterial({color:0xf0f0f0 })
      let ball2 = new THREE.Mesh(geometry2, material7)
      let material8 = new THREE.MeshPhongMaterial({color:0x0f0f0f })
      let ball3 = new THREE.Mesh(geometry2, material8)


      const geometry3 = new THREE.ConeBufferGeometry(0.3,0.5,50);//圆锥
      let material3 = new THREE.MeshPhongMaterial({color:0xff0f00 })
      let cub3 = new THREE.Mesh(geometry3, material3)//网格

      let geometry4 = new THREE.BoxGeometry(1,1,1)
      const loader4 = new THREE.TextureLoader()
      let material4 = new THREE.MeshPhongMaterial({ color:0xbbbbbb})
      let cub4 = new THREE.Mesh(geometry4, material4)//网格

      cub3.position.x = 1.5
      cub3.position.y = 1
      ball.position.x = -1.5
      ball.position.y = 0.2
      ball1.position.x = 2.3
      ball1.position.y = 1.3
      ball2.position.x = -3.7
      ball2.position.y = 3.1
      ball3.position.x = -4.9
      ball3.position.y = 1.9

      scren.add(cub)
      scren.add(ball)
      scren.add(cub3)
      scren.add(ball1)
      scren.add(ball2)
      scren.add(ball3)
      scren.add(cub4)
      camera.position.z = 8

      function renders(){
        requestAnimationFrame(renders)
        cub.rotation.x+=0.01
        cub.rotation.y+=0.01
        ball.rotation.x-=0.01
        ball.rotation.y-=0.01
        ball1.rotation.x-=0.01
        ball1.rotation.y-=0.01
        ball2.rotation.x-=0.01
        ball2.rotation.y-=0.01
        ball3.rotation.x-=0.01
        ball3.rotation.y-=0.01
        cub3.rotation.x-=0.01
        cub3.rotation.z-=0.01
        cub4.rotation.x-=0.01
        cub4.rotation.z-=0.01
        render.render(scren,camera)
      }

      renders()

    }
  }
}
</script>

<style>
#container {
  position: absolute;
  width: 100%;
  height: 100%;
}
.controls-box {
  position: absolute;
  right: 10px;
  top: 60px;
  width: 180px;
  padding: 10px;
  background-color: #fff;
  border: 1px solid #c3c3c3;
}
.vertice-span {
  line-height: 38px;
  padding: 0 2px 0 10px;
}
</style>