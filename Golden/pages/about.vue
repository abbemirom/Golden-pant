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
  <img src="https://filetandvine.com/wp-content/uploads/2015/11/buddy-placeholder-vertical.jpg" class="bild">
  <div>Emilia Romberg</div>
</div>

<div class="staff-member">
  <img src="https://filetandvine.com/wp-content/uploads/2015/11/buddy-placeholder-vertical.jpg" class="bild">
  <div>Lucas Olofsson</div>
</div>

<div class="staff-member">
  <img src="https://filetandvine.com/wp-content/uploads/2015/11/buddy-placeholder-vertical.jpg" class="bild">
  <div>Oliver Ottosson</div>
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
