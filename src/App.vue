<script setup>
import Header from "@/components/SimpleHeader.vue";
import Simple from "@/components/Simple.vue";
import EngineHeader from "@/components/EngineHeader.vue";
import Engine from "@/components/Engine.vue";
import Prog from "@/components/Prog.vue";
import ProgHeader from "@/components/ProgHeader.vue";
import ProgOpHeader from "@/components/ProgOpHeader.vue";
import ProgOp from "@/components/ProgOp.vue";

</script>

<template>
  <header>
    <Header/>
  </header>

  <main>
    <Simple/>
  </main>

  <header>
    <EngineHeader/>
  </header>

  <main>
    <Engine/>
  </main>

  <header>
    <ProgHeader/>
  </header>

  <main>
    <Prog/>
  </main>

  <header>
    <ProgOpHeader/>
  </header>

  <main>
    <ProgOp/>
  </main>

</template>