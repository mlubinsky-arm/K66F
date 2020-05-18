# Pelion ML demo - (PDM + TensorFlow)

This repository shows the integration  of **Pelion Device Management** and **Micro Speech Example**. Used as base application for pelion-ml features demo

Repository of the projects

- [Micro Speech Example](https://github.com/tensorflow/tensorflow/tree/master/tensorflow/lite/micro/examples/micro_speech#deploy-to-nxp-frdm-k66f)
- [Pelion Device Management](https://github.com/tensorflow/tensorflow/tree/master/tensorflow/lite/micro/examples/micro_speech#deploy-to-nxp-frdm-k66f)

## Requirements

- Mbed CLI >= 1.10.0

  For instructions on installing and using Mbed CLI, please see our [documentation](https://os.mbed.com/docs/mbed-os/latest/tools/developing-mbed-cli.html).

- Install the `CLOUD_SDK_API_KEY`

   `mbed config -G CLOUD_SDK_API_KEY ak_1MDE1...<snip>`

   You should generate your own API key. Pelion Device Management is available for any Mbed developer. Create a [free trial](https://os.mbed.com/pelion-free-tier).

   For instructions on how to generate your API key, please see our [documentation](https://cloud.mbed.com/docs/current/integrate-web-app/api-keys.html#generating-an-api-key).


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
