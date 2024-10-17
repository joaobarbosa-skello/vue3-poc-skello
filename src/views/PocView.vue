<script setup>
import MultipleRoots from '@/components/fragments/MultipleRoots.vue'
import HookItem from '@/components/lifecycle/HookItem.vue'
import CoreItem from '@/components/reactivity/CoreItem.vue'
import TunnelItem from '@/components/teleport/TunnelItem.vue'
</script>

<template>
  <div class="about">
    <h1>Welcome to the PoC</h1>
    <span class="description">
      This is a PoC from Skello's Tech Watch Day and the purpose is to explore
      the differences between Vue2 and Vue3
    </span>
    <span
      >João Romano Barbosa - Full Stack Developer
      <a href="https://skello.io/">@Skello</a></span
    >
    <h2>Resources</h2>
    <a href="https://vuejs.org/guide/introduction.html">
      VueJS Official Documentation
    </a>
    <a
      href="https://medium.com/@emperorbrains/vue-2-vs-vue-3-exploring-the-evolution-of-vue-js-03dab173e8a3"
    >
      Medium Article - Vue2 vs Vue3
    </a>
    <a href="https://trio.dev/vue-2-vs-vue-3/"> Trio Article - Vue2 vs Vue3 </a>
    <h2>Examples</h2>
    <section>
      <h3>
        <a href="https://v3-migration.vuejs.org/new/fragments#_3-x-syntax">
          Multiple Roots + Fragments
        </a>
      </h3>
      <div class="multiple-roots-container">
        <span class="multiple-roots-heading">#template</span>
        <MultipleRoots id="1337" />
      </div>
      <span
        >In 3.x, components now can have multiple root nodes! However, this does
        require developers to explicitly define where attributes should be
        distributed.</span
      >
    </section>
    <section>
      <h3>
        <a href="https://vuejs.org/api/reactivity-core.html">
          Reactivity API: Core
        </a>
      </h3>
      <CoreItem />
    </section>
    <section>
      <h3>
        <a href="https://vuejs.org/api/composition-api-lifecycle.html">
          Composition API: Lifecycle Hooks
        </a>
      </h3>
      <HookItem />
    </section>
    <section>
      <h3>
        <a href="https://vuejs.org/guide/built-ins/teleport.html">Portals</a>
      </h3>
      <TunnelItem />
    </section>
  </div>
</template>

<style>
h1 {
  margin: 1rem 0;
}

h2 {
  margin: 1rem 0 1rem;
  border-bottom: 3px solid #bbb;
}

h3 {
  margin-bottom: 1rem;
  font-weight: 700;
}

section {
  padding: 1rem 0;
}

.description {
  display: block;
  margin-bottom: 1rem;
}

@media (min-width: 1024px) {
  .about {
    padding-top: 35vh;
    padding-bottom: 35vh;
    height: 100vh;
    display: flex;
    flex-direction: column;
    overflow: scroll;
  }
}

.about::-webkit-scrollbar {
  display: none;
}

.multiple-roots-container {
  position: relative;
  display: flex;
  justify-content: space-around;
  flex-direction: row;
  margin: 2rem 0;
  border: 1px solid var(--color-border);
}

.multiple-roots-heading {
  position: absolute;
  top: -1rem;
  left: 1rem;
  background-color: var(--color-background);
  padding: 0 1rem;
  font-weight: 700;
}
</style>
