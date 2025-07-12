# POWER DYNAMIC TECHNOLOGY - SecureID SDK

## Client Project Files Requirements

- Copy all files from **SecureID SDK** into the `build` folder
- Add reference to `FaceSDK.NET.dll` in your project

## Project Implementation of SecureID SDK - FaceId (Face Recognition)

### Implement `IPdtFaceId` Interface

- `FaceIdImageEvent`: Event for receiving `Bitmap` images from camera

- `FaceIdDataEvent`: Event for receiving detected person user ID

- `FaceIdPositionEvent`: Event for receiving face detected position, such as: `Ok`, `ToFar`, `ToClose`

- `FaceIdProfileEvent`: Event with face detection data:
  - `Left`, `Top`, `Width` - can be used to create a canvas around the client's face
  - `Name`, `Gender`, `Age` - data from SDK face analysis
  - `Authorized` - `true` if the client is registered and authorized

- `FaceIdMultipleProfilesEvent`: Event for receiving multiple profiles found

- `FaceIdStatusEvent`: Event for SDK FaceID status updates

- `StartAsync`: Method for starting FaceID

### Create `FaceId` Instance with the Following Arguments

- `ILogger`: Your logger for receiving SecureID SDK logs

- `CancellationTokenSource`: Used to stop FaceID running tasks (e.g., `cts.Cancel()`)

- `FaceIdConfig`:
  - `ResWidth` - FaceID camera resolution width  
  - `ResHeight` - FaceID camera resolution height  
  - `AutoRes` - bypasses `ResWidth` and `ResHeight` and uses the camera's default resolution

- **Device UUID**  
  The device UUID received from `AuthenticateDevice` API
