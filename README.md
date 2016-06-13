# colourful-ping
This is my first repository and I'm trying to make the cmd ping command change colour depending on the time value.
My internet is not always working properly and I'd like to check the quality based on the cmd windows tool. The command I thought would be the most useful for this purpose is:

<i>C:\Windows\System32\PING.EXE 8.8.8.8 -t </i>

The problem is that it just adds too many innecesary data and its is not that easy to check all every the ms. I believe adding a colour gradient or something similar would make things much more intuitive for me.

I once asked this question on <a href="http://stackoverflow.com/questions/35260196/manipulate-cmd-ping-color-based-on-time">Stack Overflow</a> and the answer was rather intimidating. Someone tried to help me by spitting this code:
	
	@ECHO OFF
	SETLOCAL
	SET loops=10
	:loop
	FOR /f "tokens=3delims==" %%a IN ('PING 8.8.8.8 -n 1') DO FOR /f "delims=m" %%b IN ("%%a") DO ECHO %%b&COLOR %%b&GOTO cchgd
	:cchgd
	PAUSE
	SET /a loops-=1
	IF %loops% gtr 0 GOTO loop
	COLOR
	GOTO :EOF

The problem is that the parameters are really confusing to me, someone who is just starting with any code different than html... Any help with a new piece of code or a clarification on this one will be welcomed!

Thank you very much for any kind of feedback and your time :D
