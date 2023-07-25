
## Usage/Examples


#### Method getStores :
```typescript
import { getStores } from '@killbills-dev/killbills-sdk';

const main = async () => {
    const environment = 'prod';
    const partnerStores = await getStores(environment,'your-access-key');
    return partnerStores;
};
```
##### Output:
```yaml
[
  {
    "id": "id",
    "billing_descriptor": "store billing descriptor",
    "store_name": "store name",
    "merchant_name": "merchant name",
    "full_address": "00 street, 00000, city",
    "siret": 00000000000000
  },
   {
    "id": "id",
    "billing_descriptor": "store billing descriptor",
    "store_name": "store name",
    "merchant_name": "merchant name",
    "full_address": "00 street, 00000, city",
    "siret": 00000000000000
  },
  //...other results
]
```

#### Method sendBankingTransaction :
```typescript
import { sendBankingTransaction } from '@killbills-dev/killbills-sdk';

const main = async () => {

    const environment = 'preprod';
    const hmacKey = 'your-hmac-key';

    const transactionData = {
        bank_id: 'your-bank-id',
        callback_url: 'your-callback-url',
        partner_name: 'your-partner-name',
        receipt_format: 'the-format-you-want', // 'JSON','PDF','SVG','PNG'
        transaction: {
            reference_id: 'your-transaction-reference-id',
            amount: 'your-transaction-amount',
            customer_id: 'your-transaction-customer-id,
            transaction_date: 'your-transaction-date',
            billing_descriptor: 'your-transaction-billing-descriptor',
        })

    };

    const sendTransaction = await sendBankingTransaction(environment,transactionData,hmacKey);

    return sendTransaction;
    
};

```

#### Method sendReceipt :
```typescript
import { sendReceipt } from '@killbills-dev/killbills-sdk';

const main = async () => {
    const environment = 'prod';
    const hmacKey = 'your-hmac-key';
    const receiptData = {

    };

    const sendReceiptToKillbills = await sendReceipt(environment,receiptData,hmacKey);

    return sendReceiptToKillbills;
};

```
