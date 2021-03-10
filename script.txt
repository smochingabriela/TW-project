window.onload= function()
{
   var theToggle = document.getElementById('toggle');

// hasClass
function hasClass(elem, className) {
	return new RegExp(' ' + className + ' ').test(' ' + elem.className + ' ');
}
// addClass
function addClass(elem, className) {
    if (!hasClass(elem, className)) {
    	elem.className += ' ' + className;
    }
}
// removeClass
function removeClass(elem, className) {
	var newClass = ' ' + elem.className.replace( /[\t\r\n]/g, ' ') + ' ';
	if (hasClass(elem, className)) {
        while (newClass.indexOf(' ' + className + ' ') >= 0 ) {
            newClass = newClass.replace(' ' + className + ' ', ' ');
        }
        elem.className = newClass.replace(/^\s+|\s+$/g, '');
    }
}
// toggleClass
function toggleClass(elem, className) {
	var newClass = ' ' + elem.className.replace( /[\t\r\n]/g, " " ) + ' ';
    if (hasClass(elem, className)) {
        while (newClass.indexOf(" " + className + " ") >= 0 ) {
            newClass = newClass.replace( " " + className + " " , " " );
        }
        elem.className = newClass.replace(/^\s+|\s+$/g, '');
    } else {
        elem.className += ' ' + className;
    }
}

theToggle.onclick = function() {
   toggleClass(this, 'on');
   return false;
}

  var vi=document.getElementById("Femei");
  var vi2=document.getElementById("Barbati");
  var hd=document.querySelector(".exfemei");
  var hd2=document.querySelector(".exbarbati");
  //alert(vi.src);
  vi.onclick= function()
      {  
        document.getElementById("Femei").src="https://i2.wp.com/blog.parfimo.ro/wp-content/uploads/1449429197-one.jpg?fit=710%2C444&ssl=1";
         var inp= document.createElement("input");
         inp.value = " ";
         hd.appendChild(inp)
         b1.onclick = function()
         {
          hd.removeChild(inp);
         }
         vi.onclick = null;
      }
      
 vi2.onclick= function()
      {  
         document.getElementById("Barbati").src="https://i2.wp.com/cristivasile.ro/wp-content/uploads/2018/10/parfjumerija-zhenskaja-novinki_12-1024x683-1024x685.jpg?resize=838%2C625";
         var inp= document.createElement("input");
         inp.value = " ";
         hd2.appendChild(inp)
         b2.onclick = function()
         {
          hd2.removeChild(inp);
         }         
         vi2.onclick = null;
      }

  function imageFun(){
      var image=document.getElementById("Femei");
      if(image.src.match("https://www.adevarulonline.ro/wp-content/uploads/2020/02/parfumuri-femei-750x375.jpg")){
        image.src="https://i2.wp.com/blog.parfimo.ro/wp-content/uploads/1449429197-one.jpg?fit=710%2C444&ssl=1"
      }
      else{
        image.src="https://www.adevarulonline.ro/wp-content/uploads/2020/02/parfumuri-femei-750x375.jpg"
      }}


}
//Get the button
var mybutton = document.getElementById("top");

// When the user scrolls down 20px from the top of the document, show the button
window.onscroll = function() {scrollFunction()};

function scrollFunction() {
  if (document.body.scrollTop > 20 || document.documentElement.scrollTop > 20) {
    mybutton.style.display = "block";
  } else {
    mybutton.style.display = "none";
  }
}

// When the user clicks on the button, scroll to the top of the document
function topFunction() {
  document.body.scrollTop = 0;
  document.documentElement.scrollTop = 0;
}

