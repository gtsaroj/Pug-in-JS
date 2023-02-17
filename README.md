# Pug-in-JS
const express = require(`express`);
const app = express();

const path = require('path');
const port = 80;

app.use(`/static`, express.static(`static`))

// set the pug
app.set('view engine', 'pug');

// view the directory as pug
app.set('views', path.join(__dirname,'views'));

// Our pug views end point
app.get('/', (req, res)=>{
    const con = "This is about coronavirus";
    const params ={'title':'CORONAVIRUS', content:con};
    res.status(200).render('index.pug', params);
})



// server start
 app.listen(port, ()=>{
    console.log(`The application is started at port ${port}`);
 });
