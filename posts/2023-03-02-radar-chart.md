---
title: "chart"
published: true
date: 2023-03-02
---

<script>
 import * as Plot from '@observablehq/plot';
 let ref;
 
 function installPlot(r) {
     if (r) {
     	 console.log('Installing plot');
	 const x = Math.random;
	 const binX = Plot.binX( { y: "count" }, { x } );
	 const rectY = Plot
	       .rectY(
		   { length: 10000 },
		   binX,
	       );
	 console.log('rectY', rectY );
	 const result = rectY.plot();
	 console.log('Result is', result);
	 r.append(result);
     } else {
	 console.log('Ref not ready yet');
     }
 }
 
  $: installPlot(ref);
</script>

<div bind:this={ref}/>
