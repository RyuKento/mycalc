<template>
  <b-container>
   <b-input-group prepend="足し算">
    <b-form-input type="number" v-model="a"></b-form-input>
    <b-input-group-prepend is-text><b>+</b></b-input-group-prepend>
    <b-form-input type="number" v-model="b"></b-form-input>
    <b-input-group-append is-text><b>=</b></b-input-group-append>
    <b-input-group-append is-text><b>{{Number(a)+Number(b)}}</b></b-input-group-append>
   </b-input-group>
   <b-input-group prepend="引き算">
    <b-form-input type="number" v-model="a"></b-form-input>
    <b-input-group-prepend is-text><b>-</b></b-input-group-prepend>
    <b-form-input type="number" v-model="b"></b-form-input>
    <b-input-group-append is-text><b>=</b></b-input-group-append>
    <b-input-group-append is-text><b>{{Number(a)-Number(b)}}</b></b-input-group-append>
   </b-input-group>
      <b-input-group prepend="掛け算">
    <b-form-input type="number" v-model="a"></b-form-input>
    <b-input-group-prepend is-text><b>*</b></b-input-group-prepend>
    <b-form-input type="number" v-model="b"></b-form-input>
    <b-input-group-append is-text><b>=</b></b-input-group-append>
    <b-input-group-append is-text><b>{{Number(a)*Number(b)}}</b></b-input-group-append>
   </b-input-group>
      <b-input-group prepend="割り算">
    <b-form-input type="number" v-model="a"></b-form-input>
    <b-input-group-prepend is-text><b>/</b></b-input-group-prepend>
    <b-form-input type="number" v-model="b"></b-form-input>
    <b-input-group-append is-text><b>=</b></b-input-group-append>
    <b-input-group-append is-text><b>{{Number(a)/Number(b)}}</b></b-input-group-append>
   </b-input-group>
  </b-container>     
</template>

<script>
export default {
  name: 'IndexPage',
  data(){
    return {
      a: 0,
      b: 0
    }
  }
}
</script>
