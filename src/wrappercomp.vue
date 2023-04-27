<template>
    <div class="container">
        <div class="row">
            <div class="col-12">
                <app-header></app-header>
            </div>
        </div>
        <div class="row">
            <div class="col-4">
                <app-sidebar></app-sidebar>
            </div>
            <div class="col-8">
                <app-body></app-body>
            </div>
        </div>
        <div class="row mt-3">
            <div class="col-12">
                <app-footer></app-footer>
            </div>
        </div>
    </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Sidebar from './components/Sidebar.vue'
import Body from './components/Body.vue'
export default {
    components: {
        'app-header': Header,
        'app-footer': Footer,
        'app-sidebar': Sidebar,
        'app-body': Body
    }
}
</script>