# Kalman-Filter-for-3D-Object-Tracking

### Camera Used:
Intel(R) RealSense(TM) Depth Camera 435i

<img src="https://github.com/Arwa-Fawzy/Kalman-Filter-for-Object-Tracking-in-3D-Space/assets/101527083/17aa93ab-c4e2-4e8b-928d-d9f8d1193d57"  width="200" />

### Object to be detected:
A black and white square object with a white circle in the middle. There is only 1 sample of Circle & Dot pattern printed in a 2D shape​. The Dimensions of the marker are:​
1. Radius is 2.5 cm (White circle)​
2. Thickness is 0.5 cm


<img src="https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/bcd8f321-36a8-4b80-9920-e5c5c3bae5d7" width="200" />

### Marker Detection Output:

<img src="https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/3d71d08c-1446-4445-9283-3ced371b6066" width="200" />


### Marker Motion Tracking Output​:

<img src="https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/3c48459c-664c-4447-b5e4-d3956389303a" width="200" />

<img src="https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/c10514cd-de23-48ac-bd01-a1865bdb2578" width="200" />

<img src="https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/1318e619-1375-4f40-a2a3-39295fc9f0a8" width="400" />


Z is always equal to 0 until the depth measurment is done and kalman fliter estimates the z values based on this depth as intial value. 


### Consequences of Kalman Filter Absence on Continues Tracking:
1. **Missing frame due to challenging lighting condition:** 

   Kalman Filter estimates the missing localization  coordination in situations where the lighting conditions are challenging, such as low light or extreme brightness, the camera may struggle to capture clear images of the object being tracked. This can result in missing frames where the object's location cannot be accurately determined.​

   <img src="https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/6caf638c-9dc9-4cd7-bccf-aeac2b4c680d" width="200" />

2. **​Missing frame due to the angle of camera view:​**​
   Kalman Filter estimates the missing localization coordination when the angle at which the camera is positioned relative to the marker  can affect the visibility of it in each frame. If the marker moves out of the camera's field of view or is obscured by other objects due to the camera angle, it can result in missing frames. ​

      <img src="https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/4fcfed97-1ab4-43cd-a3bf-5aaf2119d9e8" width="200" />

3. **​Missing frame due to a barrier:​**​
   Kalman Filter estimates the missing localization  coordination when there is a physical barrier obstructing the camera's view of the object, such as another object passing in front of it or a temporary obstruction, it can lead to missing frames. The object's location cannot be tracked during these moments, causing gaps in the tracking data.​

      <img src="https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/46b45648-d029-48f1-93f5-04212fe8e6e6" width="200" />

4. **​Missing frame due to the high-speed movement:​**​
   Kalman Filter estimates the missing localization coordination when the patient table moves fast to inside the CT coil as the marker may appear blurred or may not be captured by the camera in every frame. This can result in missing frames where the marker's position cannot be accurately determined due to rapid movement.​

   ![image](https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/33aa58e2-19bd-457b-9aa0-4301709f6c09)


### Camera Calibration​ Overview:
1. The World vs Camera coordinates​
2. Camera coordinates are 2D, world coordinate are 3D​
3. Use an scene with known geometry, e.g. A chessboard​
4. Correspond image points to 3D points​
5. Get an algorithm to find the best camera matrix which minimizes the error between estimate and known corresponding 2D points​ Best M occurs when p’ = p.​


      ![1](https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/006f67ed-c56f-4b7b-be4d-17d63b29c991)



      ![2](https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/9d77f165-6c98-448f-bfcd-4f547eac7dab)
  



6. The pinhole camera parameters are represented in a 3-by-4 matrix called the camera matrix.​
7. Camera matrix can be decomposed into intrinsic matrix and extrinsic matrix.


        
![cam](https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/5c4d7e7b-06e4-4d9a-90bd-4855bb83fe5a)


![mat](https://github.com/Arwa-Fawzy/Kalman-Filter-for-3D-Object-Tracking/assets/101527083/c0f4d172-608e-44c9-ade4-c2310e0dc078)




​

​

​




