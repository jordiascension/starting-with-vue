<template>
  <div class="hello">
    <div>
      <h1>{{ msg }}</h1>
      <p>
        Hello World from Your Starter Component
      </p>
      <br/>
      <p>
          {{ count }} <br/>
          <button @click="increment">+</button>
          <button @click="decrement">-</button>
      </p>
    </div>
    <br/>
    <div>
      <p>Mensaje original: "{{ msg }}"</p>
      <p>Mensaje invertido computado: "{{ reverseMessage }}"</p>
    </div>
    <br/>
    <div v-if="Math.random() > 0.5">
        Ahora me ves
    </div>
    <div v-else>
        Ahora no
    </div>
    <div v-if="type === 'A'">
      A
    </div>
    <div v-else-if="type === 'B'">
      B
    </div>
    <div v-else-if="type === 'C'">
      C
    </div>
    <div v-else>
      Si no es A, B o C
    </div>
    <br/>
    <div>
      <button type="button" 
          class="btn btn-primary" @click="test">Call a method</button>
      <div class="divider"/>
          <button type="button" 
          class="btn btn-success" @click="testWithParameter('Pepe')">Call a method with parameter</button>
    </div>
    <br/>
    <div>
    <ul id="example-1">
        <li v-for="user in users" :key="user.id">
            {{ user.firstName }}
        </li>
    </ul>
    </div>
    
  </div>    
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'StartingWithVue',
  props: {
    msg: {required: true, type: String},
    type: {default: 'A', type: String}
  },
  data: () => ({
        /*This data is private, and only for the component itself to use. 
          Other components do not have access to it.
        */
        count: 0
  }),
  computed: {
        reverseMessage: function() {
            return this.msg.split('').reverse().join('')
        }
  },
  methods: {
        //All we have to do is update count, and Vue detects this change.
        // It then re-renders our app with the new value!
        increment() {
            this.count += 1;
        },
        decrement() {
            this.count -= 1;
        },
        test: function() {
            alert('test fuction with this message ' + this.message);
        },
        testWithParameter: function(name) {
            alert('hello ' + name);
        }
    },
    setup(props) {
        alert('The message is ' + props.message)
        // make users variable reactive with the ref() function
        const users = ref([
            { firstName: 'Frank', lastName: 'Murphy', age: 24 },
            { firstName: 'Vic', lastName: 'Reynolds', age: 30 },
            { firstName: 'Gina', lastName: 'Jabowski', age: 40 },
            { firstName: 'Jessi', lastName: 'Glaser', age: 50 },
            { firstName: 'Jay', lastName: 'Bilzerian', age: 60 }
        ]);

        return {
            users
        };
    }   
}
</script>