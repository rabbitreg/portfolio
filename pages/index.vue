<template>
  <v-container fluid color class="pa-0">
    <v-container fluid class="backgroundSub">
      <v-row justify="center">
        <v-col cols="12" md="8" lg="6" xl="5">
          <v-card elevation="2" outlined>
            <v-card-title
              ><h3>HELLOWORLD</h3>
              <v-img></v-img>
            </v-card-title>
            <v-card-text><p>HELLOWORLD</p></v-card-text>
          </v-card>
          <v-card elevation="2" outlined>
            <v-card-title><h3>HELLOWORLD</h3></v-card-title>
            <v-card-text><p>HELLOWORLD</p></v-card-text>
          </v-card>
          <v-card elevation="2" outlined>
            <v-card-title><h3>HELLOWORLD</h3></v-card-title>
            <v-card-text><p>HELLOWORLD</p></v-card-text>
          </v-card>
          <template>
            <div class="text-center">
              <v-pagination v-model="page" :length="3"> </v-pagination>
            </div>
          </template>
        </v-col>

        <v-col cols="12" md="3" lg="2" xl="2">
          <h3>SEARCH...</h3>
          <v-text-field label="TITLE" type="text">
            <template v-slot:append-outer>
              <v-btn color="#FFE0B3">search</v-btn>
            </template>
          </v-text-field>
          <h3>TAG</h3>
          <v-chip>{{ tag }}</v-chip>
          <h3>CATEGORIES</h3>
          <v-list-item active-class="default"></v-list-item>
          <h3>ABOUT ME</h3>
          <v-banner icon="images">MICHITSUJI</v-banner>
          <p>
            初めまして道草の管理人のしているものです。このサイトに立ち寄っていただきありがとうございます。
            lomosaitodeha
          </p>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>

<script></script>

<style>
.backgroundSub {
  background-color: #6d4c41;
}
</style>
