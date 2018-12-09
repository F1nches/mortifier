<template>
  <div class="canvas-wrapper">

    <div id="canvas-wrapper-inner">
      <canvas id="c"></canvas>
    </div>

    <div class="save-image">save image</div>

    <svg version="1.1" id="Morty" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
	 viewBox="0 0 100 250" style="enable-background:new 0 0 100 250;" xml:space="preserve" :style="{'stroke': strokeColor, 'stroke-width': strokeWidth, 'stroke-linecap': strokeLineCap, 'stroke-linejoin': strokeLineJoin, 'stroke-miterlimit': strokeMiterLimit}">
      <path id="Arm2" :style="{'fill': armColor, 'stroke': strokeColor}" class="st0" d="M70.3,104l-0.4,37.8c0,0,1.6,7.3,1.3,9l-1.7-2.4c0,0,0.9,7,0,8c-0.9,1-1.6-4.9-1.6-4.9s-0.4,8-1.8,8
      	s-0.5-9.9-0.5-9.9l-0.3-45.4"/>
      <g id="FeetGroup" :style="{'fill': feetColor}">
      	<path class="st1" d="M63.1,211.1v2.9l11.9,7.9c0,0,1.3,6.1-17.3,0c0,0-1.9-2.4,0-6.8l0.3-4"/>
      	<path class="st1" d="M45.2,213.9v2.5c0,0-6.5,10.5,1.7,11.6c8.2,1,3.7-11.3,3.7-11.3l-0.7-2.7"/>
      </g>
      <path id="Pants" :style="{'fill': pantsColor}" class="st2" d="M67.3,142.9l-2.1,67.3c0,0-4.8,2.8-8.5,0.6l-1.9-61.4c0,0-1,0.6-1.9,0.1l-1.7,63.7
      	c0,0-5.4,1.6-7.8,0l-3.9-71L67.3,142.9z"/>
      <g id="ShirtGroup" :style="{'fill': shirtColor}">
      	<path class="st3" d="M44,89.7l-0.7,16.2c-5.6,2.2-9.3,0-9.3,0c0-20.5,6.9-31.1,6.9-31.1h24c0,0,6.3,8.1,6.3,29c0,0-2,0.9-4.6,0.6
      		c0,0,1.6,20.9,1.7,38.4c0,0-7.7,1.6-11.6,0.6c-1.7-0.5-2.9-0.4-3.8-0.3c-2.1,0.4-4.3,0.6-6.5,0.4c-2.8-0.2-6.2-0.7-8.4-1.8
      		l1.3-34.4"/>
      	<path class="st3" d="M43.3,105.8c0,0-4.7,1.9-9.3,0"/>
      	<polyline class="st4" points="66.6,104.4 65.5,90 66.6,104.4 	"/>
      </g>
      <path id="Arm" :style="{'fill': armColor}" class="st0" d="M35.1,106.3L36,143c0,0-1.8,9-0.9,11.7l0.9-3.6c0,0-0.7,7,1.3,7.6l0.7-7.3c0,0,0.4,7.6,1.2,8.2l1-8.2
      	c0,0,0.3,7.3,1.2,8.2c0,0,1-7.9,1-9.8l1.4,1.9c0,0,1.7-3-3.2-8.7l0.4-36.7"/>
      <path id="Hair" :style="{'fill': hairColor}" class="st5" d="M65.4,35.3c0,0,1.5-5-4.3-8.6s-13.3-4.3-13.3-4.3S40,23.1,37,25.8c-1.6,1.5-3.8,2.7-5.4,3.5
      	c-1.6,0.8-2.9,2-3.8,3.5L24,38.9c-0.8,1.3-1.3,2.8-1.4,4.4c-0.2,2.7-0.4,6.8,0.2,8.8c0.3,1.1,0.4,2.3,0.3,3.4c-0.2,2.5,0.5,5,2.1,7
      	l1.6,2l4,4.2L65.4,35.3z"/>
      <g id="FaceSkinGroup" :style="{'fill': skinColor}">
      	<circle class="st0" cx="52.9" cy="55.1" r="23"/>
      	<path class="st0" d="M61.5,58c0,0,2.7,2.1,4.6,0c1.9-2.1-2.3-4-2.3-4"/>
      	<path class="st0" d="M70.5,64.9c0,0-9-1.3-13.8,2.7"/>
      	<path class="st0" d="M33.3,62c0,0-3.9,3-2.5,6.8c1.3,3.9,6.5,1.3,6.5,1.3"/>
      </g>
      <g id="EyesGroup" :style="{'fill': eyeColor}">
      	<circle class="st6" cx="50.5" cy="49.9" r="8"/>
      	<circle class="st6" cx="69.5" cy="47.1" r="8"/>
      	<g>
      		<line class="st4" x1="51.8" y1="47.4" x2="52.9" y2="48.8"/>
      		<line class="st4" x1="53" y1="47.9" x2="51.7" y2="48.7"/>
      		<line class="st4" x1="51.7" y1="48" x2="52.6" y2="48.1"/>
      	</g>
      	<g>
      		<line class="st4" x1="70.8" y1="44.2" x2="72.6" y2="44.6"/>
      		<line class="st4" x1="72.1" y1="43.8" x2="71.6" y2="45.3"/>
      		<line class="st4" x1="71.2" y1="44.7" x2="71.9" y2="44.3"/>
      	</g>
      </g>
    </svg>

  </div>
</template>

<script>
import { fabric } from 'fabric'

export default {
  name: 'Canvas',
  data () {
    return {
      portal: require('@/assets/portal2.png'),
      skinColor: '#E8C39D',
      armColor: '#E8C39D',
      eyeColor: '#27ae60',
      hairColor: '#e74c3c',
      shirtColor: '#E8E869',
      pantsColor: '#2E3E64',
      feetColor: '#E8E8E8',
      strokeColor: '#231F20',
      strokeWidth: '0.75',
      strokeLineCap: 'round',
      strokeLineJoin: 'round',
      strokeMiterLimit: '10'
    }
  },
  mounted: function() {

    var svgEl = document.body.getElementsByTagName('svg')[0];
    var serializer = new XMLSerializer();
    var svgStr = serializer.serializeToString(svgEl);

    var canvas = new fabric.Canvas('c');

    canvas.backgroundColor = 'rgb(21,21,26)';

    window.addEventListener('resize', resizeCanvas, false);

    function resizeCanvas() {

      canvas.clear();

      var height = document.getElementById('canvas-wrapper-inner').offsetHeight;
      var width = document.getElementById('canvas-wrapper-inner').offsetWidth;

      canvas.setHeight(height);
      canvas.setWidth(width);

      canvas.renderAll();

      var path = fabric.loadSVGFromString(svgStr,function(objects, options) {
        var obj = fabric.util.groupSVGElements(objects, options);
        obj.scaleToHeight(canvas.height-10).set({ left: canvas.width/4, top: canvas.height/12 }).setCoords();

        canvas.add(obj).renderAll();
      });

    }

    // size on init
    resizeCanvas();

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .canvas-wrapper {
    width: 600px;
    height: 600px;
    margin: 0 auto;
  }
  #canvas-wrapper-inner {
    height: 100%;
    width: 100%;
    background: none;
  }
  #Morty {
    display: none;
  }
</style>
