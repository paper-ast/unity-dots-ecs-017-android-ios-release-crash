# unity-dots-ecs-017-android-release-crash
Created for or bugreport;

Reproducible with: 2020.3.11f1

Steps to reproduce:
1.Create empty project in Unity with simple scene 
2.Add packages:  
```
    "com.unity.burst": "1.5.4",
    "com.unity.entities": "0.17.0-preview.42",
    "com.unity.jobs": "0.8.0-preview.23",
    "com.unity.nuget.newtonsoft-json": "2.0.0",
    "com.unity.serialization": "1.7.0-preview.1",
```
3. Switch build to Android. Set release.  Set IL2CPP.
4. Build and Run on device.
5. Get crash on start



If downgrade entities to 0.16 or make dev.build - no crash  


    