# JsForm
JsForm

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Send Email</title>
</head>
<body>
  <form method="post" name="Form">
    <p><input type="Email" id="sender" placeholder="sender@gmail.com"></p>
    <p><input type="Email" id="reciever" placeholder="Reciever@gmail.com"></p>
    <p><input type="text" id="content" placeholder="Enter Email Content" id="Message"></p>
    <p><input type="button" value="Send Email" onclick="sendMail()"></p>
  </form>

<script src="http://smtpjs.com/v3/smtp.js"></script>

<script type="text/javascript">
    getData = (elemId) => {
      //getting values from input fields
      return document.getElementById(elemId).value;
    }
    sendMail = () => {
      var sender = getData("sender");
      var receiver = getData("reciever");
      var content = getData("content");
 
      //Sending email
      Email.send({
        Host: "smtp.gmail.com",
        Username: "youremail@gmail.com",
        Password:"anandksdjdsihun",
        To: receiver,
        From: sender,
        Subject: "Check Email Sending",
        Body: content,
      }).then(function (message) {
        alert("Email sent successfully")
      });
    } 
  </script>
</body>
</html>
