<template>
 <nav :class="['navbar-' + theme, 'bg-' + theme, 'navbar', 'navbar-expand-lg', 'border-bottom', 'border-2', 'border-danger', 'shadow']">
                        <div class="container-fluid">
                            <a href="" class="navbar-brand">
                                <img class="img-fluid" src="../assets/logo.png" alt="" style="width: 50%;">
                            </a>
                            <ul class="navbar-nav mb-2 mb-lg-0 ml-2 ">
                                <li v-for="(page,index) in pages" class="nav-item mx-2 " :key="index">
                                    <a v-bind:href="page.link.url" 
                                    v-bind:title="'This link goes to the ' + page.link.text + ' page'"
                                    aria-current="page"
                                    class="nav-link"
                                    :class="{active: activePage==index}"
                                    @click.prevent="navLinkClick(index)"
                                    >{{ page.link.text}} 
                                </a>
                                </li>
                                <form  class="d-flex">
                                    <button class="btn btn-primary"
                                    @click.prevent=changeTheme()>
                                    Toggle</button>
                                </form>
                            </ul>                          
                        </div>
                    </nav>
</template>

<script>
export default{
    props:['pages','activePage','navLinkClick'],
            data(){
                return{
                    theme:'light',
                  

                }
                
            },
            methods: {
                        changeTheme(){
                            let theme = 'light'

                            if(this.theme == 'light'){
                                theme='dark';
                            }

                            this.theme=theme
                        }
            },
    
}
</script>