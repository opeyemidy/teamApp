<template>
  <div class="home">
    <h1>Home</h1>
    <p class="red white--text">Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni, distinctio quasi. Commodi hic dolores a iure ipsam aliquid exercitationem corrupti, autem nemo corporis quos placeat sapiente earum. Praesentium, repellat quo.</p>
    <p class="pink lighten-4 red--text text--darken-4">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Tenetur et consectetur rem veritatis quibusdam, itaque molestias nihil maiores hic ut? Atque non ad libero minus vel. Porro eos veniam sapiente.</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Corporis natus cupiditate beatae rem, ut ab. Possimus, animi quas officiis voluptas corporis consectetur magnam omnis impedit consequuntur odit id cumque dolores.</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam, quibusdam debitis quaerat corporis dignissimos quae hic recusandae quas, enim, voluptate possimus eveniet doloremque ex earum dicta odit eligendi totam repellendus.</p>
    <h1 class="display-4">Massive Display</h1>
    <h4 class="display-1">Smaller Display</h4>
    <p class="headline">this is a headline</p>
    <p class="subheading font-weight-bold text-capitalize">this is a subheading</p>
    <p class="caption">this is caption</p>
    <v-btn class="pink white--text">Click Me!</v-btn>
    <v-btn color="pink" depressed dark>Click Me!</v-btn>
    <v-btn text rounded color="pink">Click Me!</v-btn>
    <v-btn text rounded color="pink">
        <v-icon left small>mdi-email</v-icon>
        <span>email me</span>
    </v-btn>
    <v-btn dark color="pink">
        <span>email me</span>
        <v-icon right large >mdi-email</v-icon>
    </v-btn>
    <v-btn dark depressed small fab color="purple" class="hidden-md-down d-none d-lg-flex d-xl-none">
        <v-icon>mdi-heart</v-icon>
    </v-btn>
    <v-icon>mdi-checkbox-marked-circle-outline</v-icon>
    <!-- break point and visibility -->

  </div>
</template>

<script>

export default {

}
</script>
