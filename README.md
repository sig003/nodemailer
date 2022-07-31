# nodemailer
nodemailer sample

```
const express = require('express');
const request = require('request');
const fs = require('fs');
const nodemailer = require('nodemailer');

const app = express();

app.get('/', (req, res) => {
   const transporter = nodemailer.createTransport({
      service: 'Naver',
      prot: 587,
      host: 'smtp.naver.com',  
      secure: false,  
      requireTLS: true ,
      auth: {
        user: 'naverEmail',
        pass: 'naverPassword'
      }
    });
  
    const mailOptions = {
      from: 'fromEmail',
      to: 'toEmail',
      subject: 'test',
      text: 'hello'
    };
      
    transporter.sendMail(mailOptions, function (error, info) {
      if (error) {
        console.log(error);
      } else {
        console.log('Email sent: ' + info.response);
      }
    });
});


app.listen(3000, () => {
        console.log('ready server');
});
```   
   
   ### Tip 
   fs module is required using nodejs or react
   
   ## References
   [https://velog.io/@jiwon/-Nodemailer로-인증-관련-이메일-보내기-d4k4pqoot4](https://velog.io/@jiwon/-Nodemailer%EB%A1%9C-%EC%9D%B8%EC%A6%9D-%EA%B4%80%EB%A0%A8-%EC%9D%B4%EB%A9%94%EC%9D%BC-%EB%B3%B4%EB%82%B4%EA%B8%B0-d4k4pqoot4)

[https://devlog-wjdrbs96.tistory.com/234](https://devlog-wjdrbs96.tistory.com/234)

