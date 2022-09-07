<template>
    <div id="app">
        <h3>Teambase Router</h3>
        <h4>
          <router-link class="link" to="/data/character">Meet the Character</router-link> | 
          <router-link class="link" to="/data/location">Explore the planet</router-link>
        </h4>
        <router-view></router-view>
    </div>
</template>