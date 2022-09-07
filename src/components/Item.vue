<template>
   <div class="col-3">
     <div  class="card" align="center">
       <div class="card-body">
         <h5 class="card-title">{{ item.name }}</h5>
       </div>
        <div v-for="(value, key, index) in item">
          <div v-if="index < 4">
            <ul class="list-group list-group-flush">
              <li class="list-group-item"><strong>{{key}}</strong>: {{ value }}</li>
            </ul>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
  export default {
    props: ['item']
  }
</script>