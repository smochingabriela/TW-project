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
}

 document.getElementById("try").addEventListener("click", 
    function(){ 
        document.getElementById("text1").innerText = "de la 174 lei";
        document.getElementById("text2").innerText = "de la 135 lei";
        document.getElementById("text3").innerText = "de la 72 lei";
        document.getElementById("text4").innerText = "de la 298 lei";
        document.getElementById("text5").innerText = "de la 254 lei";
        document.getElementById("text6").innerText = "de la 75 lei";
        document.getElementById("text7").innerText = "de la 210 lei";
        document.getElementById("text8").innerText = "de la 232 lei";
        document.getElementById("text9").innerText = "de la 226 lei";
        document.getElementById("text10").innerText = "de la 150 lei";
        document.getElementById("text11").innerText = "de la 239 lei";
        document.getElementById("text12").innerText = "de la 201 lei";
        document.getElementById("text13").innerText = "de la 205 lei";
        document.getElementById("text14").innerText = "de la 343 lei";
        document.getElementById("text15").innerText = "de la 87 lei";});  
    
  


startday = new Date();
clockStart = startday.getTime();
function initStopwatch() {
var myTime = new Date();
return((myTime.getTime() - clockStart)/1000);
}
function getSecs() {
    var tSecs = Math.round(initStopwatch());
    var iSecs = tSecs % 60;
    var iMins = Math.round((tSecs-30)/60);
    var sSecs ="" + ((iSecs > 9) ? iSecs : "0" + iSecs);
    var sMins ="" + ((iMins > 9) ? iMins : "0" + iMins);
    document.getElementById("timespent").value = sMins+":"+sSecs;
    return this;
    
}
var idVar = setInterval(() => {
	getSecs()
}, 1000);
function myStopFunction() {
	clearInterval(idVar);
}