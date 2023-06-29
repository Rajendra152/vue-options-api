<script>
export default {
  name: "App",
  data() {
    return {
      greet: 'Hello',
      name: "Rajendra",
      org: 'Innominds',
      emp: '<b>6151</b>',
      headingId: 'heading',
      isDisabled: true,
      status: 'danger',
      isPromoted: true,
      isSoldOut: true,
      highlightColor: 'orange',
      headerSize: 50,
      headerStyleObject: {
        color: 'orange',
        fontSize: '50px',
        padding: '20px',
      },
      baseStyleObject: {
        fontSize: '50px',
        padding: '10px',
      },
      successStyleObject: {
        color: 'green',
        backgroundColor: 'lightgreen',
        border: '1px solid green',
        padding: '20px',
      },
      dangerStyleObject: {
        color: 'darkred',
        backgroundColor: 'red',
        border: '1px solid darkred',
      }
    };
  },
};
</script>

<template>
<div>

<!-- This is the mustache way of binding text which is preferred -->
<p>{{greet}} {{ name }} Whatsup?</p>

<!-- v-text directive  is another way of binding text which is not preferably used -->
<!-- It will overwrite the text which is already present in between templates -->
<p v-text="org"></p>     

<!-- v-html used for binding bold/italic html elements in script -->
<div v-html="emp"></div>

<!-- we can bind attributes using  or simply using the :  -->
<h2 :id="headingId">Heading</h2>
<button :disabled= "isDisabled">click</button>

<h4 class='underline'>I have been underlined</h4>

<h2 class='underline' :class="status">Status</h2>

<h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>

<h2 :class="isSoldOut ? 'sold-out' : 'new'">Soldout? movie</h2>

<h2 :class="['new','promoted' ]">Newly promoted Movie</h2>

<h2 :class="[isPromoted && 'promoted',isSoldOut ? 'sold-out' : 'new' ]">Array conditional Movie</h2>

<h2 :class="{
  promoted: isPromoted,
  new: !isSoldOut,
  'sold-out': isSoldOut,
}">Object conditional Movie</h2>

<h2 :style="{
  color:highlightColor,
  'font-size': headerSize + 'px', //can also use camelCase fontSize
  padding: '20px'
}">Inline Style</h2>

<h2 :style="headerStyleObject">Style Object</h2>

<h2 :style="[baseStyleObject, successStyleObject]">Success Style</h2>
<h2 :style="[baseStyleObject, dangerStyleObject]">Danger Style</h2>
</div>
</template>



<style>
.underline{
  text-decoration: underline;
}

.promoted{
  font-style: italic;
}

.new {
  color: green;
}

.sold-out{
  color: red;
}
</style>
