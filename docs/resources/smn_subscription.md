---
subcategory: "Simple Message Notification (SMN)"
---

# huaweicloud\_smn\_subscription

Manages a SMN subscription resource within HuaweiCloud.
This is an alternative to `huaweicloud_smn_subscription_v2`

## Example Usage

```hcl
resource "huaweicloud_smn_topic" "topic_1" {
  name         = "topic_1"
  display_name = "The display name of topic_1"
}

resource "huaweicloud_smn_subscription" "subscription_1" {
  topic_urn = huaweicloud_smn_topic.topic_1.id
  endpoint  = "mailtest@gmail.com"
  protocol  = "email"
  remark    = "O&M"
}

resource "huaweicloud_smn_subscription" "subscription_2" {
  topic_urn = huaweicloud_smn_topic.topic_1.id
  endpoint  = "13600000000"
  protocol  = "sms"
  remark    = "O&M"
}
```

## Argument Reference

The following arguments are supported:

* `region` - (Optional) The region in which to obtain the SMN subscription resource. If omitted, the provider-level region will work as default. Changing this creates a new SMN subscription resource.

* `topic_urn` - (Required) Resource identifier of a topic, which is unique.

* `endpoint` - (Required) Message endpoint.
     For an HTTP subscription, the endpoint starts with http\://.
     For an HTTPS subscription, the endpoint starts with https\://.
     For an email subscription, the endpoint is a mail address.
     For an SMS message subscription, the endpoint is a phone number.

* `protocol` - (Required) Protocol of the message endpoint. Currently, email,
     sms, http, and https are supported.

* `remark` - (Optional) Remark information. The remarks must be a UTF-8-coded
     character string containing 128 bytes.

* `subscription_urn` - (Optional) Resource identifier of a subscription, which
     is unique.

* `owner` - (Optional) Project ID of the topic creator.

* `status` - (Optional) Subscription status.
     0 indicates that the subscription is not confirmed.
     1 indicates that the subscription is confirmed.
     3 indicates that the subscription is canceled.


## Attributes Reference

The following attributes are exported:

* `topic_urn` - See Argument Reference above.
* `endpoint` - See Argument Reference above.
* `protocol` - See Argument Reference above.
* `remark` - See Argument Reference above.
* `subscription_urn` - See Argument Reference above.
* `owner` - See Argument Reference above.
* `status` - See Argument Reference above.
