<template>
    <div class="particles-container " >
        <vue-particles id="tsparticles" @particles-loaded="particlesLoaded" url="http://foo.bar/particles.json" />

        <vue-particles
            id="tsparticles"
            @particles-loaded="particlesLoaded"
            :options="{
                    background: {
                        color: {
                            value: '#ffffff'
                        }
                    },
                    fpsLimit: 120,
                    interactivity: {
                        events: {
                            onClick: {
                                enable: false,
                                mode: 'push'
                            },
                            onHover: {
                                enable: true,
                                mode: 'repulse'
                            },
                        },
                        modes: {
                            bubble: {
                                distance: 400,
                                duration: 200,
                                opacity: 5,
                                size: 40
                            },
                            push: {
                                quantity: 4
                            },
                            repulse: {
                                distance: 100,
                                duration: 1
                            }
                        }
                    },
                    particles: {
                        color: {
                            value: '#0d47a1'
                        },
                        links: {
                            color: '#0d47a1',
                            distance: 150,
                            enable: true,
                            opacity: 1,
                            width: 1
                        },
                        move: {
                            direction: 'none',
                            enable: true,
                            outModes: 'bounce',
                            random: false,
                            speed: 1,
                            straight: false
                        },
                        number: {
                            density: {
                                enable: true,
                            },
                            value: 80
                        },
                        opacity: {
                            value: 0.5
                        },
                        shape: {
                            type: 'circle'
                        },
                        size: {
                            value: { min: 1, max: 5 }
                        }
                    },
                    detectRetina: true
                }"
        />
    </div>
</template>
<style scoped>
.particles-container {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  z-index: -1;
  overflow: hidden;
  filter: blur(2px); /* Adjust the blur radius as needed */
}
</style>