--# How to check a email or a constraint with triggers-instead of
 --With this code, check your mask
 
 --Check email with istead of trigger

create TRIGGER CheckEmail ON Activeusers INSTEAD OF INSERT

AS

BEGIN

declare @email varchar(40)

SELECT @email = email FROM INSERTED;



if(@email like '%_@__%.__%')

begin

print @email

end

else

begin



print 'this statement doesn`t providing.(emails doesn`t matching)'



end



END



insert into Activeusers values('enginkaratas99@gmail.com','xx','xx')
