# speco-cameras

Certain models of Speco IP WiFi cameras require no authentication to view them
--

Upon discovery of a Speco camera, you may be prompted to download an executable, which wants to install a browser plug-in to view the camera. While this is fine if you want to administer the camera, view video or image snapshots, what the owner may not know, is that the camera's feed can be seen without the plug-in, and without authentication.

On vulnerable models, you can look for the following path:

		[ /cgi-bin/snapshot.cgi?channel=# ] 
		
where # is the channel of the camera you want to view. If only one camera, make this 1. Increment to find other cameras.

Example: http://127.0.0.1/video.html > http://127.0.0.1/cgi-bin/snapshot.cgi?channel=1

I also found a list of possible strings to try against other Speco cameras here:
https://www.ispyconnect.com/man.aspx?n=Speco

The above was not in the list, but after some enumeration I landed on the "/cgi-bin/snapshot.cgi?channel=1" path which showed a live image from the camera.

--
The images can also be found in http://127.0.0.1/images/snapshot-01.jpg - http://127.0.0.1/images/snapshot-02.jpg and so on.
