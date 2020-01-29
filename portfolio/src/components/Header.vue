<template>
    <div>
        <v-navigation-drawer v-model="drawer" absolute temporary>
            <v-list-item>
                <v-avatar class="profile" tile height="100" width="80">
                    <v-img src="@/static/chikkun.jpg" height="75" width="75"></v-img>
                </v-avatar>
                <v-list-item-content>
                    <v-list-item-title>Hideyasu Chiku</v-list-item-title>
                </v-list-item-content>
            </v-list-item>
            <v-divider></v-divider>
            <v-list dense>
                <v-list-item v-for="item in items" :key="item.title" :to="item.to">
                    <v-list-item-icon>
                        <v-icon>{{ item.icon }}</v-icon>
                    </v-list-item-icon>
                    <v-list-item-content>
                        <v-list-item-title>{{ item.title }}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-list>
        </v-navigation-drawer>
        <v-app-bar dark clipped-left fixed app height="40">
            <v-btn
                @click.stop="drawer = !drawer"
                class="hidden-md-and-up"
                color="white"
                tile
                icon
                large
            >
                <v-icon>mdi-menu</v-icon>
            </v-btn>
            <v-toolbar-title class="headline text-uppercase white--text">
                <span>HIDEYASU</span>
                <span class="font-weight-light">CHIKU</span>
            </v-toolbar-title>
            <v-spacer></v-spacer>
            <v-toolbar-items class="hidden-sm-and-down">
                <v-btn text to="/">Home</v-btn>
                <v-btn text to="/about">About</v-btn>
                <v-btn text to="/skillset">Skillset</v-btn>
                <v-btn text to="/works">Works</v-btn>
                <v-btn text to="/activities">Activities</v-btn>
                <v-btn text to="/contact">Contact</v-btn>
            </v-toolbar-items>
        </v-app-bar>
    </div>
</template>


<script>
export default {
  name: "Header",
  data() {
    return {
      drawer: null,
      items: [
        { title: "Home", icon: "mdi-view-dashboard", to: "/" },
        { title: "About", icon: "mdi-account-question", to: "/about" },
        { title: "Skillset", icon: "mdi-chart-bubble", to: "/skillset" },
        { title: "Works", icon: "mdi-lightbulb-on-outline", to: "/works" },
        { title: "Activities", icon: "mdi-chevron-triple-up", to: "/activities" },
        { title: "Contact", icon: "mdi-at", to: "/contact" }
      ]
    };
  }
};
</script>