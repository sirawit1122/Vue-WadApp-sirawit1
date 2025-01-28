<!--สำหรับการแสดงผล-->
<template>
 <div>
   <ul>   
     <li><a href="#home">Home</a></li>
     <li><a href="#mycard">my card</a> </li>
     <li><a href="#about">About</a></li>
   </ul>
 </div>

</template>
<!--สำหรับเขียน java script เพื่อควบคุมการทำงานของ Component
 เช่น การกำหนด  data,methode เป็นต้น-->
<script>
export default {
    }
</script>
<!--ส่วนสำหรับเขียน css เพื่อตกแต่ง template-->
<style>
ul {
   list-style-type: none;
   margin: 0;
   padding: 0;
   overflow: hidden;
   background-color: #f3eaea;
}

li {
    float: left;
}

li {
    display: block;
    color: white;
    text-align: center;
    padding: 14px 16px;
    text-decoration: none;
}

/* Change the link color to #111 (black) on hover */
li a:hover {
    background-color: #c29d9d;
}
</style>