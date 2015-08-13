Within your .git/config you'll see a nifty lil' ```ignorecase = [bool]``` item.  
In langs where case sensitivity matters, if this is ```true``` , annoying things happen when things get renamed ;)  
The default is false. 
This gets set to true because a ```git init``` or ```git clone``` will set this based on the case sensitivity of the system you're on.  

