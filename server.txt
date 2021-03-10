var http = require('http');
var url = require('url');
var fs = require('fs');


var server=http.createServer(function (req, res) 
{
  console.log("cerere");
	var objURL=url.parse(req.url,true);
  console.log(objURL);
  if(objURL=='/submit')
  {
    let queryU=objURL.query;
    let date=JSON.stringify({salutation: queryU.salutation, name: queryU.name, email: queryU.email, review: queryU.review});
    console.log("formular",date);
    fs.writeFileSync('form.json',date);
    res.writeHead(200, {'Content-Type': 'text/plain'});
    res.end();
  }
  if(objURL.pathname=='/')
  {
    fs.readFileSync('./index.html',function(err,html)
    {
      if(err){
        res.end(500,{error: err});
      }
      res.writeHeader(200,{"Content-Type": "text/html"});
      res.write(html);
      res.end();
    });
  }
  fs.writeFileSync("formular/form.json",date);
}).listen(3100);
console.log('Serverul asteapta cereri de la http://localhost:3100/');

  

