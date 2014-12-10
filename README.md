VBD
===

Project On Virtual Blood Donation

//Registration.jsp
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Virtual Blood Donation</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="">
  <meta name="author" content="">

  
	<!--link rel="stylesheet/less" href="less/bootstrap.less" type="text/css" /-->
	<!--link rel="stylesheet/less" href="less/responsive.less" type="text/css" /-->
	<!--script src="js/less-1.3.3.min.js"></script-->
	<!--append â#!watchâ to the browser URL, then refresh the page. -->
	
	<link href="css/bootstrap.min.css" rel="stylesheet">
	<link href="css/style.css" rel="stylesheet">
	</head>



<body background-color="00000">
<div class="container">

	<div class="row clearfix">
		<div class="col-md-12 column">
			<nav class="navbar navbar-inverse" role="navigation">
				<div class="navbar-header">
					 <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1"> <span class="sr-only">Toggle navigation</span><span class="icon-bar"></span><span class="icon-bar"></span><span class="icon-bar"></span></button> <a class="navbar-brand active" href="index.html">Home</a>
				</div>
				
				<div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
					<ul class="nav navbar-nav">
					
						<li>
							<a href="about.jsp">ABOUT US</a>
						</li>
						
					</ul>
					<form class="navbar-form navbar-left" role="search">
						<div class="form-group">
							<input class="form-control" type="text">
						</div> <button type="submit" class="btn btn-default">Submit</button>
					</form>
					<ul class="nav navbar-nav navbar-right">
						<li>
							<a href="login.jsp">LOGIN</a>
						</li>
						<li>
							<a href="reg3.jsp"> REGISTRATION</a>
						</li>
						<li>
							<a href="contactb.html">CONTACT US</a>
						</li>
						
					</ul>
				</div>
				</nav>
				</div>
				</div>
				</div>
<%@ page import ="java.sql.*" import="java.util.*" import="java.util.Date" import ="java.text.SimpleDateFormat" %>
<%  String fname = request.getParameter("fname");
    String gen=request.getParameter("gender"); 
    String blood=request.getParameter("blood");
    String dob=request.getParameter("dob");
    //java.sql.Date date=new java.sql.Date(0000-00-00);
    //SimpleDateFormat formatter = new SimpleDateFormat("yyyy-MM-dd");
    //Date date = formatter.parse(dob);
   //Date date = new SimpleDateFormat("yyyy-MM-dd").parse(dob);
  //SimpleDateFormat formatter ;
  //formatter = new SimpleDateFormat("yyyy-MM-dd");
  //Date date=formatter.parse(request.getParameter("dob"));    
    Long mobile=Long.parseLong(request.getParameter("number"));
    String country= request.getParameter("select0");
    String state= request.getParameter("select1");
    String dist= request.getParameter("select2");
    String city= request.getParameter("select3");
    String email = request.getParameter("email");
    String pwd = request.getParameter("pass");
    String cpwd = request.getParameter("cpass");
    String c1 = request.getParameter("tos");
    String c2=request.getParameter("tos1");
    String c3=request.getParameter("tos2");
    String loc=request.getParameter("location");
    Class.forName("com.mysql.jdbc.Driver");
    Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/synergy",
            "root", "santu");
    Statement st = con.createStatement();
    //ResultSet rs;
    int i = st.executeUpdate("insert into register(fname,gen,blood,dob,mobile,country,state,dist,city,email,pwd,cpwd,c1,c2,c3,location) values ('" + fname + "','" + gen + "','"+ blood+ "','" + dob+ "','" + mobile + "','" + country + "','" + state + "','" + dist + "','" + city + "','" + email + "','" + pwd + "', '" + cpwd + "','" +c1 + "','" + c2 + "','" + c3+ "','"+loc+"')");
    if (i > 0)
   {
        //session.setAttribute("userid", user);
        response.sendRedirect("welcome.jsp");
       // out.print("Registration Successfull!"+"<a href='index.jsp'>Go to Login</a>");
    } else 
 {
        response.sendRedirect("index.jsp");
 }

%>
</body>
</html>

//RequestBlood.jsp
<%@ page contentType="text/html; charset=iso-8859-1" language="java" %>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Virtual Blood Donation</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="">
  <meta name="author" content="">

  
	<!--link rel="stylesheet/less" href="less/bootstrap.less" type="text/css" /-->
	<!--link rel="stylesheet/less" href="less/responsive.less" type="text/css" /-->
	<!--script src="js/less-1.3.3.min.js"></script-->
	<!--append â#!watchâ to the browser URL, then refresh the page. -->
	
	<link href="css/bootstrap.min.css" rel="stylesheet">
	<link href="css/style.css" rel="stylesheet">
	</head>



<body background-color="00000">
<div class="container">

	<div class="row clearfix">
		<div class="col-md-12 column">
			<nav class="navbar navbar-inverse" role="navigation">
				<div class="navbar-header">
					 <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1"> <span class="sr-only">Toggle navigation</span><span class="icon-bar"></span><span class="icon-bar"></span><span class="icon-bar"></span></button> <a class="navbar-brand active" href="index.html">Home</a>
				</div>
				
				<div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
					<ul class="nav navbar-nav">
					
						<li>
							<a href="about.jsp">ABOUT US</a>
						</li>
						
					</ul>
					<form class="navbar-form navbar-left" role="search">
						<div class="form-group">
							<input class="form-control" type="text">
						</div> <button type="submit" class="btn btn-default">Submit</button>
					</form>
					<ul class="nav navbar-nav navbar-right">
						<li>
							<a href="login.jsp">LOGIN</a>
						</li>
						<li>
							<a href="reg3.jsp"> REGISTRATION</a>
						</li>
						<li>
							<a href="contactb.html">CONTACT US</a>
						</li>
						
					</ul>
				</div>
			</nav>
		</div>
	</div>
	</div>
<%@ page import="java.util.*" %>
<%@ page import="javax.mail.*" %>
<%@ page import="javax.mail.internet.*" %>
<%@ page import="javax.activation.*" %>
<%@ page import="javax.net.ssl.*" %>
<%@ page import="java.sql.*" %>
<%
	String email1=request.getParameter("email");
	Long mobile1=Long.parseLong(request.getParameter("number"));
	int units=Integer.parseInt(request.getParameter("sel"));
	int r=(int)(Math.random()*9000)+1000;
	int r1=(int)(Math.random()*90000)+10000;
	Class.forName("com.mysql.jdbc.Driver");
	Connection con3=DriverManager.getConnection("jdbc:mysql://localhost:3306/synergy","root","santu");
	Statement st3=con3.createStatement();
	st3.executeUpdate("insert into req(email1,mobile1,units,code,code1) VALUES('"+email1+"','"+mobile1+"','"+units+"','"+r+"','"+r1+"')");
%>
<%
String host = "smtp.gmail.com";
String cit=request.getParameter("select3");
String  bld= request.getParameter("blood");
ArrayList<String> to = new ArrayList();
Class.forName("com.mysql.jdbc.Driver"); 
Connection con1 = DriverManager.getConnection("jdbc:mysql://localhost:3306/synergy",
            "root", "santu");
Statement st = con1.createStatement();
  ResultSet rs1;
rs1 = st.executeQuery("select * from register where blood='" + bld + "' and city='" + cit+ "' ");
//int i=0;
if(rs1.next())
{  
rs1 = st.executeQuery("select * from register where blood='" + bld + "' and city='" + cit+ "' ");
 while(rs1.next())
 {
 to.add(rs1.getString("email"));
}
 
 for(int i=0;i<to.size();i++)
{
//out.println(to.get(i));
String toe=to.get(i);
String from="vinjavatester@gmail.com";  // write your email address means from email address.
String subject = "requesting blood";
String messageText = bld+" blood required you are available or not if available click the link http://localhost:8080/SHARE/req.jsp \n Request Code Is "+r;
boolean sessionDebug = true;
// Create some properties and get the default Session.
//System.setProperty("smtp.protocols", "SSLv3");
Properties props = System.getProperties();

props.put("mail.smtp.startssl.enable","true");
props.setProperty("mail.transport.protocol","smtp");
props.setProperty("mail.host",host);
props.put("mail.smtp.auth", "true");
props.put("mail.smtp.port", "465");    //port is 587 for TLS  if you use SSL then port is 465
props.put("mail.debug", "true");
props.put("mail.smtp.socketFactory.port", "465");
props.put("mail.smtp.socketFactory.fallback", "false");
props.put("mail.smtp.socketFactory.class", "javax.net.ssl.SSLSocketFactory");

Session mailSession = Session.getInstance(props, new javax.mail.Authenticator() {protected PasswordAuthentication getPasswordAuthentication() {return new PasswordAuthentication("username", "password");
}
});
 
// Set debug on the Session
// Passing false will not echo debug info, and passing True will.
 
mailSession.setDebug(sessionDebug);
 
// Instantiate a new MimeMessage and fill it with the
// required information.
 
Message msg = new MimeMessage(mailSession);
msg.setFrom(new InternetAddress(from));
InternetAddress[] address = {new InternetAddress(toe)};
msg.setRecipients(Message.RecipientType.TO, address);
msg.setSubject(subject);
//msg.setSentDate(new Date());
msg.setText(messageText);
 
// Hand the message to the default transport service
// for delivery.
 
 Transport transport = mailSession.getTransport("smtp");
transport.connect(host, "vinjavatester@gmail.com", "#$vin123$#");
transport.sendMessage(msg, msg.getAllRecipients());
/*out.print("<html>");
out.print("<body bgcolor='cyan'>");
out.print("<font size=45 color='red'>");
out.print("<br>");
out.println("\n Mail was sent to "+to+"\n");
out.print("<br><br>");
out.println(" \n from "+from+"\n");
out.print("<br><br>");
out.println(" \n using host "+host+".");
out.print("<br><br>");
out.println("\n Email sent successfully.");
out.print("</font>");
out.print("</body>");
out.print("</html>");*/

}
 out.println("Mail Sent to the appropriate donors. We'll Get back to you soon");
}

else
{
out.println("Mail was not sent because no matched blood group found");
}
%>
</body>
</html>

//donor.jsp
<%@ page contentType="text/html; charset=iso-8859-1" language="java" %>
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Virtual Blood Donation</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="">
  <meta name="author" content="">

  
	<!--link rel="stylesheet/less" href="less/bootstrap.less" type="text/css" /-->
	<!--link rel="stylesheet/less" href="less/responsive.less" type="text/css" /-->
	<!--script src="js/less-1.3.3.min.js"></script-->
	<!--append â#!watchâ to the browser URL, then refresh the page. -->
	
	<link href="css/bootstrap.min.css" rel="stylesheet">
	<link href="css/style.css" rel="stylesheet">
	</head>



<body background-color="00000">
<div class="container">

	<div class="row clearfix">
		<div class="col-md-12 column">
			<nav class="navbar navbar-inverse" role="navigation">
				<div class="navbar-header">
					 <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1"> <span class="sr-only">Toggle navigation</span><span class="icon-bar"></span><span class="icon-bar"></span><span class="icon-bar"></span></button> <a class="navbar-brand active" href="index.html">Home</a>
				</div>
				
				<div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
					<ul class="nav navbar-nav">
					
						<li>
							<a href="about.jsp">ABOUT US</a>
						</li>
						
					</ul>
					<form class="navbar-form navbar-left" role="search">
						<div class="form-group">
							<input class="form-control" type="text">
						</div> <button type="submit" class="btn btn-default">Submit</button>
					</form>
					<ul class="nav navbar-nav navbar-right">
						<li>
							<a href="login.jsp">LOGIN</a>
						</li>
						<li>
							<a href="reg3.jsp"> REGISTRATION</a>
						</li>
						<li>
							<a href="contactb.html">CONTACT US</a>
						</li>
						
					</ul>
				</div>
			</nav>
		</div>
	</div>
	</div>
	<%@ page import="java.util.*" %>
<%@ page import="javax.mail.*" %>
<%@ page import="javax.mail.internet.*" %>
<%@ page import="javax.activation.*" %>
<%@ page import="javax.net.ssl.*" %>
<%@ page import="java.sql.*" %>
<%
	String email=request.getParameter("email");
	Long mobile=Long.parseLong(request.getParameter("number"));
	int code=Integer.parseInt(request.getParameter("code1"));
	Class.forName("com.mysql.jdbc.Driver");
	Connection con=DriverManager.getConnection("jdbc:mysql://localhost:3306/synergy","root","santu");
	Statement st=con.createStatement();
	ResultSet rs=st.executeQuery("select units,status from req where code='"+code+"'");
	
	if(rs.next())
	{
		int n=rs.getInt("units");
		int s=rs.getInt("status");
		rs=st.executeQuery("select units,status from req where code='"+code+"'");
			if(n==s)
			{
				%>
				<script>alert('Donors already available');</script><%
			//out.println("Donors already available");
			//response.sendRedirect("dnr.jsp");
			}
			else
			{
				if(s==0)
				{
					s=1;
					%>
					<script>alert('values is 1');</script><%
					st.executeUpdate("update req set status='"+s+"' where code='"+code+"'");
				}
				else
				{
					%>
					<script>alert('values is incremented');</script><%
					s=s+1;
					st.executeUpdate("update req set status='"+s+"' where code='"+code+"'");
				}
			}
		
	}
%>
<%
	String mail=request.getParameter("email");
	Long number=Long.parseLong(request.getParameter("number"));
	 Class.forName("com.mysql.jdbc.Driver");
	    Connection con1 = DriverManager.getConnection("jdbc:mysql://localhost:3306/synergy","root", "santu");
	    Statement st1 = con.createStatement();
	    st.executeUpdate("insert into res(email,mobile) VALUES('"+mail+"','"+number+"')");
	    out.println("Thank You.. We'll Inform You Soon..");
%>
<%
String host = "smtp.gmail.com";
Class.forName("com.mysql.jdbc.Driver");
Connection con2=DriverManager.getConnection("jdbc:mysql://localhost:3306/synergy","root","santu");
Statement st2=con.createStatement();
ResultSet rs2=st.executeQuery("select email1,code1 from req where code='"+code+"'");
if(rs2.next())
{
	String to=rs2.getString("email1");
	int n=rs2.getInt("code1");
	String from="vinjavatester@gmail.com";
	String subject = "Donor Available";
	String messageText = "Donor Details \n Donar Email :"+mail+"\n Mobile Number "+number+"\n Donater code: "+n;
	boolean sessionDebug = true;
	Properties props = System.getProperties();

	props.put("mail.smtp.startssl.enable","true");
	props.setProperty("mail.transport.protocol","smtp");
	props.setProperty("mail.host",host);
	props.put("mail.smtp.auth", "true");
	props.put("mail.smtp.port", "465");    //port is 587 for TLS  if you use SSL then port is 465
	props.put("mail.debug", "true");
	props.put("mail.smtp.socketFactory.port", "465");
	props.put("mail.smtp.socketFactory.fallback", "false");
	props.put("mail.smtp.socketFactory.class", "javax.net.ssl.SSLSocketFactory");

	Session mailSession = Session.getInstance(props, new javax.mail.Authenticator() {protected PasswordAuthentication getPasswordAuthentication() {return new PasswordAuthentication("username", "password");
	}
	});
	 
	// Set debug on the Session
	// Passing false will not echo debug info, and passing True will.
	 
	mailSession.setDebug(sessionDebug);
	 
	// Instantiate a new MimeMessage and fill it with the
	// required information.
	 
	Message msg = new MimeMessage(mailSession);
	msg.setFrom(new InternetAddress(from));
	InternetAddress[] address = {new InternetAddress(to)};
	msg.setRecipients(Message.RecipientType.TO, address);
	msg.setSubject(subject);
	//msg.setSentDate(new Date());
	msg.setText(messageText);
	 
	// Hand the message to the default transport service
	// for delivery.
	 
	 Transport transport = mailSession.getTransport("smtp");
	transport.connect(host, "vinjavatester@gmail.com", "#$vin123$#");
	transport.sendMessage(msg, msg.getAllRecipients());
}
%>
</body>
</html>
