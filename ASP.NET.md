```html
<%@ Page Language="C#" AutoEventWireup="true" CodeFile="Default.aspx.cs" Inherits="_Default" %>
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
	<meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>
    <title>ASP.NET学习笔记</title>
</head>
<body>NULL</body>
</html>
```
<!-- HTML注释  -->
<%-- ASP.NET注释 编译后不包含在html文件中 --%>

ASP.NET的内置对象：
Response	将数据从服务器发送回浏览器
Request		检索从浏览器向服务器发送的请求中的信息
Application	共享应用程序级信息
Session		存储在多个页面调用之间特定用户的信息
Cookie		保存客户端浏览器请求的服务器页面
Server		访问服务器上的资源
ViewState


1.Response
<%--重定向网页--%>
Response.Redirect("~/path/Default.aspx?param_1="+a+"&param_2="+b);
<%--获取参数--%>
string param_3 = Response.Params["param_1"];
<%--写入数据到网页--%>
Response.Write("(string)param_1.value=="+param_3+" is true!");

<%--输出二进制图像--%>
FileStream stream = new FileStream(Server.MapPath("picture.gif"),FileMode.Open);
long FileSize = stream.Length;
byte[] Buffer = new byte[(int)FileSize];
stream.Read(Buffer,0,(int)FileSize);
stream.Close();
Response.BinaryWrite(Buffer);

<%--弹出对话框--%>
Response.Write("<script>alert('Error!')</script>");
<%--关闭窗口--%>
Response.Write("<script>window.close();</script>")


2.Request
<%--获取key的value--%>
Request["key"]
Request.Params["key"]
Request.QueryString["key"]
<%--获取当前使用的浏览器信息--%>
HttpBrowserCapabilities bw = Request.Browser;
类型=bw.Type 名称=bw.Browser 版本=bw.Version 操作平台=bw.Platform 
是否支持 框架=bw.Frames 表格=bw.Tables Cookies=bw.Cookies

string 客户端IP地址 = Request.UserHostAddress;
string 远程客户端IP地址 = Request.ServerVariables["REMOTE_ADDR"];
string 当前页面路径 = Request.CurrentExecutionFilePath;

3.Application
Application.Lock();
Application["key"] = value;
Application.UnLock();
string v = Application["key"].ToString();

4.Session
Session["key"] = value;
		DataTime.Now //当前时间

5.Cookie
Response.Cookies["key"].Value = value;
Response.Cookies["key"]["sub_key"].Value = value;
Response.Cookies["key"].Value = 	  //加密cookies中的数据
	Forms.Authentication.HashPasswordForStoringInConfigFile(data,"md5")
//设置cookies销毁日期
TimeSpan s = new TimeSpan(0,0,20,0);
Response.Cookies["key"].Expires = DataTime.Now.Add(ts);
Response.Cookies["key"].Expires = DataTime.Now.AddMonths(1);
Response.Cookies["key"].Expires = DataTime.Now.Parse("10/26/2007");
Response.Cookies["key"].Expires = DataTime.Now.MaxValue;//永不销毁
Response.Cookies["key"].Expires = DataTime.Now.MinValue;//关闭浏览器时销毁

6.Server
//将执行从当前页转到指定页，并将执行返回到当前页
Server.Execute("newPage.aspx?message=Execute"); 
//将执行从当前页完全转移到指定页面
Server.Transfer("newPage.aspx?message=Transfer");
//从虚拟路径获取物理地址
Server.MapPath("Default.aspx");
//进行URL编码、解码（可防止传递汉字时出现错误）
Server,UrlEncode("http://Default.aspx");
Server,UrlDecode("http%3a%2f%2fDefault.aspx");





