<template>
    <div>
        <!-- {{ item }} -->
        <div class="mx-auto">
            <div class="bg-white shadow-md border border-gray-200 rounded-lg max-w-sm dark:bg-gray-800 dark:border-gray-700 m-auto">
                <a href="#">
                    <img class="rounded-t-lg" :src="item.img" alt="">
                </a>
                <div class="p-5">
                    <a href="#">
                        <h5 class="text-gray-900 font-bold text-2xl tracking-tight mb-2 dark:text-white">{{ item.titulo }}</h5>
                    </a>
                    <p class="font-normal text-gray-700 mb-3 dark:text-gray-400">{{ item.descripcion }}</p>
                    <div class="relative h-10 w-10">
                        <img
                        class="h-full w-full rounded-full object-cover object-center"
                        :src="item.creador.img"
                        v-if="item.creador.img"
                        alt=""
                        />
                        <span class="absolute right-0 bottom-0 h-2 w-2 rounded-full bg-green-400 ring ring-white"></span>
                    </div>
                    <div class="text-sm mb-2">
                        <div class="font-medium text-gray-700">{{item.creador.nombre}}</div>
                        <!-- <div class="text-gray-400">{{item.creador.role}}</div> -->
                        <div class="text-gray-400 mt-2">
                            <span
                            class="inline-flex items-center gap-1 rounded-full bg-blue-50 px-2 py-1 text-xs font-semibold text-blue-600"
                            >
                            {{item.creador.role}}
                            </span>    
                        </div>
                        

                        <!-- <div class="font-medium text-gray-700">{{item.titulo}}</div>
                        <div class="text-gray-400">{{item.descripcion}}</div> -->
                    </div>
                    <a href="#" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-3 py-2 text-center inline-flex items-center  dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
                        Read more
                        <svg class="-mr-1 ml-2 h-4 w-4" fill="currentColor" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" d="M10.293 3.293a1 1 0 011.414 0l6 6a1 1 0 010 1.414l-6 6a1 1 0 01-1.414-1.414L14.586 11H3a1 1 0 110-2h11.586l-4.293-4.293a1 1 0 010-1.414z" clip-rule="evenodd"></path></svg>
                    </a>
                </div>
            </div>

            </div>
    </div>
</template>
<script>
export default {
    props: ['item']
}
</script>