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
        document.getElementById("text1").innerText = "de la 178 lei";
        document.getElementById("text2").innerText = "de la 139 lei";
        document.getElementById("text3").innerText = "de la 200 lei";
        document.getElementById("text4").innerText = "de la 212 lei";
        document.getElementById("text5").innerText = "de la 234 lei";
        document.getElementById("text6").innerText = "de la 244 lei";
        document.getElementById("text7").innerText = "de la 168 lei";
        document.getElementById("text8").innerText = "de la 259 lei";
        document.getElementById("text9").innerText = "de la 78 lei";
        document.getElementById("text10").innerText = "de la 108 lei";
        document.getElementById("text11").innerText = "de la 118 lei";
        document.getElementById("text12").innerText = "de la 105 lei";
        document.getElementById("text13").innerText = "de la 274 lei";
        document.getElementById("text14").innerText = "de la 205 lei";
        document.getElementById("text15").innerText = "de la 397 lei";});  
    
  


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