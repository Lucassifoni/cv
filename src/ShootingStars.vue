<template>
    <canvas ref="canvasRef"></canvas>
</template>

<script setup lang="ts">
import { onMounted, Ref, ref } from 'vue';
const canvas: Ref<HTMLCanvasElement | null> = ref(null);
const ctx : Ref<CanvasRenderingContext2D | null> = ref(null);

let lastFrameTime = performance.now();
const FRAME_TIME = 66;

const draw = () => requestAnimationFrame(() => {
    const now = performance.now();
    if (now < lastFrameTime + FRAME_TIME) return requestAnimationFrame(draw); 
    lastFrameTime = now;
});

const setupCanvas = () => {
    const PX_SIZE = 4;
    const c = canvas.value as HTMLCanvasElement;
    const width = window.innerWidth / PX_SIZE;
    const height = window.innerHeight / PX_SIZE;
    c.width = width;
    c.height = height;
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