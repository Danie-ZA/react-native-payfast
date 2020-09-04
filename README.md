# react-native-payfast
A react native component to integrate with PayFast via a webview/API calls.

Check out the [PayFast documentation](https://developers.payfast.co.za/documentation) for more information on the payload and signature usage.

## Note
Currently in BETA, with new features and improvements coming soon

## Installation
1. Add the package to `composer.json` and run `npm install`
```js
"dependencies" : {
    "react-native-payfast" : "^1.0.0"
}
```
## Usage
1. Import the `PayFastWebView` component.

```js
import {PayFastWebView} from "react-native-payfast";
```

2. Assign a JSON object of payment data to the `data` prop of the component. Note the naming conventions of the fields as per the official [PayFast documentation](https://developers.payfast.co.za/documentation/#checkout-page).
```js
const paymentData = {
    merchant_id : 10000100,
    merchant_key: '46f0cd694581a',
    amount: 60.00,
    item_name: 'React Native Purchase'
};

export default function App() {
    return (
        <View>
            <PayFastWebView title='Pay Now' data={paymentData}/>
        </View>
      );
}
```

## Component Props
| Prop name | Type | Description | Example |
| ------------- |:-------| :-------------| :-------|
| title     | String | The title of the payment button | `Pay Now` |
| data      | JSON | The payment data as per the [PayFast documentation](https://developers.payfast.co.za/documentation/#checkout-page). | `{merchant_id : 10000100,merchant_key: '46f0cd694581a',amount: 60.00,item_name: 'React Native Purchase'}` 
| sandbox   | Boolean | Set the component to redirect to the PayFast sandbox environment for test payments | `sandbox={true}` |
| signature | Boolean | An optional security measure to prevent man in the middle attacks. Note - you must have a passphrase set on your PayFast account | `signature={true}` |
| passphrase | String | The passphrase set on your PayFast/Sandbox account for use in conjunction with the signature generation | passphrase={"passphrase"} |
