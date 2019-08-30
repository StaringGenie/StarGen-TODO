<template lang="pug">
  <div>
    .dashboard
      h1.display-3.subheading.grey--text Dashboard
      v-container.my-5
        v-layout(row mb-5 )
            v-btn( small text @click="sortBy('title')")
              v-icon(left small) folder
              span.caption.text-lowercase By project name 
            v-btn( small text @click="sortBy('person')")
              v-icon(left small) person
              span.caption.text-lowercase By person   

        v-card( flat )
          v-layout( row wrap v-for="project in projects" :key="project.title" :class="`pa-3 project ${project.status}`" )
            v-flex( xs12 md6 )
              .caption.grey--text
                p Project title 
              p {{project.title}}  
            v-flex( xs6 sm4 md2 )
              .caption.grey--text
                p Person
              p {{project.person}} 
            v-flex( xs6 sm4 md2 )
              .caption.grey--text
                p Due by
              p {{project.due}}
            v-flex( xs6 sm4 md2 )
                p
                v-chip.right(:color="`${project.status}`" :class="`v-chip--active caption my-2 white--text`") {{project.status}}
          v-divider
              
                
                 
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {title: 'Design a new Website', person: 'StaringGenie', due:'1st June 2019', status: 'ongoing', content: 'Dolor culpa nulla adipisicing cupidatat ea sunt ex id culpa dolore. Excepteur eiusmod veniam voluptate nulla occaecat dolor. Aliqua reprehenderit minim aliqua deserunt. Fugiat amet exercitation deserunt tempor tempor.'},
        {title: 'Code a new Website', person: 'CtaringGenie', due:'2st June 2019', status: 'complete', content: 'Dolore mollit sunt aute mollit Lorem ut. Cupidatat excepteur amet irure consectetur cillum in excepteur anim cupidatat culpa ex veniam. Amet deserunt officia quis id amet culpa exercitation qui magna ullamco. Aliqua exercitation pariatur incididunt eu ea. Eu velit tempor fugiat tempor ex proident amet. Commodo nostrud fugiat ex velit nulla dolore enim duis commodo qui veniam. Fugiat mollit voluptate officia qui.'},
        {title: 'Deploy a new Website', person: 'EtaringGenie', due:'2st June 2019', status: 'overdue', content: 'Dolore mollit sunt aute mollit Lorem ut. Cupidatat excepteur amet irure consectetur cillum in excepteur anim cupidatat culpa ex veniam. Amet deserunt officia quis id amet culpa exercitation qui magna ullamco. Aliqua exercitation pariatur incididunt eu ea. Eu velit tempor fugiat tempor ex proident amet. Commodo nostrud fugiat ex velit nulla dolore enim duis commodo qui veniam. Fugiat mollit voluptate officia qui.'}
      ]
    }
  },
  methods: {
   sortBy(prop){
     this.projects.sort((a,b) => a[prop] < b[prop] ? -1 : 1)
   } 
  }
};
</script>


<style>

.project.complete{
  border-left: 4px solid #3cd1c2
}
.project.ongoing{
  border-left: 4px solid orange
}
.project.overdue{
  border-left: 4px solid tomato
}

.v-chip.complete{
  
  background:  #3cd1c2
}
.v-chip.ongoing{
 background: orange
}
.v-chip.overdue{
  background: tomato
}

</style>