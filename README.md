# [`pca` module](https://github.com/viam-modules/pca)

This [pca module](https://app.viam.com/module/viam/pca) implements a pca [pca9685 board](<LINK TO HARDWARE>), used for <DESCRIPTION> using the [`rdk:component:board` API](https://docs.viam.com/appendix/apis/components/board/).

> [!NOTE]
> Before configuring your board, you must [create a machine](https://docs.viam.com/cloud/machines/#add-a-new-machine).

## Configure your pca9685 board

Navigate to the [**CONFIGURE** tab](https://docs.viam.com/configure/) of your [machine](https://docs.viam.com/fleet/machines/) in the [Viam app](https://app.viam.com/).
[Add board / pca:pca9685 to your machine](https://docs.viam.com/configure/#components).

On the new component panel, copy and paste the following attribute template into your board's attributes field:

```json
{
  <ATTRIBUTES>
}
```

### Attributes

The following attributes are available for `viam:pca:pca9685` boards:

<EXAMPLE !!>
| Attribute | Type | Required? | Description |
| --------- | ---- | --------- | ----------  |
| `i2c_bus` | string | **Required** | The index of the I<sup>2</sup>C bus on the board that the board is wired to. |
| `i2c_address` | string | Optional | Default: `0x77`. The [I<sup>2</sup>C device address](https://learn.adafruit.com/i2c-addresses/overview) of the board. |

## Example configuration

### `viam:pca:pca9685`
```json
  {
     "name": "<your-pca-pca9685-board-name>",
      "model": "viam:pca:pca9685",
      "type": "board",
      "namespace": "rdk",
      "attributes": {
      },
      "depends_on": []
  }
```

### Next Steps
- To test your board, expand the **TEST** section of its configuration pane or go to the [**CONTROL** tab](https://docs.viam.com/fleet/control/).
- To write code against your board, use one of the [available SDKs](https://docs.viam.com/sdks/).
- To view examples using a board component, explore [these tutorials](https://docs.viam.com/tutorials/).