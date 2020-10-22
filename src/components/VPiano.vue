<template>
    <div class="MainPiano">
        <img id="emoji" class="m-auto" src="" alt="">
        <div class="Piano__container flex flex-column bg-black m-auto">
            <div class="toucheBlanche flex py-3 relative">
                <button class="firstBlanche" @click="onC(), getEmoji()"></button>
                <button class="blanche" @click="onD(), getEmoji()"></button>
                <button class="blanche" @click="onE(), getEmoji()"></button>
                <button class="blanche" @click="onF(), getEmoji()"></button>
                <button class="blanche" @click="onG(), getEmoji()"></button>
                <button class="blanche" @click="onA(), getEmoji()"></button>
                <button class="blanche rounded-r-lg" @click="onB(), getEmoji()"></button>
            </div>
            <div class="toucheNoir flex z-5 absolute">
                <button class="firstNoir hover:bg-rose-hover" @click="onC2(), getEmoji()"></button>
                <button class="noir bg-black hover:bg-rose-hover" @click="onD2(), getEmoji()"></button>
                <button class="noir bg-transparent"></button>
                <button class="noir bg-black hover:bg-rose-hover" @click="onF2(), getEmoji()"></button>
                <button class="noir bg-black hover:bg-rose-hover" @click="onG2(), getEmoji()"></button>
                <button class="noir bg-black hover:bg-rose-hover" @click="onA2(), getEmoji()"></button>
            </div>
        </div>
    </div>
</template>

<script>
import { GiphyFetch } from '@giphy/js-fetch-api'

export default {
    data() {
        return {
            gifs: []
        }
    },
    methods: {
        async getEmoji() {
            const gf = new GiphyFetch('hoc7Xw81iwUP2iewXhekupQznVmYDlHK')
            const { data: gifs } =  await gf.emoji()
            console.log(gifs)
            const nbRandom = Math.floor(Math.random() * Math.floor(25)) ;
            console.log(gifs[nbRandom].images['fixed_width'].webp) ;
            const urlRandom = gifs[nbRandom].images['fixed_width'].webp ;
            document.getElementById('emoji').src=urlRandom ;
        },
        onA() {
            const audio = document.createElement('audio')
            audio.src = 'assets/sounds/A.mp3'

            audio.play()
        },
        onA2() {
            const audio = document.createElement('audio')
            var chemin = 'assets/sounds/A#.mp3'
            var res = encodeURIComponent(chemin)
            audio.src = res

            audio.play()
        },
        onB() {
            const audio = document.createElement('audio')
            audio.src = 'assets/sounds/B.mp3'

            audio.play()
        },
        onC() {
            const audio = document.createElement('audio')
            audio.src = 'assets/sounds/C.mp3'

            audio.play()
        },
        onC2() {
            const audio = document.createElement('audio')
            var chemin = 'assets/sounds/C#.mp3'
            var res = encodeURIComponent(chemin)
            audio.src = res

            audio.play()
        },
        onD() {
            const audio = document.createElement('audio')
            audio.src = 'assets/sounds/D.mp3'

            audio.play()
        },
        onD2() {
            const audio = document.createElement('audio')
            var chemin = 'assets/sounds/D#.mp3'
            var res = encodeURIComponent(chemin)
            audio.src = res

            audio.play()
        },
        onE() {
            const audio = document.createElement('audio')
            audio.src = 'assets/sounds/E.mp3'

            audio.play()
        },
        onF() {
            const audio = document.createElement('audio')
            audio.src = 'assets/sounds/F.mp3'

            audio.play()
        },
        onF2() {
            const audio = document.createElement('audio')
            var chemin = 'assets/sounds/F#.mp3'
            var res = encodeURIComponent(chemin)
            audio.src = res

            audio.play()
        },
        onG() {
            const audio = document.createElement('audio')
            audio.src = 'assets/sounds/G.mp3'

            audio.play()
        },
        onG2() {
            const audio = document.createElement('audio')
            var chemin = 'assets/sounds/G#.mp3'
            var res = encodeURIComponent(chemin)
            audio.src = res

            audio.play()
        },
    }
}
</script>

<style lang="postcss" scoped>

.MainPiano {
    margin: auto;
}

.Piano__container {
    height: 276px;
    width: 531px;
    left: 0px;
    top: 0px;
    border-radius: 10px;
}

.firstBlanche {
    height: 252px;
    width: 69px;
    left: 450px;
    top: 12px;
    margin-left: 12px;
    @apply bg-white rounded-l-lg;
}

.blanche {
    height: 252px;
    width: 69px;
    left: 450px;
    top: 12px;
    margin-left: 4px;
    @apply bg-white;
}

.firstBlanche:hover {
    @apply bg-yellow-hover;
}
.blanche:hover {
    @apply bg-yellow-hover;
} 

.firstNoir {
    height: 184px;
    width: 30px;
    left: 68px;
    top: 12px;
    margin-top: 12px;
    margin-left: 68px;
    @apply bg-black rounded-b-lg;
}

.noir {
    height: 184px;
    width: 30px;
    left: 68px;
    top: 12px;
    margin-top: 12px;
    margin-left: 43px;
    @apply rounded-b-lg;
}

</style>