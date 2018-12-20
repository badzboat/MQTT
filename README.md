# MQTT

Using Paho-MQTT (python module) to connect to CloudMQTT (Free tier under 15 devices)

1) pip install paho-mqtt
2) Write code

##<Code>
import paho.mqtt.client as mqtt
def on_connect(client, userdata, flags, rc):
   print ("connected with code" +str(rc))
   client.subscribe("Test/#")

def on_message(client, userdata, msg):
 print (str(msg.payload))
 
 client = mqtt.Client()
 client.on_connect = on_connect
 client.on_message = on_message
 client.connect("xxx.cloudmqtt.com", portxxx, 60)
 client.username_pw_set("userxxx", "passxxx")
 client.loop_forever();
<Code>


Ping to all subscribe under "Test"
![image](https://user-images.githubusercontent.com/16419246/50311785-0518c800-046c-11e9-9394-70ba978c18a8.png)

![image](https://user-images.githubusercontent.com/16419246/50312045-b4ee3580-046c-11e9-8f7b-96d49d6d01f3.png)
