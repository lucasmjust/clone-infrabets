<template>
    <main class="pt-28 flex justify-around gap-6 p-6 px-20  bg-[url('../../public/img/bg-capa.jpg')] bg-cover bg-no-repeat bg-center">
        <div class="content w-1/2 p-4 flex flex-col justify-center items-center gap-12">
            <div class="text-size-one">
                <P class="text-4xl font-black p-2 tracking-widest text-left text-slate-100">SISTEMA DE APOSTAS ESPORTIVAS COM +<br>
                    <span>{{ typeValue }} <span class="invisible">.</span></span>
                </P>
            </div>
            <div class="text-size-two">
                <P class="text-xl font-lg p-4 text-left leading-relaxed text-slate-100">Monte sua banca com o melhor sistema de apostas esportivas do mercado, <i><strong>futebol pré jogo e ao vivo, mma, basquete, vólei, tênis e gerador de banner já incluso</strong></i>, sistema 100% automático, alugue sua banca esportiva com melhor custo-benefício do mercado.</P>
            </div>
            <button type="button" class="p-2 px-6 mr-64 mb-8 rounded-full border-4 border-slate-100 shadow-md flex gap-3 items-center bg-green-100 hover:bg-blue-500 hover:border-4 box-border hover:transition hover:text-slate-100"> <DevicePhoneMobileIcon class="h-6 w-6 text-green-500"/> 
                <span class="mt-2">ENTRE EM CONTATO AGORA</span>
            </button>
        </div>
        <div class="img w-auto">
            <img class="w-96" src="../../public/img/capa.png" alt="">
        </div>
    </main>
</template>
<script>
    import { DevicePhoneMobileIcon } from '@heroicons/vue/24/outline'
    import 'animate.css'
    
    export default {
      components: { DevicePhoneMobileIcon },

      data: () => {
      return {
        typeValue: '',
        typeStatus: false,
        typeArray: ["ESPORTES","SEGURANÇA","RENTABILIDADE","MERCADOS","EXCLUSIVIDADE","SEGURANÇA","VELOCIDADE"],
        typingSpeed: 30,
        erasingSpeed: 10,
        newTextDelay: 2000,
        typeArrayIndex: 0,
        charIndex: 0
      }
    },
    methods: {
      typeText() {
        if(this.charIndex < this.typeArray[this.typeArrayIndex].length) {
          if(!this.typeStatus)
            this.typeStatus = true;
          this.typeValue += this.typeArray[this.typeArrayIndex].charAt(this.charIndex);
          this.charIndex += 1;
          setTimeout(this.typeText, this.typingSpeed);
        }
        else {
          this.typeStatus = false;
          setTimeout(this.eraseText, this.newTextDelay);
        }
      },
      eraseText() {
        if(this.charIndex > 0) {
          if(!this.typeStatus)
            this.typeStatus = true;
          this.typeValue = this.typeArray[this.typeArrayIndex].substring(0, this.charIndex - 1);
          this.charIndex -= 1;
          setTimeout(this.eraseText, this.erasingSpeed);
        }
        else {
          this.typeStatus = false;
          this.typeArrayIndex += 1;
          if(this.typeArrayIndex >= this.typeArray.length)
            this.typeArrayIndex = 0;
          setTimeout(this.typeText, this.typingSpeed + 1000);
        }
      }
    },
    created() {
      setTimeout(this.typeText, this.newTextDelay + 200);
    }
    }
    </script>