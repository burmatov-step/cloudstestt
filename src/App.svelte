<script>

	let canvas;
	let context;
	class Cloud {
		constructor(x, y, src, dx, dy) {
			this.x = x;
			this.y = y;
			this.src = src;
			this.dx = dx;
			this.dy = dy;
			this.img = null
		}

		draw() {
			
			if(!this.img){
				let img
				img = new Image()
				
				img.onload = () =>{
					console.log(img)
					context.drawImage(img, this.x, this.y);
					this.img = img
					this.update();
				} 

				img.src = this.src
			}else{
				context.drawImage(this.img, this.x, this.y);
				this.update();
			}
			
		}

		update() {
			if(this.x > window.innerWidth || this.x < 0){
				this.dx = -this.dx
			}
			if(this.y > 500 || this.y < 0){
				this.dy = -this.dy
			}
			this.x += this.dx;
			this.y += this.dy;
		}
	}

	const x = Math.random() * window.innerWidth;
	const y = Math.random() * 200;
	const dx = (Math.random() - 0.5) * 10;
	const dy = (Math.random() - 0.5) * 10;
	const imgs = './vishnya.png';

	const cloud = new Cloud(x, y,imgs, dx, dy);

	function animate() {
		requestAnimationFrame(animate);
		context.clearRect(0, 0, window.innerWidth, 500);
		cloud.draw()
	}


	$: if (canvas) {
		context = canvas.getContext("2d");
		animate()
	}
</script>

<canvas bind:this={canvas} width={window.innerWidth} height={500} />
<div class="ss">
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	<div class="dd" />
	
	
	
</div>
<style>

canvas{
	position: absolute;
	left: 0;
	top: 0;
	pointer-events: none;
}
	.ss{
		box-sizing: border-box;
		width: 300px;
		height: 300px;
		padding: 5px;
		background-color: #000;
		overflow: scroll;

	}
	.dd{
		width: 100%;
		height: 20px;
		background-color: #fff;
		margin-bottom: 10px;
	}
</style>
