<template lang="pug">
    nav
        v-toolbar(flat) 
            v-app-bar-nav-icon.grey--text(@click='drawer = !drawer')
            v-toolbar-title.text-uppercase.grey--text
            span.font-weight-light StaringGenie TODO
            v-spacer
            v-btn(text color='grey')
                span Sign Out
                v-icon(right) exit_to_app
        v-navigation-drawer(app v-model='drawer')
            v-list(
            :rounded="true"
            )       
                    v-app-bar-nav-icon.grey--text(@click='drawer = !drawer')
                    v-list-item(v-for='(item, i) in items' :key='i' router :to= "item.route")
                        v-list-item-icon
                            v-icon(v-text='item.icon')
                        v-list-item-content
                            v-list-item-title(v-text='item.text')
            

</template>

<script>
export default {
    data() {
        return {
            drawer: false,
            items: [
                {icon: 'dashboard', text: 'Dashboard', route: '/'},
                {icon: 'folder', text: 'My Projects', route: '/projects'},
                {icon: 'person', text: 'Team', route: '/team'}
            ]
        
        }
    },
}
</script>