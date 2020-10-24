<template>
    <div class="MainPiano">
        <img id="emoji" class="Emoji m-auto" src="" alt="">
        <div class="Piano__container flex flex-column bg-black m-auto">
            <div class="toucheBlanche flex relative m-auto">
                <button class="blanche rounded-l-lg" @click="onC(), getEmoji()" @keyup.67="onC()"></button>
                <button class="blanche ml-1" @click="onD(), getEmoji()"></button>
                <button class="blanche ml-1" @click="onE(), getEmoji()"></button>
                <button class="blanche ml-1" @click="onF(), getEmoji()"></button>
                <button class="blanche ml-1" @click="onG(), getEmoji()"></button>
                <button class="blanche ml-1" @click="onA(), getEmoji()"></button>
                <button class="blanche ml-1 rounded-r-lg" @click="onB(), getEmoji()"></button>
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
        <div class="Notes__container m-auto hidden md:flex">
            <div class="note ml-6">
                <p>DO</p>
            </div>
            <div class="note">
                <p>RE</p>
            </div>
            <div class="note">
                <p>MI</p>
            </div>
            <div class="note">
                <p>FA</p>
            </div>
            <div class="note">
                <p>SOL</p>
            </div>
            <div class="note">
                <p>LA</p>
            </div>
            <div class="note">
                <p>SI</p>
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

            const nbRandom = Math.floor(Math.random() * Math.floor(25))
            console.log(gifs[nbRandom].images['fixed_width'].webp)
            const urlRandom = gifs[nbRandom].images['fixed_width'].webp
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

.Piano__container {
    height: 276px;
    width: 531px;
    border-radius: 10px;
}

@media only screen and (max-width: 767px) {
    .Piano__container {
        max-height: 190px ;
        max-width: 368px ;
        margin-top: 70px ;
    }
}

.Emoji {
    height: 200px;
    margin-top: 105px;
}

.blanche {
    height: 252px;
    width: 69px;
    left: 450px;
    top: 12px;
    @apply bg-white;
}

@media only screen and (max-width: 767px) {
    .blanche {
        height: 173px;
        width: 47px;
    }
}

.blanche:hover {
    @apply bg-yellow-hover;
} 

.firstNoir {
    height: 184px;
    width: 30px;
    left: 68px;
    top: 12px;
    margin-top: 9px;
    margin-left: 68px;
    @apply bg-black rounded-b-lg;
}

@media only screen and (max-width: 767px) {
    .firstNoir {
        height: 126px;
        width: 21px;
        margin-left: 45px;
    }
}

.noir {
    height: 184px;
    width: 30px;
    left: 68px;
    top: 12px;
    margin-top: 9px;
    margin-left: 43px;
    @apply rounded-b-lg;
}

@media only screen and (max-width: 767px) {
    .noir {
        height: 126px;
        width: 21px;
        margin-left: 30px;
    }
}

.Notes__container {
    height: 252px;
    width: 507px;
    margin-top: 15px;
}
.note {
    @apply text-white;
}
</style>