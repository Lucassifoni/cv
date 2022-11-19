<template>
    <canvas id="starfield" ref="canvas"></canvas>
</template>

<script setup lang="ts">
import { onMounted, Ref, ref } from 'vue';
const canvas: Ref<HTMLCanvasElement | null> = ref(null);
const ctx: Ref<CanvasRenderingContext2D | null> = ref(null);

let lastFrameTime = performance.now();
const FRAME_TIME = 66;

const draw = () => requestAnimationFrame(() => {
    const now = performance.now();
    if (now < lastFrameTime + FRAME_TIME) return requestAnimationFrame(draw);
    lastFrameTime = now;
    do_draw();
});

let WIDTH = 0;
let HEIGHT = 0;

const d2r = (d: number) => d * Math.PI / 180;

const makeStars = () => {
    const out = [];
    const num = Math.round(Math.random() * 60) + 30;
    for (let i = 0; i < num; i++) {
        let x = Math.random() * WIDTH;
        let h = Math.random() * HEIGHT;
        let mag = 8 - Math.round(Math.random() * 8) + (Math.random() * 4 * h / HEIGHT);
        let tw = Math.random() * 360;
        out.push({
            c: ['#dfe6e9', '#74b9ff', '#fab1a0', '#ffeaa7'][Math.round(Math.random() * 4)],
            x,
            y: h,
            mag,
            tw,
        });
    }
    return out;
};

let stars: { c: string, x: number, y: number, mag: number, tw: number }[] = [];

const a = 0.01;
let total_angle = 0;
let originX = 0;
let originY = 0;
const do_draw = () => {
    if (!ctx.value) return;
    const c = ctx.value;
    const grd = c.createLinearGradient(0, 0, WIDTH, HEIGHT);
    grd.addColorStop(0, 'rgba(2,0,36,1)');
    grd.addColorStop(0.35, 'rgba(79,79,112,1)');
    grd.addColorStop(1, 'rgba(100,145,154,1)');
    c.fillStyle = grd;
    c.fillRect(0, 0, WIDTH, HEIGHT);
    c.setTransform(1, 0, 0, 1, 0, 0);
    c.translate(WIDTH * 0.65, HEIGHT * 0.4);
    c.rotate(d2r(total_angle));
    total_angle += a;
    stars.forEach((star) => {
        c.fillStyle = star.c;
        c.beginPath();
        c.arc(star.x - originX, star.y - originY, Math.abs(1 + (star.mag / 10) - (Math.sin(d2r(total_angle + star.tw)) * 1)), 0, d2r(360));
        c.closePath();
        c.fill();
    });
    c.setTransform(1, 0, 0, 1, 0, 0);
    draw();
};

const setupCanvas = () => {
    const c = canvas.value as HTMLCanvasElement;
    const width = window.innerWidth / 1;
    WIDTH = width;
    const height = window.innerHeight / 1;
    HEIGHT = height;
    originX = WIDTH * 0.65;
    originY = HEIGHT * 0.4;
    c.width = width;
    c.height = height;
    stars = makeStars();
    ctx.value = c.getContext("2d");
};

onMounted(() => {
    const canvasKickingInterval = setInterval(() => {
        if (!canvas.value) return;
        clearInterval(canvasKickingInterval);
        setupCanvas();
        draw();
    }, 100);
});
</script>

<style lang="scss">
#starfield {
    position: fixed;
    left: 0;
    top: 0;
    bottom: 0;
    right: 0;
    width: 100vw;
    height: 100vh;
    z-index: -1;
}
</style>