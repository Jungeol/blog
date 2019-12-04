---
title: nodejs-express
tag: nodejs
category: nodejs
date: 2019-12-04 21:40:29
---
# Express
## hello world
```
var express = require("express");
var http = require("http");

var app = express();

//middle ware 1
app.use(function (request, response) {
    console.log("In comes a request to: " + request.url);
    response.end("Hello World!");
});
//middle ware 2
...
//middle ware 3
...

http.createServer(app).listen(3000);
//same as app.listen(3000);
```
## middleware
basic
```
app.use(function (req, res, next) {
    ...
    next();
});
```
error
```
app.use(function (err, req, res, next) {
    ...
    next();
});
```
### third party middleware
#### logger
```
...
var logger = require("morgan");
app.use(logger("short");
...
```
#### express.static
```
...
var path = require("path");
var publicPath = path.resolve(__dirname, "public");
app.use(express.static(publicPath));
...
```
#### etc
- connect-ratelimit
  - 시간당 특정 요청수 연결 조절
- Helmet
  - http 헤더를 추가해 앱을 특정 종류의 공격으로부터 더 안전하게
- cookie-parser
  - 브라우저 쿠키 분석
- response-time
  - X-Response-Time 헤더를 전송, 애플리케이션의 성능 디버깅 가능
- body-parser
  - 양식 제출할때 사용 등
- compression
  - 바이트를 줄이기위해 응답 압축
- connect-assets
  - CSS와 자바스크립트 자산을 컴파일하고 줄임
  - SASS, LESS, Stylus 등의 CSS 전처리기와 동작
## router
### basic
```
...
//basic
app.get("/about", function (request, response) {
    response.end("about");
});
//get variable, but not good
app.get("/hello/:who", function (request, response) {
    response.end("Hello, " + request.params.who + "!");
});
//regex pattern and get variable
app.get(/^\/users\/(\d+)$/, function (req, res) {
    var userId = parseInt(req.params[0], 10);
    ...
});
//get query
app.get("/search", function (req, res) {
    var b = req.query.q == "something like that";
});
...
```
### routes
app.js
```
var express = require("express");
var apiRouter = require("./routes/api_router");

var app = express();

app.use("/api", apiRouter);

app.listen(3000);
```
./routes/api_router.js
```
var express = require("express");

var api = express.Router();
api.use(function (req, res, next) {
    ...
    next();
});
api.get("/users", function (req, res) { ... });
api.post("/users", function (req, res) { ... });
api.get("/messages", function (req, res) { ... });
api.post("/messages", function (req, res) { ... });

module.exports = api;
```
## response extend
redirect
```
response.redirect("/some/path");
response.redirect("http://www.google.com/");
```
sendFile
```
response.sendFile("/path/to/some_file.txt");
```
json
```
response.json({ result: "blabla" });
```
crud
```
app.get("/", function (req, res) { ... });
app.post("/", function (req, res) { ... });
app.put("/", function (req, res) { ... });
app.delete("/", function (req, res) { ... });
```
send
```
app.send("message");
```
## ejs view
Ejs view setup
```
var express = require("express");
var path = require("path");

var app = express();

//view files in ./views
app.set("views", path.resolve(__dirname, "views));
//set use ejs
app.set("view engine", "ejs");
```
./views/footer.ejs
```
</body>
</html>
```
./views/index.ejs
```
<!DOCUMENT html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Hello, world!</title>
    </head>
<body>
<%= message =%>
<% include footer %>

```
View render
```
app.get("/", function (req, res) {
    response.render("index", {
        message: "Hello World!"
    });
});
```