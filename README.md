# [`pca` module](https://github.com/viam-modules/pca)

This [pca module](https://app.viam.com/module/viam/pca) implements a [PCA9685 Arduino I<sup>2</sup>C Interface](https://www.adafruit.com/product/815) using the [`rdk:component:board` API](https://docs.viam.com/appendix/apis/components/board/).

> [!NOTE]
> Before configuring your board, you must [create a machine](https://docs.viam.com/cloud/machines/#add-a-new-machine).

Navigate to the [**CONFIGURE** tab](https://docs.viam.com/configure/) of your [machine](https://docs.viam.com/fleet/machines/) in the [Viam app](https://app.viam.com/).
[Add board / pca:pca9685 to your machine](https://docs.viam.com/configure/#components).

## Configure your pca9685 board
copy and paste the following attribute template into your board's attributes field:

```json
{
  "i2c_bus": "<your-i2c-bus-index>",
  "i2c_address": <int>
}
```

### Attributes
The following attributes are available for `viam:pca:pca9685` boards:

| Attribute | Type | Required? | Description |
| --------- | ---- | --------- | ----------  |
| `i2c_bus` | string | **Required** | The index of the I2C bus on the board with GPIO pins your `pca9685` is connected to. Often a number. <br> Example: `”1”` |
| `i2c_address` | int | Optional | The PCA9685's unique [I2C address](https://learn.adafruit.com/i2c-addresses/overview). |

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
        "i2c_address": 127
      },
      "depends_on": []
  }
```

## Next Steps
- To test your board, expand the **TEST** section of its configuration pane or go to the [**CONTROL** tab](https://docs.viam.com/fleet/control/).
- To write code against your board, use one of the [available SDKs](https://docs.viam.com/sdks/).
- To view examples using a board component, explore [these tutorials](https://docs.viam.com/tutorials/).
