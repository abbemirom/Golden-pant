<template>
<div class="about">
  <div class="om-header">Om Oss</div>

  <div>
  Våran hemsida riktar sig i huvudsak till lastbilschauförer - men är självklart menad för alla.
  Vi har försökt att göra det vi kan för att hemsidan ska vara så optimerad som möjlig för våra användare.
  På hemsidan kan du skrolla och kolla igenom böcker,
  samt beställa och köpa böcker genom att lägga de i din varukorg.
  Längre ner på sidan finns en karta som visar biblioteken du kan hämta ut eller köpa böckerna i din varukorg från.
  </div>
    <br>

<div class="staff">Anställda:</div>
<div class="staff-members">

<div class="staff-member">
  <img src="https://cdn.fakercloud.com/avatars/ganserene_128.jpg" class="bild">
  <div>Florence Stokes</div>
</div>

<div class="staff-member">
  <img src="https://cdn.fakercloud.com/avatars/bublienko_128.jpg" class="bild">
  <div>Kate Bode</div>
</div>

<div class="staff-member">
  <img src="https://cdn.fakercloud.com/avatars/calebjoyce_128.jpg" class="bild">
  <div>Jeton Mustini</div>
</div>

<div class="staff-member">
  <img src="https://cdn.fakercloud.com/avatars/gmourier_128.jpg" class="bild">
  <div>Joakim Flink</div>
</div>

<div class="staff-member">
  <img src="https://cdn.fakercloud.com/avatars/sindresorhus_128.jpg" class="bild">
  <div>Carlos Corwin</div>
</div>
</div>

<NuxtLink to="/"> Till startsida</NuxtLink>
  </div>
</template>

<script>
export default {

}
</script>

<style>
.om-header, .staff {
 font-weight: bold;
 font-size: 160%;
}

.about {
  padding: 10px;
  font-size: 120%;
}

.about:hover {
  cursor: default;
}

.staff-members{
	display: flex;
	flex-direction: row;
	flex-wrap: nowrap;
	justify-content: space-evenly;
	align-items: center;
	align-content: space-between;
}

.staff-member {
  padding: 2%;
}

.bild {
  border-radius: 15px;
  border: solid black 4px;
}
</style>
