<!DOCTYPE html>
<html>
    <head lang="en">
         <!-- Required meta tags -->
         <meta charset="utf-8">
         <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
 
         <!-- Bootstrap CSS -->
         <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384-ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
         <!-- Optional JavaScript -->
         <!-- jQuery first, then Popper.js, then Bootstrap JS -->
         <!-- jQuery first, then Popper.js, then Bootstrap JS -->
         <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
         <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
         <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
         <script src="https://code.jquery.com/jquery-3.6.0.js"></script>
         <script src="js/fsd7.js"></script>        
         <link rel="stylesheet" href="css/fsd7.css">
    </head>
    <body onload="hideform();">
        <center>
            <h3>ENQUIRY FORM</h3>
            <button type="button" id="formshow" class="btn btn-danger" value="Open Form">
                Open Form
            </button>
            <button type="button" id="formhide" class="btn btn-danger" value="hide Form">
                Close Form
            </button>
        </center>
        <div class="container" id="formid">
            <form id="studentform" onsubmit="return submitjs();" name="student_form">
                <div class="form-row">
                    <div class="form-group col-md-6">
                      <label for="inputfname">Name: </label>
                      <input type="text" onblur="blurjs(this);" onfocus="focusjs(this);" class="form-control" id="inputfname" placeholder="Enter name here" required>
                      <p id="spanfirstname"></p>
                      <p id="spanfirstname2"></p>
                    </div>
                   
                </div>
                <div class="form-row">
                    <div class="form-group col-md-6">
                        <label for="inputnumber">Number: </label>
                        <input type="number" onblur="blurjs(this);myguardiansname();" onfocus="focusjs(this);" class="form-control" id="inputnumber" placeholder="Enter Number here" required>
                        <p id="spanguardian"></p>
                </div>
                </div>
              
                <div class="form-row">
                  <div class="form-group col-md-6">
                    <label for="inputEmail4">Email:</label>
                    <input type="email" onblur="blurjs(this);" onfocus="focusjs(this);fillmail();" class="form-control" id="inputEmail4" placeholder="Email">
                  </div>
                </div>
                
                
                
                
            
                  <div class="form-group ">
                    <label for="inputEnquiry">Enquiry: </label>
                    <input type="text" onblur="blurjs(this);" onfocus="focusjs(this);" class="form-control" id="text" required>
                    <span id="spanzipy"></span>
                  </div>
                
                
                <div class="form-group">
                 
                </div>
                <button type="submit" class="btn btn-dark">Submit Enquiry</button>
              </form>  
        </div>
        <style>
            #studentform{
                padding: 100px 50px 100px 50px;
            }

            body{
                background-color:rgb(255, 209, 4);
                padding-top:70px;
            }

            .container{
                margin-top: 20px;
                margin-bottom: 20px;
                background-color:rgb(0, 0, 0);
                color: cornsilk;
            }
            .jumbotron1{
                margin:25px;
                padding:25px;
                background-color: orange;
                font-size: x-large;
                text-align: center;
            }
            .jumbotron2{
                margin:25px;
                padding:25px;
                background-color:aliceblue;
                font-size: x-large;
                text-align: center;
            }
        </style>
        <script>
            function fillmail()
            {
                var y = document.forms["student_form"]["inputfname"].value; 
                var z = document.forms["student_form"]["inputlname"].value;
                if(y == "" && z==""){
                    var mail= "";
                }
                else
                {
                    var mail= y+z+"@gmail.com";
                }
                document.getElementById("inputEmail4").value = mail;
            }

            function focusjs(x)
            {
                x.style.color = "white";
                x.style.backgroundColor="black";
            }

            function blurjs(x)
            {
                x.style.color = "black";
                x.style.backgroundColor="white";
            }

            function submitjs()
            {
                alert("ENQUIRY SUCCESSFUL!");
                return true;
            }

            // Form Validation


            $(document).ready(function(){
                $('#formid').hide();
                $('#formshow').click(function(){
                    $('#formid').animate({
                        height:"toggle"

                    },1000,function(){});
                    console.log("hello");
                });
                $('#formhide').click(function(){
                    $("#formid").hide('slow');
                    console.log("hi");
                });
                $("#inputfname").change(function(){
                    var x = $("#inputfname").val();
                    var letters = /^[A-Za-z]+$/;
                    if(!(letters.test(x)) || x.length==0)
                    {
                        $("#spanfirstname").replaceWith("<span id='spanfirstname' style='color:red'> Alphabets Only </span>");
                    }
                    else{
                        $("#spanfirstname").replaceWith("<span id='spanfirstname' style='color:green'> Input Accepted </span>"); 
                    }
                });
                $("#inputlname").change(function(){
                    var x = $("#inputlname").val();
                    var letters = /^[A-Za-z]+$/;
                    if(!(letters.test(x)) || x.length==0)
                    {
                        $("#spanlastname").replaceWith("<span id='spanlastname' style='color:red'> Alphabets Only </span>");
                    }
                    else{
                        $("#spanlastname").replaceWith("<span id='spanlastname' style='color:green'> Input Accepted </span>"); 
                    }
                });
                $("#inputGuardian").change(function(){
                    var x = $("#inputGuardian").val();
                    var letters = /^[A-Za-z]+$/;
                    if(!(letters.test(x)) || x.length==0)
                    {
                        $("#spanguardian").replaceWith("<span id='spanguardian' style='color:red'> Alphabets Only </span>");
                    }
                    else{
                        $("#spanguardian").replaceWith("<span id='spanguardian' style='color:green'> Input Accepted </span>"); 
                    }
                });
                $("#inputnumber").change(function(){
                    a = document.getElementById("inputnumber").value;
                    if (isNaN(a))
                    { 
                        $("#spancontactnumber").replaceWith("<span id='spancontactnumber' style='color:red'> Numbers Only </span>");
                    }
                    else if (a.length>10)
                    {
                        $("#spancontactnumber").replaceWith("<span id='spancontactnumber' style='color:red'> Max 10 Numbers Only </span>");
                    }
                    else if (a.length<10) 
                    {
                        $("#spancontactnumber").replaceWith("<span id='spancontactnumber' style='color:red'> Min 10 Numbers Only </span>");
                    }
                    else
                    {
                        $("#spancontactnumber").replaceWith("<span id='spancontactnumber' style='color:green'> Input Accepted </span>");
                    }
                });
                $("#inputage").change(function(){
                    a = document.getElementById("inputage").value;
                    if (isNaN(a))
                    { 
                        $("#spanage").replaceWith("<span id='spanage' style='color:red'> Numbers Only </span>");
                    }
                    else
                    {
                        $("#spanage").replaceWith("<span id='spanage' style='color:green'> Input Accepted </span>");
                    }
                });
                $("#inputCity").change(function(){
                    var x = $("#inputCity").val();
                    var letters = /^[A-Za-z]+$/;
                    if(!(letters.test(x)) || x.length==0)
                    {
                        $("#spancity").replaceWith("<span id='spancity' style='color:red'> Alphabets Only </span>");
                    }
                    else{
                        $("#spancity").replaceWith("<span id='spancity' style='color:green'> Input Accepted </span>"); 
                    }
                });
                $("#inputZip").change(function(){
                    a = document.getElementById("inputZip").value;
                    if (isNaN(a))
                    { 
                        $("#spanzipy").replaceWith("<span id='spanzipy' style='color:red'> Numbers Only </span>");
                    }
                    else
                    {
                        $("#spanzipy").replaceWith("<span id='spanzipy' style='color:green'> Input Accepted </span>");
                    }
                });
                
            });
        </script>
    </body>
</html>
