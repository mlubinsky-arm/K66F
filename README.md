## K66F

Combination of 

<https://github.com/tensorflow/tensorflow/tree/master/tensorflow/lite/micro/examples/micro_speech#deploy-to-nxp-frdm-k66f>

and
<https://github.com/ARMmbed/mbed-os-example-pelion>
 

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
