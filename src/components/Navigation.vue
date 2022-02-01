<template>
    <div>
    <header :class="{'scrolled-nav':scrolledNav}">
        <nav>
            <div class="brand">
                <img src="" alt="">
            </div>
            <ul v-show="!mobile" class="navigation">
                <li>
                    <router-link class="link" :to="{name:'Home'}"></router-link>
                    <router-link class="link" :to="{name:'About'}">About</router-link>
                    <router-link class="link" :to="{name:'Portfolio'}">Portfolio</router-link>
                    <router-link class="link" :to="{name:'Contact'}">Contact</router-link>
                </li>
            </ul>
            <div class="icon">
            <i @click="toggleMobileNav" v-show="mobile" class="far fa bars" :class="{'icon-active' : mobileNav}"></i>
            </div>
            <transition name="mobile-nav">
            <ul v-show="mobileNav" class="dropdown-nav">
                <li>
                    <router-link class="link" :to="{name:'Home'}"></router-link>
                    <router-link class="link" :to="{name:'About'}">About</router-link>
                    <router-link class="link" :to="{name:'Portfolio'}">Portfolio</router-link>
                    <router-link class="link" :to="{name:'Contact'}">Contact</router-link>
                </li>
            </ul>    
            </transition>
        </nav>
    </header>
    <router-view/>
    </div>
</template>

<script>
export default {
    name:'navigation',
    data() {
        return {
            scrolledNav: null,
            mobile: null,
            mobileNav: null,
            windowWidth: null,            
        };
    },
    created() {
        window.addEventListener('resize', this.checkScreen);
    },
    mounted() {
        window.addEventListener("scroll", this.updateScroll);
    },
    methods: {
        toggleMobileNav() {
            this.mobileNav = !this.toggleMobileNav
        },

        updateScroll(){
            const scrollposition =window.scrollY;
            if (scrollPostion > 50) {
                this.scrolledNav = true;
                return;
            }
            this.scrolledNav = false;
        },

        checkScreen() {
            this.windowWidth = window.innerWidth;
            if (this.windowWidth <= 750) {
                this.mobile = true;
                return;
            }
            this.mobile = false;
            this.mobileNav = false;
        }
    }

}
</script>



