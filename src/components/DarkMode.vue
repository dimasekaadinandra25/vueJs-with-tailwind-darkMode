<template>
    <div class="antialiased flex items-center justify-center min-h-screen bg-gray-200 dark:bg-gray-700">
        <div class="w-5/12">
            <div class="bg-white dark:bg-gray-800 dark:text-white shadow p-4 rounded-lg mb-6 flex justify-between items-center">
                <div class="font-semibold text-lg text-gray-500">Dark Mode Switch</div>
                <div>
                    <button @click.prevent="selectTheme('light')" class="focus:outline-none w-5 h-5 bg-gray-200 rounded-full mr-2"></button>
                    <button @click.prevent="selectTheme('dark')" class="focus:outline-none w-5 h-5 bg-black rounded-full"></button>
                </div>
            </div>

            <div class="bg-white dark:bg-gray-800 shadow rounded-lg overflow-hidden">
                <div class="px-10 py-8">
                    <h1 class="text-2xl font-bold text-gray-800 dark:text-white mb-6">Lorem ipsum dolor sit amet consectetur.</h1>
                    <div class="leading-relaxed text-gray-500 dark:text-gray-300 text-lg">
                        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Officia ratione quibusdam corporis impedit minima reprehenderit necessitatibus fugit ab deleniti recusandae perferendis ad eaque sit unde, est nihil voluptatem temporibus. Exercitationem nesciunt expedita nemo illum quod quam tempora ipsum itaque quo quas? Unde labore aperiam perferendis. Tempora, qui dignissimos! Commodi, eligendi.
                    </div>
                </div>
                <div class="px-10 py-6 bg-white dark:bg-gray-900 border-gray-200 dark:border-gray-900 dark:text-gray-200">Lorem ipsum dolor sit amet.</div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'DarkMode',
    methods: {
        selectTheme(indexing){
            localStorage.setItem('theme', indexing)
            const html = document.querySelector('html')
            html.classList.add(localStorage.getItem('theme'))
            if(indexing == "dark"){
                html.classList.remove('light')
            }else{
                html.classList.remove('dark')
            }
        },
    },
    mounted() {
        document.querySelector('html').classList.add(localStorage.getItem('theme'))
    }
}
</script>