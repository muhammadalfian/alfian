<!DOCTYPE HTML>

<html>
	<head>
		<title>D-Light</title>
		<meta http-equiv="content-type" content="text/html; charset=utf-8" />
		<meta name="description" content="" />
		<meta name="keywords" content="" />
		<link href="http://fonts.googleapis.com/css?family=Source+Sans+Pro:300,400,600,300italic" rel="stylesheet" type="text/css" />
		<!--[if lte IE 8]><script src="css/ie/html5shiv.js"></script><![endif]-->
		<script src="js/jquery.min.js"></script>
		<script src="js/jquery.poptrox.min.js"></script>
		<script src="js/skel.min.js"></script>
		<script src="js/init.js"></script>
		<noscript>
			<link rel="stylesheet" href="css/skel-noscript.css" />
			<link rel="stylesheet" href="css/style.css" />
		</noscript>
		<!--[if lte IE 8]><link rel="stylesheet" href="css/ie/v8.css" /><![endif]-->
		<style type="text/css">
.button1 {
    background-color: #009933;
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    outline: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
    cursor: pointer;
    border: none;
    border-radius: 15px;
    -webkit-transition-duration: 0.4s;
    transition-duration: 0.4s;
    position: absolute;
    left: 28.5%;
    top: 60%;
    width: 20%;
    text-align: center;
    font-size: 18px;
}
.button2 {

    background-color: #991f00;
    border: none;
    color: white;
    padding: 15px 32px;
    text-align: center;
    text-decoration: none;
    outline: none;
    display: inline-block;
    font-size: 16px;
    margin: 4px 2px;
	cursor: pointer;
    border: none;
    border-radius: 15px;
    -webkit-transition-duration: 0.4s;
    transition-duration: 0.4s;
    position: absolute;
    left: 51.5%;
    top: 60%;
    width: 20%;
    text-align: center;
    font-size: 18px;
}
.button1:hover {
    box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24),0 17px 50px 0 rgba(0,0,0,0.19);
    background-color: #00802b;
}
.button1:active {
    background-color: #00802b;
    box-shadow: 0 5px #666;
    transform: translateY(4px);
}
.button2:hover {
    box-shadow: 0 12px 16px 0 rgba(0,0,0,0.24),0 17px 50px 0 rgba(0,0,0,0.19);
    background-color: #801a00;
}
.button2:active {
    background-color: #801a00;
    box-shadow: 0 5px #666;
    transform: translateY(4px);
}
		</style>
	</head>
	<body>

		<!-- Header -->
			<!-- Header -->
      <section id="header">
        <header>
          <h1> D-Light</h1>
          <p>By Arkademy</p>
        </header>
      </section>
    <button onclick="On()" class="button1">ON</button>
    <button onclick="Off()" class="button2">OFF</button>
    <script>
          function On(){
            $.ajax({
              url:'https://api.arkademy.com:8443/v0/arkana/device/IO/percobaan/gpio/control',
              type : 'POST',
              headers : {
                'accept' : 'application/json',
                'content-type' : 'application/json',
                'authorization' : 'Bearer NDQ4NTcwMzIxNC4zOTgxMDY6'
              },
              data : '{"controls":{"4":1,"5":1}}' , //data yang dikirimkan harus dalam STRING
              success:function(response){
                       //konversi dari javascript object ke string agar bisa di print
                        var string_response=JSON.stringify(response);
                        //variabel response berisi data response dari API
                        alert(string_response);
              },
              error:function(err){
               //variabel err berisi data error dari API (404,401,400,500)
               alert("error!",err);
              }
            });
          }
          function Off(){
            $.ajax({
              url:'https://api.arkademy.com:8443/v0/arkana/device/IO/percobaan/gpio/control',
              type : 'POST',
              headers : {
                'accept' : 'application/json',
                'content-type' : 'application/json',
                'authorization' : 'Bearer NDQ4NTcwMzIxNC4zOTgxMDY6'
              },
              data : '{"controls":{"4":0,"5":0}}' , //data yang dikirimkan harus dalam STRING
              success:function(response){
                       //konversi dari javascript object ke string agar bisa di print
                        var string_response=JSON.stringify(response);
                        //variabel response berisi data response dari API
                        alert(string_response);
              },
              error:function(err){
               //variabel err berisi data error dari API (404,401,400,500)
               alert("error!",err);
              }
            });
          }
    </script>
	</body>
</html>
