<template>
    <header class="fixed w-full scroll:shadow-lg  bg-blue-500 p-5 px-32 flex justify-between items-center drop-shadow-lg">
        <img class="w-36 mb-2 ml-6 cursor-pointer" src="../../public/img/logo_light.png" alt="">
        <nav>
            <ul class="flex mt-2 gap-8">
                <li><a class=" text-slate-100 p-2 hover:text-green-400 hover:transition  hover:border-b-2 border-indigo-400" href="#">Início</a></li>
                <li><a class=" text-slate-100 p-2 hover:text-green-400 hover:transition  hover:border-b-2 border-indigo-400" href="#">Sobre nós</a></li>
                <li><a class=" text-slate-100 p-2 hover:text-green-400 hover:transition  hover:border-b-2 border-indigo-400" href="#">Nossas funcionalidades</a></li>
                <li><a class=" text-slate-100 p-2 hover:text-green-400 hover:transition  hover:border-b-2 border-indigo-400" href="#">Contato</a></li>
            </ul>
        </nav>
    </header>
</template>
<script>
    export default{
        data(){
            return{
            }
        }
    }
</script>