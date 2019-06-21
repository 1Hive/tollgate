# Tollgate forwarder

A simple Aragon App forwarder that requires a user to deposit fees before executing an action.

Useful for when an organization wants to make actions public, but impose a customizable cost to prevent spam.

Note that this forwarder does not accept native ETH as a fee.

## Customization

### Initialization

Customizable via initialization for the following parameters:

- `feeToken`: Token address for the fee token
- `feeAmount`: Amount required from fee token (remember to adjust for token decimals)
- `feeDestination`: Destination address to send the fees to

### `feeAmount`

Adjustable via `changeFeeAmount()`, which is protected by `CHANGE_AMOUNT_ROLE`.

Note that `feeAmount` can be set to 0 to dynamically remove or impose a toll without having to modify the organization's permissions.

### `feeDestination`

Adjustable via `changeFeeDestination()`, which is protected by `CHANGE_DESTINATION_ROLE`.
