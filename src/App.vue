<template>
  <div>
    <AccordionList></AccordionList>
  </div>
</template>

<script>
import AccordionList from './components/AccordionList.vue';

export default {
  name: 'App',
  data() {
    return {
      default: false
    }
  },
  components: {
    AccordionList,
  }
}
</script>

<style>
@keyframes fadeInDown {
    0% {
        opacity: 0;
        transform: translateY(-1.25em);
    }
    100% {
        opacity: 1;
        transform: translateY(0);
    }
}
details { 
    animation-name: fadeInDown;
    animation-duration: 0.5s;
    border: 1px solid rgb(79, 139, 190);
    background: rgb(79, 139, 190);
}
details {
  transition: height 1s ease;
}
details:not([open]) { height: 1.25em; }
details[open] { height: 3.75em; }
summary {
  border: 1px solid rgb(150, 179, 179);  
  background: rgb(150, 177, 177);
}
summary::-webkit-details-marker {
  display:none;
}
summary::-moz-list-bullet {
  list-style-type:none;
}
summary::marker {
  display:none;
  content: ''
} 
summary:before {  
  content: "+";
  margin-right: .3em;
}
details[open] > summary:before {
  content: "–";
}

</style>
