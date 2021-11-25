<template>
    <div class="d-flex flex-column align-items-center align-self-sm-center">
        <svg xmlns="http://www.w3.org/2000/svg" fill="currentColor" class="bi bi-vinyl-fill" viewBox="0 0 16 16">
            <path d="M8 6a2 2 0 1 0 0 4 2 2 0 0 0 0-4zm0 3a1 1 0 1 1 0-2 1 1 0 0 1 0 2z"/>
            <path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0zM4 8a4 4 0 1 0 8 0 4 4 0 0 0-8 0z"/>
        </svg>

        <div>Loading<span class="Uno">.</span><span class="Due">.</span><span class="Tre">.</span></div>
    </div>
</template>

<script>
export default {
    name: 'DiscLoader',
}
</script>

<style scoped lang="scss">

    * {
        font-size: 20px;
        font-weight: 600;
    }

    svg {
        height: 80px;
        color: #717377;
        margin-bottom: 20px;
        animation: rotate 2s linear infinite;
    }

    @keyframes rotate {
        from {
            transform: rotateY(0);
        }
        to {
            transform: rotateY(360deg);
        }
    }

    .Uno,
    .Due,
    .Tre {
        position: relative;
    }

    .Uno {
        animation: bouncing 1s linear infinite;
    }
    .Due {
        animation: bouncing 1s linear 0.3s infinite;
    }
    .Tre {
        animation: bouncing 1s linear 0.5s infinite;
    }

    @keyframes bouncing {
        0% {
            bottom: 0;
            }
        50% {
            bottom: 2px;
        }
        100% {
            bottom: 0
        }
    }

</style>