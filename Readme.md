POWER DYNAMIC TECHNOLOGY - SecureID SDK

Client project files requirements:
- Copy all files from SecureID SDK in build folder
- Add reference to FaceSDK.NET.dll in your project

Project implementation of SecureID SDK - FaceId (Face Recognition)
- Implement IPdtFaceId Interface:
		- FaceIdImageEvent - Event for receiving Bitmap images from camera
		- FaceIdDataEvent - Event for receiving detected person user ID
		- FaceIdPositionEvent - Event for receiving face detected position like : Ok, ToFar, ToClose
		- FaceIdProfileEvent - Event with face detection data.
				- Left, Top, Width - It cand be used to create a canvas around client face
				- Name, Gender, Age - Data from SDK face analysing
				- Authorized - This is true if client is regitered and authorised
		- FaceIdMultipleProfilesEvent - Event for receiving multiple profiles found
		- FaceIdStatusEvent - Event for SDK FaceID status events
		- StartAsync - Method for starting FaceID
		
- Create FaceId instance with the following arguments:
		- ILogger - Your logger for receiving SecureID SDK logs
		- CancellationTokenSource - stopping FaceID running tasks using ex: cts.Cancel()
		- FaceIdConfig:
				- ResWidth - FaceID camera resolution width
				- ResHeight - FaceID camera resolution height
				- AutoRes - Baypas ResWidth ResHeight and uses camera default resolution
		- Device UUID - The devaice UUID received from AuthenticateDevice API
				