<template>
    <button @click="test += ' row'">Add {{test}}</button>
    <div class="row">
        <div class="col-3" ref='sidebarWrapper'>
            <ul :style="'width:' + clientWidth + 'px'" class="divide-y divide-gray-100 overflow-hidden shadow-lg rounded-md bg-white fixed">
                <li class="p-3 hover:bg-blue-600 hover:text-blue-200">
                    <h1 class="text-2xl">Default Styles</h1>
                </li>
                <li>
                    <a href="#logo" @click.prevent="scroll('logo')" class="hover:bg-blue-600 hover:text-blue-200 w-full block p-3">Logo</a>
                </li>
                <li>
                    <a href="#Colours"  @click.prevent="scroll('color')" class="hover:bg-blue-600 hover:text-blue-200 w-full block p-3">Colors</a>
                </li>
            </ul>
        </div>
        <div class='col-9'>
            <section id="logo" class="bg-white p-4 rounded-md shadow-lg mb-4">
                <h1 class="text-xl font-weight-bold">Logo</h1>
                <hr class="my-2 border-2 border-black">
                <div class="row">
                    <!-- Mark Coloured -->
                    <div class="col-4 shadow-md rounded-md p-2">
                        <p class="underline">Logo Mark Coloured</p>
                        <img :src="$page.props.assets + `/Logo/mark-coloured.svg`" alt="">
                    </div>

                    <!-- Mark White -->
                    <div class="col-4 shadow-md rounded-md bg-gray-100 p-2">
                        <p class="underline">Logo Mark White</p>
                        <img :src="$page.props.assets + `/Logo/mark-white.svg`" alt="">
                    </div>

                    <!-- Mark Black -->
                    <div class="col-4 shadow-md rounded-md p-2">
                        <p class="underline">Logo Mark Black</p>
                        <img :src="$page.props.assets + `/Logo/mark-black.svg`" alt="">
                    </div>

                    <!-- Logo Black -->
                    <div class="col-4 shadow-md rounded-md p-2">
                        <p class="underline">Logo Dark</p>
                        <img :src="$page.props.assets + `/Logo/logo-dark.svg`" alt="">
                    </div>

                    <!-- Logo Light -->
                    <div class="col-4 shadow-md bg-gray-100 rounded-md p-2">
                        <p class="underline">Logo Light</p>
                        <img :src="$page.props.assets + `/Logo/logo-light.svg`" alt="">
                    </div>
                </div>
            </section>

            <br><br>

            <section id="color" class="bg-white p-4 rounded-md shadow-lg mb-4">
                <h1 class="text-xl font-weight-bold">Colours</h1>
                <hr class="my-2 border-2 border-black">
                <div class="row">
                    <!-- Logo Coloured -->
                    <div v-for="color in colors" :key="color" :class="'col-4 p-4 rounded shadow-md bg-' + color">
                        <p class="font-bold text-white text-lg">{{color}}</p>
                    </div>
                </div>
            </section>

            <br><br>

            <section id="typography" class="bg-white p-4 rounded-md shadow-lg mb-4">

            </section>
        </div>
    </div>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
    data(){
        return {
            test: 1,
            clientWidth: 0,
            colors: [
                'gray-900',
                'gray-800',
                'gray-700',
                'gray-300',
                'gray-200',
                'gray-100',
                'primary',
                'primary-dark',
                'primary-light',
                'secondary',
                'secondary-dark',
                'secondary-light',
                'success',
                'success-dark',
                'success-light',
                'warning',
                'warning-dark',
                'warning-light',
                'danger',
                'danger-dark',
                'danger-light',
                'accent-green',
                'accent-blue',
                'accent-peach',
                'accent-lightPeach',
                'accent-cyan',
            ],
        }
    },
    created() {
      window.addEventListener("resize", this.setSidebar);
   },
    mounted () {
        this.setSidebar();
    },
    methods: {
        setSidebar(e){
            this.clientWidth = this.$refs.sidebarWrapper.clientWidth;
        },
        scroll(selector){
            document.getElementById(selector).scrollIntoView({behavior: 'smooth'});
        }
    }
})
</script>
