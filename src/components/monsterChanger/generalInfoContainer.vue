<template>
  <v-container>
    <!-- perception frame -->
    <v-row>
      <v-col>
        <input-field
          type="number"
          property="perceptionFrom"
          label="Perception"
        ></input-field>
        
      </v-col>
    </v-row>
    <!-- skills from frame -->
    <v-row>
      <v-col
        v-for="(skill,i) in monsterChanger.skillsFrom"
        :key="i"
        :cols="3"
      >
        <skill-entry
          :skill="skill"
          :i="i"
        ></skill-entry>
      </v-col>
    </v-row>
    <v-row>
      <v-col>
        <add-from-skill-container></add-from-skill-container>
      </v-col>
    </v-row>
    <!-- stats frame -->
    <v-row>
      <v-col
        v-for="(stat,i) in stats"
        :key="i"
      >
        <stat-entry
          :i="i"
          :propertyName="stat"
        ></stat-entry>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import monsterChanger from "@/models/monsterChanger.js";
import inputField from '@/components/monsterChanger/inputField.vue';
import skillEntry from '@/components/monsterChanger/skillEntry.vue';
import addFromSkillContainer from '@/components/monsterChanger/addFromSkillContainer.vue';
import statEntry from '@/components/monsterChanger/statEntry.vue';

export default {
  name: "generalInfoContainer",
  components: { inputField, skillEntry, addFromSkillContainer, statEntry },
  data: () => ({
    monsterChanger,
    stats: ["strFrom","dexFrom","conFrom","intFrom","wisFrom","chaFrom"]
  })
}
</script>