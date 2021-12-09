<template>
    <div class="rlv-signIn">
        <b-row>
        <b-col class="rlv-zindex d-none d-lg-block">
          <div class="rlv-imagen-sign-up">
        <b-img :src="require('../static/img/signin/signin.png')" fluid ></b-img>
      </div>
        </b-col>
        <b-col>
            <RLVSignIn />
        </b-col>
        </b-row>
    </div>
</template>

<script>