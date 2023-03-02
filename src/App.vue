<script setup>
  const name = 'Diana';
  const styleColor = 'color: red';
  const arrayColor = ['pink','green','grey'];
  const activo = false;
  const arrayFrutas = ["🍎", "🍌", "🍉", "🍓", "🍒"];
  const arrayVerduras = [
        {
            name: "Manzana",
            price: "$1.00",
            description: "Una manzana",
            id: "1",
        },
        {
            name: "Pera",
            price: "$2.00",
            description: "Una pera",
            id: "2",
        },
        {
            name: "Naranja",
            price: "$3.00",
            description: "Una naranja",
            id: "3",
        },
    ];
  
  const objetoFruta = {
            name: "Manzana",
            price: "$1.00",
            description: "Una manzana",
            id: "1",
        }
</script>

<template>
  <!-- interpolacion -->
  <h1>Hola! {{ name }}</h1>

  <h2 :style="styleColor">Soy azul</h2>

  <h2 :style="`color:${arrayColor[0]}`">Texto en color de mi array</h2>

  <!-- Directivas IF-->
  
  <p v-if ='activo'> Estoy activo</p>
  <!-- <p v-else> Desactivo</p>  solo puede ir despues de un if-->
  <p v-else-if ='activo===false'> Desactivo</p>
  <p v-else>  No lo se</p>
  <p v-show="activo"> Muestra dimanica de vshow</p>

  <!-- Directivas FOR: se puede usar in u of-->
  <ul>
    <li 
      v-for="( fruta, index) in arrayFrutas" :key="index">
      {{index}} {{ fruta }}
    </li>
  </ul>

  <ul>
    <li
     v-for="value in arrayVerduras" :key="value">
     {{ value }}
    </li>
  </ul>

  <ul>
    <li
     v-for="(value, property) in objetoFruta" :key="value">
     {{ property }} : {{ value }}
    </li>
  </ul>
</template>

<style></style>