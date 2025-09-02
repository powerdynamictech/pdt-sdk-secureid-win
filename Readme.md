# POWER DYNAMIC TECHNOLOGY - SecureID SDK

## 📂 Client Project Files Requirements
- Copy all files from **SecureID SDK** into the **build folder**
- Add reference to `FaceSDK.NET.dll` in your project

---

## 🧩 Project Implementation of SecureID SDK - FaceId (Face Recognition)

### Implement `IPdtFaceId` Interface:
- **FaceIdImageEvent** – Event for receiving Bitmap images from camera  
- **FaceIdDataEvent** – Event for receiving detected person user ID  
- **FaceIdPositionEvent** – Event for receiving face detected position (`Ok`, `TooFar`, `TooClose`)  
- **FaceIdProfileEvent** – Event with face detection data:  
  - `Left`, `Top`, `Width` – can be used to create a canvas around client’s face  
  - `Name`, `Gender`, `Age` – data from SDK face analysis  
  - `Authorized` – `true` if client is registered and authorized  
- **FaceIdMultipleProfilesEvent** – Event for receiving multiple profiles found  
- **FaceIdStatusEvent** – Event for SDK FaceID status events  
- **StartAsync** – Method for starting FaceID  

---

### Create `FaceId` Instance with the Following Arguments:
- **ILogger** – Your logger for receiving SecureID SDK logs  
- **CancellationTokenSource** – for stopping FaceID tasks (`cts.Cancel()`)  
- **FaceIdConfig**:
  - `ResWidth` – FaceID camera resolution width  
  - `ResHeight` – FaceID camera resolution height  
  - `AutoRes` – bypasses `ResWidth`/`ResHeight` and uses camera default resolution  
- **Device UUID** – The device UUID received from `AuthenticateDevice` API
