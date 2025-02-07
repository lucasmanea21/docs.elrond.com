---
id: es-index-receipts
title: receipts
---


## _id

The `_id` field of this index is composed of hex encoded receipt hash.
(example: `ced4692a092226d68fde24840586bdf36b30e02dc4bf2a73516730867545d53c`)

## Fields

| Field     | Description                                                                                         |
|-----------|-----------------------------------------------------------------------------------------------------|
| value     | The value field represents the amount of EGLD that was refunded/penalized from the transaction fee. |
| sender    | The sender field represents the sender of the transaction that generated the receipt.               |
| data      | The data field holds a message with the reason why the receipt was generated.                       |
| txHash    | The txHash field represents the hash of the transaction that generated the receipt.                 |
| timestamp | The timestamp field represents the timestamp of the block in which the transaction was generated.   |

## Query examples

### Fetch the receipt generated by a transaction

```
curl --request GET \
  --url ${ES_URL}/receipts/_search \
  --header 'Content-Type: application/json' \
  --data '{
	"query": {
		"match": {
			"txHash":"d6.."
		}
	}
}'
```
