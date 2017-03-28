function formValidation() // function written for validation
{  
var uid = document.registration.userid;//userid variable declaration  
var passid = document.registration.passid;//passid variable declaration  
var uname = document.registration.username;//useranme variable declaration  
var uadd = document.registration.address;//uadd variable declaration  
var ucountry = document.registration.country;//ucountry variable declaration  
var uzip = document.registration.zip;//uzip variable declaration  
var uemail = document.registration.email;//uemail variable declaration  
var umsex = document.registration.msex;//usexfemale variable declaration  
var ufsex = document.registration.fsex; if(userid_validation(uid,5,12))//usexmale variable declaration  
{  
if(passid_validation(passid,7,12))  
{  
if(allLetter(uname))  
{  
if(alphanumeric(uadd))  
{   
if(countryselect(ucountry))  
{  
if(allnumeric(uzip))  
{  
if(ValidateEmail(uemail))  
{  
if(validsex(umsex,ufsex))  
{  
}  
}   
}  
}   
}  
}  
}  
}  
return false;  
  
} function userid_validation(uid,mx,my)  
{  
var uid_len = uid.value.length;  
if (uid_len == 0 || uid_len >= my || uid_len < mx)  
{  
alert("User Id should not be empty / length be between "+mx+" to "+my);  
uid.focus();  
return false;  
}  
return true;  
}  
function passid_validation(passid,mx,my)  
{  
var passid_len = passid.value.length;  
if (passid_len == 0 ||passid_len >= my || passid_len < mx)  
{  
alert("Password should not be empty / length be between "+mx+" to "+my);  
passid.focus();  
return false;  
}  
return true;  
}  
function allLetter(uname) //function for username restriction
{   
var letters = /^[A-Za-z]+$/;  
if(uname.value.match(letters))  
{  
return true;  
}  
else  
{  
alert('Username must have alphabet characters only');  
uname.focus();  
return false;  
}  
}  
function alphanumeric(uadd)  
{   
var letters = /^[0-9a-zA-Z]+$/;  
if(uadd.value.match(letters))  
{  
return true;  
}  
else  
{  
alert('User address must have alphanumeric characters only'); //alert boxes for user authentication
uadd.focus();  
return false;  
}  
}  
function countryselect(ucountry) // country selection 
{  
if(ucountry.value == "Default")  
{  
alert('Select your country from the list'); //alert boxes for country authentication
ucountry.focus();//hover country  
return false;  
}  
else  
{  
return true;  
}  
}  
function allnumeric(uzip)// function for numerical only zip code 
{   
var numbers = /^[0-9]+$/;  
if(uzip.value.match(numbers))  
{  
return true;  
}  
else  
{  
alert('ZIP code must have numeric characters only');// alert boxes for zip code   
uzip.focus();  
return false;  
}  
}  
function ValidateEmail(uemail)// function for email validation  
{  
var mailformat = /^\w+([\.-]?\w+)*@\w+([\.-]?\w+)*(\.\w{2,3})+$/;  
if(uemail.value.match(mailformat)) // condition for email validation
{  
return true;  
}  
else  
{  
alert("You have entered an invalid email address!");// alert boxes for email validation  
uemail.focus();  
return false;  
}  
} function validsex(umsex,ufsex)// function for gender validation  
{  
x=0;  
  
if(umsex.checked)// condition1   
{  
x++;  
} if(ufsex.checked)// condition2  
{  
x++;   
}  
if(x==0)  
{  
alert('Select Male/Female');//  
umsex.focus();  
return false;  
}  
else  
{  
alert('Form Succesfully Submitted');  
window.location.reload()  
return true;  
}  
}  