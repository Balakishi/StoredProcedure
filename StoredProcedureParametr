USE [Northwind]
GO
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
/* I want to check here that if this username already exists, it returns the parameter as status 1. 
And I will use this parameter in the code part in c#. 
At else , add your entered username and password to the database. */
Create procedure [dbo].[RegistWeb]
@status int out, @Username nvarchar (50), @Email nvarchar(50), @Password nvarchar(50), @phone nvarchar(50)
as
--inside the if, i check username at database which equal to entered username--
if exists(select * from Registration where Username=@Username)
begin
--if entered username exisits at the database, return status --
set @status=1
return @status
end
--at else case, Username and paswword which that entered from textbox will be added to databse--
else
begin
insert into Registration(Username,Email,Password,Phone)
values(@Username,@Email,@Password,@phone)
--After the user name and password are added to the database, the status will return 0--
set @status=0
return @status
end
