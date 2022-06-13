<template>
    <header  v-bind:class="{'nav--close': !open } ">
        <div class="brand">
            <img src="../assets/images/logo.svg" alt="logo snap">
        </div>
        <div class="nav"> 
            <nav >
                <img @click=handleClickNav class="close" src="../assets/images/icon-close-menu.svg" alt="close menu" >
                <ul>
                    <li  class="nav__item--features">
                        <a href="#" v-on:submit.prevent="onSubmit"  @click=handleMenuChildFeatures >Features </a>

                        <div  v-bind:class="[childMenuFeatures ? 'drop--up' : 'drop--down']"></div>

                        <ul class='list' v-bind:class="{'list--open' : childMenuFeatures}" >
                            <li><a href="#"> <img src="../assets/images/icon-todo.svg" alt="logo todolist--open"> Todo
                                    List </a></li>
                            <li><a href="#"> <img src="../assets/images/icon-calendar.svg" alt="logo calendar"> Calendar
                                </a></li>
                            <li><a href="#"> <img src="../assets/images/icon-reminders.svg" alt="logo reminders">
                                    Reminders </a></li>
                            <li><a href="#"> <img src="../assets/images/icon-planning.svg" alt="logo planning"> Planning
                                </a></li>
                        </ul>
                    </li>
                    <li  class="nav__item--compagny">
                        <a  @click=handleMenuChildCompany href="#" v-on:submit.prevent="onSubmit">  Company</a>
                        <div v-bind:class="[childMenuCompany ? 'drop--up' : 'drop--down']" ></div>
                        <ul class="list"  v-bind:class="{'list--open' : childMenuCompany}" >
                            <li><a href="#">History</a></li>
                            <li><a href="#">Our Team</a></li>
                            <li><a href="#">Blog</a></li>
                        </ul>
                    </li>
                    <li><a href="#">Careers</a></li>
                    <li><a href="#">About</a></li>
                </ul>
                <div class="nav__user">
                    <a href="#">Login</a>
                    <a href="#">Register</a>
                </div>
            </nav>
        </div>
        <button @click=handleClickNav type="button" name="mobile menu" class="menu"></button>

    </header>
</template>

<script>
export default{
    data(){
        return{
            open: false,
            childMenuCompany: false,
            childMenuFeatures: false,
        }
    },
    methods: {
        handleClickNav(){
            this.open = !this.open
        },
        handleMenuChildCompany(){
            this.childMenuCompany = !this.childMenuCompany
        },
        handleMenuChildFeatures(){
            this.childMenuFeatures = !this.childMenuFeatures

        }
    }
}



</script>