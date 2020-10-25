<template>
    <div class="MainPiano">
        <img id="emoji" class="Emoji m-auto" src="" alt="">
        <div class="Piano__container flex flex-column bg-black m-auto">
            <div class="toucheBlanche flex relative m-auto">
                <button class="blanche rounded-l-lg C" @click="onC(), getEmoji()"></button>
                <button class="blanche ml-1 D" @click="onD(), getEmoji()"></button>
                <button class="blanche ml-1 E" @click="onE(), getEmoji()"></button>
                <button class="blanche ml-1 F" @click="onF(), getEmoji()"></button>
                <button class="blanche ml-1 G" @click="onG(), getEmoji()"></button>
                <button class="blanche ml-1 A" @click="onA(), getEmoji()"></button>
                <button class="blanche ml-1 rounded-r-lg B" @click="onB(), getEmoji()"></button>
            </div>
            <div class="toucheNoir flex z-5 absolute">
                <button class="firstNoir hover:bg-rose-hover C2" @click="onC2(), getEmoji()"></button>
                <button class="noir bg-black hover:bg-rose-hover D2" @click="onD2(), getEmoji()"></button>
                <button class="thirdNoir bg-black hover:bg-rose-hover F2" @click="onF2(), getEmoji()"></button>
                <button class="noir bg-black hover:bg-rose-hover G2" @click="onG2(), getEmoji()"></button>
                <button class="noir bg-black hover:bg-rose-hover A2" @click="onA2(), getEmoji()"></button>
            </div>
        </div>
        <div class="Notes__container m-auto hidden md:flex">
            <div class="note ml-8">
                <p>DO</p>
            </div>
            <div class="note ml-12">
                <p>RE</p>
            </div>
            <div class="note ml-12">
                <p>MI</p>
            </div>
            <div class="note ml-16">
                <p>FA</p>
            </div>
            <div class="note ml-12">
                <p>SOL</p>
            </div>
            <div class="note ml-12">
                <p>LA</p>
            </div>
            <div class="note ml-12">
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
    mounted() {
        this.isPress = false
        this.addListeners()
    },
    methods: {
        addListeners() {
            document.addEventListener('keydown', this.onKeyDown)
            document.addEventListener('keyup', this.onKeyUp)
        },
        onKeyDown(e) {
            if (this.isPress) return
            switch (e.keyCode) {
                case 81: 
                    this.onC();
                    this.getEmoji();
                    document.getElementsByClassName('C')[0].style.backgroundColor = '#F1C40F';
                    break;
                case 83:
                    this.onD();
                    this.getEmoji();
                    document.getElementsByClassName('D')[0].style.backgroundColor = '#F1C40F';
                    break;
                case 68:
                    this.onE();
                    this.getEmoji();
                    document.getElementsByClassName('E')[0].style.backgroundColor = '#F1C40F';
                    break;
                case 70:
                    this.onF();
                    this.getEmoji();
                    document.getElementsByClassName('F')[0].style.backgroundColor = '#F1C40F';
                    break;
                case 71:
                    this.onG();
                    this.getEmoji();
                    document.getElementsByClassName('G')[0].style.backgroundColor = '#F1C40F';
                    break;
                case 72:
                    this.onA();
                    this.getEmoji();
                    document.getElementsByClassName('A')[0].style.backgroundColor = '#F1C40F';
                    break;
                case 74:
                    this.onB();
                    this.getEmoji();
                    document.getElementsByClassName('B')[0].style.backgroundColor = '#F1C40F';
                    break;
                case 90:
                    this.onC2();
                    this.getEmoji();
                    document.getElementsByClassName('C2')[0].style.backgroundColor = '#C2185B';
                    break;
                case 69:
                    this.onD2();
                    this.getEmoji();
                    document.getElementsByClassName('D2')[0].style.backgroundColor = '#C2185B';
                    break;
                case 84:
                    this.onF2();
                    this.getEmoji();
                    document.getElementsByClassName('F2')[0].style.backgroundColor = '#C2185B';
                    break;
                case 89:
                    this.onG2();
                    this.getEmoji();
                    document.getElementsByClassName('G2')[0].style.backgroundColor = '#C2185B';
                    break;
                case 85:
                    this.onA2();
                    this.getEmoji();
                    document.getElementsByClassName('A2')[0].style.backgroundColor = '#C2185B';
                    break;
            }
            this.isPress = true
        },
        onKeyUp() {
            this.isPress = false

            for (let i = 0 ; i < 7 ; i++) {
                document.getElementsByClassName('blanche')[i].style.backgroundColor = "#FFFFFF" ;
            }
            for (let j = 0 ; j < 1 ; j++) {
                document.getElementsByClassName('firstNoir')[j].style.backgroundColor = "#000000" ;
            }
            for (let j = 0 ; j < 1 ; j++) {
                document.getElementsByClassName('thirdNoir')[j].style.backgroundColor = "#000000" ;
            }
            for (let j = 0 ; j < 5 ; j++) {
                document.getElementsByClassName('noir')[j].style.backgroundColor = "#000000" ;
            }
        },
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

.thirdNoir {
    height: 184px;
    width: 30px;
    left: 68px;
    top: 12px;
    margin-top: 9px;
    margin-left: 116px;
    @apply rounded-b-lg;
}

@media only screen and (max-width: 767px) {
    .thirdNoir {
        height: 126px;
        width: 21px;
        margin-left: 82px;
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