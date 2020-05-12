## K66F

Combination of 

<https://github.com/tensorflow/tensorflow/tree/master/tensorflow/lite/micro/examples/micro_speech#deploy-to-nxp-frdm-k66f>

and

<https://github.com/ARMmbed/mbed-os-example-pelion>
 
Compiled with baud rate 9600

iBut the actual Serial port baud rate 14500

```
mbed compile --target K66F --toolchain GCC_ARM --profile release --flash --sterm --baudrate  14500
```

It recognize  the following:
```
- yes
- no
- silence
- unknown
```
### Link
<https://developer.arm.com/solutions/machine-learning-on-arm/developer-material/how-to-guides/build-arm-cortex-m-voice-assistant-with-google-tensorflow-lite/single-page>
