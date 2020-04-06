<template>
    <header class="header">
        <div class="header__inner">
            <div class="header__logo">
                <router-link tag="a" to="/">dice<br>masters</router-link>
            </div>
            <div class="header__current-page">
                <p>dice masters</p>
            </div>
            <nav class="header__nav">
                <button class="header__nav__button" :class="headerNavigationButtonClass"></button>
                <ul class="header__nav-list">
                    <template v-for="(item, index) in navigation">
                        <router-link class="header__nav-list__item" tag="li" :to="item.path" :key="index">
                            {{ item.name }}
                        </router-link>
                    </template>
                </ul>
            </nav>
        </div>
    </header>
</template>

<script>
    export default {
        data() {
            return {
                navigation: [
                    { name: 'Home', path: '/' },
                    { name: 'About', path: '/about' },
                    { name: 'Skills', path: '/skills' },
                    { name: 'Contacts', path: '/contacts' }
                ],
                navigationStatus: false
            }
        },
        computed: {
            headerNavigationButtonClass() {
                return (this.navigationStatus) ? 'header__nav__button--close' : 'header__nav__button--close'
            }
        }
    }
</script>

<style lang="stylus" scoped>
    .header
        width 100%
        height 40px
        background-color white
        border-bottom 3px solid black
</style>