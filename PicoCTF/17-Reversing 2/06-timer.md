## Descripcion
You will find the flag after analysing this apk Download [here](https://artifacts.picoctf.net/c/449/timer.apk).
## Solucion
```
┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ jadx -d /home/min/decomapk /home/min/timer.apk
INFO  - loading ...
INFO  - processing ...
ERROR - finished with errors, count: 3

┌──(min㉿WIN-U49VUBQG3G3)-[~]
└─$ cd decomapk

┌──(min㉿WIN-U49VUBQG3G3)-[~/decomapk]
└─$ dir
resources  sources

┌──(min㉿WIN-U49VUBQG3G3)-[~/decomapk]
└─$ cd resources/

┌──(min㉿WIN-U49VUBQG3G3)-[~/decomapk/resources]
└─$ dir
AndroidManifest.xml  kotlin  META-INF  res

┌──(min㉿WIN-U49VUBQG3G3)-[~/decomapk/resources]
└─$ cat AndroidManifest.xml
<?xml version="1.0" encoding="utf-8"?>
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
    android:versionCode="1"
    android:versionName="picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}"
    android:compileSdkVersion="32"
    android:compileSdkVersionCodename="12"
    package="com.example.timer"
    platformBuildVersionCode="32"
    platformBuildVersionName="12">
    <uses-sdk
        android:minSdkVersion="21"
        android:targetSdkVersion="32"/>
    <application
        android:theme="@style/Theme.Timer"
        android:label="@string/app_name"
        android:icon="@mipmap/ic_launcher"
        android:debuggable="true"
        android:allowBackup="true"
        android:supportsRtl="true"
        android:fullBackupContent="@xml/backup_rules"
        android:roundIcon="@mipmap/ic_launcher_round"
        android:appComponentFactory="androidx.core.app.CoreComponentFactory"
        android:dataExtractionRules="@xml/data_extraction_rules">
        <activity
            android:name="com.example.timer.MainActivity"
            android:exported="true">
            <intent-filter>
                <action android:name="android.intent.action.MAIN"/>
                <category android:name="android.intent.category.LAUNCHER"/>
            </intent-filter>
        </activity>
        <provider
            android:name="androidx.startup.InitializationProvider"
            android:exported="false"
            android:authorities="com.example.timer.androidx-startup">
            <meta-data
                android:name="androidx.emoji2.text.EmojiCompatInitializer"
                android:value="androidx.startup"/>
            <meta-data
                android:name="androidx.lifecycle.ProcessLifecycleInitializer"
                android:value="androidx.startup"/>
        </provider>
    </application>
</manifest>

```
## Notas
- primero decompilamos el apk con jadx, se guarda lo que resulte en la carpeta decomapk, una vez que termine revisamos la carpeta decomapk/resources y entonces revisamos el archivo AndroidManifest.xml 
- encontramos la bandera dentro de AndroidManifest.xml = android:versionName="picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}"
## Referencias
- 