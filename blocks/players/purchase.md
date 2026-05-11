# Purchase

**Category**: 👨‍👩‍👧‍👦 Players

![purchase thumbnail](https://portal.patchxr.io/block-thumbnails/purchase.png)

## Description

Allows to other users to send coins for you as tips or pay for one of your connected device.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Make purchase | Jolt Input | Starts the transaction. |
| Set Coins Tips | Jolt Input |  |
| Target Device | Tag Input | Device to purchase. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| On purchasing | Jolt Output | Signals when the purchasing is in process. |
| On purchasing is finished | Jolt Output | Signals when the purchasing process is ended. -1 means cancelled purchase, while value 1 means successful operation. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Set receiver ID on next spawn | checkbox |  |

---