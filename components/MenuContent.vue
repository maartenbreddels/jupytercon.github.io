<template>
    <div class="clearfix">
        <nav>
            <ul class="menu">
                <li class="menu-block float-left" v-for="block in menuData" v-if="!block.disabled">
                    <h3>
                        <nuxt-link v-if="block.to" :to="block.to">{{ block.label }}</nuxt-link>
                        <div class="no-title" v-else="">{{ block.label }}</div>
                    </h3>
                        <div v-for="item in block.items" class="anchor-link">
                            <nuxt-link
                                    v-if="typeof item === 'string'"
                                    :to="{ path: block.to, hash: item }"
                            >- {{ item }}</nuxt-link>
                            <nuxt-link
                                    v-if="typeof item === 'object'"
                                    :to="{ path: (item.to || block.to), hash: item.anchor }"
                            >- {{ item.label }}</nuxt-link>
                        </div>
                </li>
            </ul>
        </nav>
    </div>
</template>

<script>
    export default {
        name: "MenuContent",
        data() {
            return {
                menuData: [{
                    label: 'About',
                    to: '/about/',
                    items: [
                        'What is it?',
                        'Past Events',
                        'Organizing Committee',
                        { label: 'Code of Conduct', to: '/codeofconduct/' },
                        { label: 'Diversity', anchor: "conduct-diversity-eco" },
                        { label: 'Eco-friendly efforts', to: '/sustainability/' }
                    ]
                }, {
                    label: 'Participate',
                    to: '/participate/',
                    items: [
                        'Register / Tickets',
                        'Call for proposals',
                        { label: 'Propose a talk', anchor: "Call for proposals" },
                        { label: 'Propose a tutorial', anchor: "Call for proposals" },
                        { label: 'Attend sprints', to: "/sprint/" },
                    ]
                }, {
                    label: 'Program',
                    disabled: true,
                    items: [
                        'Schedule',
                        'Social events',
                        'Tips for attendees'
                    ]
                }, {
                    label: 'Venue',
                    to: '/venue/',
                    items: [
                        'Conference center',
                        'Getting there',
                        'Hotel and local info',
                        'Child care',
                        'Things to do'
                    ]
                }, {
                    label: 'Sponsors',
                    to: '/sponsors/',
                    items: [
                        'Sponsoring',
                        'Sponsors',
                        'Community Sponsors'
                    ]
                }]
            }
        }
    }
</script>

<style lang="sass">


</style>
