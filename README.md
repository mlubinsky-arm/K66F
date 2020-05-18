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

## Compiling

Get the code using mbed import

```sh
mbed import https://github.com/mlubinsky-arm/K66F
cd K66F
```

### 1) PDM application (Must for first time)

```sh
mbed target K6GF
mbed toolchain GCC_ARM
mbed device-management init -d arm.com --model-name example-app --force -q
mbed compile -f # flashes the firmware to device 
```

Uart logs (Baud rate 9600) Snippet from successfully Device bootstrapped and Device registered

```sh
Application ready
Connect to network
Network initialized, connected with IP 192.168.2.2

Start developer flow
Create resources
Register Pelion Device Management Client

Tensor flow disabled 
Client registered.
Account ID: 016ae19784b892467cec285400000000
Endpoint name: 017229a5a17800000000000100115c48
Device ID: 017229a5a17800000000000100115c48
```

### 2) PDM application + TensorFlow

Enable TensorFlow library using macro `ENABLE_TENSORFLOW`. This will include the library

```sh
mbed compile -f -DENABLE_TENSORFLOW #flashes the firmware to device 
```

Uart logs (Baud rate 14400) Snippet from successfully Device bootstrapped and Device registered

```sh
.flow library.... 
12 bytes lost due to alignment. To avoid this loss, please make sure the tensor_arena is 16 bytes aligned.
Client registered.
Account ID: 016ae19784b892467cec285400000000
Endpoint name: 017229a5a17800000000000100115c48
Device ID: 017229a5a17800000000000100115c48

Heard silence (208) @608ms
Heard no (221) @3136ms
Heard unknown (201) @7104ms
Heard no (204) @8512ms
Heard no (211) @16128ms

```

Note : Compiled with baud rate 9600 , But the actual Serial port baud rate 14400

## Keyword detection

It recognize  the following:

```sh
- yes
- no
- silence
- unknown
```

## Link

<https://developer.arm.com/solutions/machine-learning-on-arm/developer-material/how-to-guides/build-arm-cortex-m-voice-assistant-with-google-tensorflow-lite/single-page>
