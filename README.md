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
--------------------------------------------------------



<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>Send Mail</title>
    <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
    <script src="https://smtpjs.com/v3/smtp.js"></script>
</head>
<body>
    <h3> Send Email using Javascript</h3>
    <form action="#" method="post">
        <label for="name">Your Name</label>
        <input type="text" id="name" placeholder="Enter Name"> <br>
        <label for="email">Email</label>
        <input type="email" id="email" placeholder="Enter Email"> <br>
        <label for="message">Message</label>
        <textarea  id="message" placeholder="Enter Message" rows="3"> </textarea>  <br>

        <button type="submit" id="submit" onclick="sendEmail()"> Send Email </button>
    </form>
     <div id="response"></div>
</body>


<script>  
function sendEmail() {
    let name = document.getElementById("name").value;
    let email = document.getElementById("email").value;
    let message = document.getElementById("message").value;
    let finalmessage = `Name : ${name} <br>  Email : ${email} <br>  Message : ${message} <br>`;

    Email.send({
        Host : "smtp.mailtrap.io",
        Username : "username",
        Password : "password",
        To : 'them@website.com',
        From : "you@isp.com",
        Subject : "Mail from website",
        Body : finalmessage
    }).then(
      message => alert(message)
    );
}
</script>


</html>
----------------------------------------------------

<!DOCTYPE html> 
<html> 

<head> 
<title>Send Mail</title> 
<script src= 
	"https://smtpjs.com/v3/smtp.js"> 
</script> 

<script type="text/javascript"> 
	function sendEmail() { 
	Email.send({ 
		Host: "smtp.gmail.com", 
		Username: "sender@email_address.com", 
		Password: "Enter your password", 
		To: 'receiver@email_address.com', 
		From: "sender@email_address.com", 
		Subject: "Sending Email using javascript", 
		Body: "Well that was easy!!", 
	}) 
		.then(function (message) { 
		alert("mail sent successfully") 
		}); 
	} 
</script> 
</head> 

<body> 
<form method="post"> 
	<input type="button" value="Send Email"
		onclick="sendEmail()" /> 
</form> 
</body> 

</html> 
