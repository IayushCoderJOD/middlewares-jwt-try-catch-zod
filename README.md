# middlewares-jwt-try-catch-zod


const express = require("express");

const app = express();

function ticketChecker(req, res, next) {
  const ticket = req.query.age;
  if (ticket >=14) {
    next();
  } else {
    res.status(300).send("Access denied");
  }
}

app.use(ticketChecker);

app.get("/ride1", (req, res) => {
  res.send("you rode the first ride");
});

app.get("/ride2", (req, res) => {
  res.send("you rode the second ride");
});

app.get("/ride3", (req, res) => {
  res.send("you rode the third ride");
});

app.listen(3000);

const jwt = require("jsonwebtoken");

// generating, decoding, verifying

const value = {
  name: "Ayush",
  account: "123321",
};

// 1. Generating

try {
  const token = jwt.verify(
    "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJuYW1lIjoiQXl1c2giLCJhY2NvdW50IjoiMTIzMzIxIiwiaWF0IjoxNzA5ODg2NDI1fQ.mCZrXZxAzgViBtAynXA5xTaaVYhGOV13K-OyIO9aUMo",
    "Secret ",
  );

  console.log(token);
} catch (error) {
  console.log("abe bsdk nikal");
}



understanding try catch

function getLength(name){
  return name.length;
}
try{
const ans=getLength();
console.log(ans)
}catch(err){
  console.log(err)
}
console.log(
  "this to har halat me run"
)
