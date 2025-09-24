# [`pca` module](https://github.com/viam-modules/pca)

This [pca module](https://app.viam.com/module/viam/pca) implements an [Adafruit PCA9685 I<sup>2</sup>C Interface](https://www.adafruit.com/product/815) using the [`rdk:component:board` API](https://docs.viam.com/appendix/apis/components/board/).

> [!NOTE]
> Before configuring your board, you must [create a machine](https://docs.viam.com/cloud/machines/#add-a-new-machine).

Navigate to the [**CONFIGURE** tab](https://docs.viam.com/configure/) of your [machine](https://docs.viam.com/fleet/machines/) in the [Viam app](https://app.viam.com/).
[Add board / pca:pca9685 to your machine](https://docs.viam.com/configure/#components).

## Usage
To use this board, connect servo(s) to one of the 16 outputs on the board. Then configure them in Viam as a [GPIO Servo](https://docs.viam.com/operate/reference/components/servo/gpio/) with the `board` set to the configured pca9685 board and `pin` corresponding to the slot it is plugged into (0-15).

For example, if you have a configured pca9685 board called "servo-board" and a servo plugged into the first output, you'd configure a gpio servo like this:

```json
{
  "name": "servo-1",
  "api": "rdk:component:servo",
  "model": "rdk:builtin:gpio",
  "attributes": {
    "pin": "0",
    "board": "servo-board",
  }
}
```

## Configure your pca9685 board
Copy and paste the following attribute template into your board's attributes field:

```json
{
  "name": "<your-i2c-bus-index>",
  "i2c_address": <int>
}
```

### Attributes
The following attributes are available for `viam:pca:pca9685` boards:

| Attribute | Type | Required? | Description |
| --------- | ---- | --------- | ----------  |
| `i2c_bus` | string | **Required** | The index of the I2C bus on the board with GPIO pins your `pca9685` is connected to. Often a number. Example: `”1”` |
| `i2c_address` | int | Optional | The PCA9685's unique [I2C address] in decimal. Default: 68 (0x40)|

### Example configuration

### `viam:pca:pca9685`
```json
  {
      "name": "<your-pca-pca9685-board-name>",
      "model": "viam:pca:pca9685",
      "type": "board",
      "namespace": "rdk",
      "attributes": {
        "i2c_bus": "1",
        "i2c_address": 68
      },
      "depends_on": []
  }
```

## Next Steps
- Add and configure one or more GPIO Servos.
- To test your board, expand the **TEST** section of its configuration pane or go to the [**CONTROL** tab](https://docs.viam.com/fleet/control/).
- To write code against your board, use one of the [available SDKs](https://docs.viam.com/sdks/).
- To view examples using a board component, explore [these tutorials](https://docs.viam.com/tutorials/).
