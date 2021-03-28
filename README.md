**Coupon service:**
----
The service manages coupons for end-customers. This API service allows to generate both rewardpoint coupon and referral coupon  and retrieve referral coupon.

* **Bonus coupon:**

Allows customers to gain extra points with each paid order that can be turned into special coupons.

**Referral coupons:**
----
* **Referral coupon:**

  order validity: 1 - 14 days old
  
  order status: at least “delivery confirmation"
  
*  **Referral coupon redemption:**

  Coupon has to be used by a different person (not by the buyer)

**Generate Rewardpoints Coupon**
----

  _Generates a coupon from a customer’s bonus points_
  
  POST - `/coupon/RewardpointsCoupon/generateCoupon`

* **Sample request:**

```
{ 
 "_id": "5c57f66f1cd03602abb1a2cb", 
 "type": "coupon", 
 "name": "1 USD Voucher", 
 "description": "For 20 points you can get a voucher worth of 1 USD",  "points": 20, 
 "coupon": { 
 "name": "Voucher worth of 1 USD", 
 "description": "Voucher worth of 1 USD from 20 rewardpoints",  "discountType": "ABSOLUTE", 
 "discountAbsolute": { 
 "amount": 10, 
 "currency": "USD" 
 }, 
 "allowAnonymous": true, 
 "maxRedemptions": 1, 
 "status": "VALID" 
 } 
}
```

* **Sample response:**

```
{ 
 "name": "1 USD Voucher", 
 "description": "Voucher worth of 1 USD from 20 rewardpoints",  "discountType": "ABSOLUTE", 
 "discountAbsolute": { 
 "amount": 10.0, 
 "currency": "USD" 
 } 
}
```

**Referral Coupon Code**
----
  _Retrieves the referral coupon code for a given customer_

  GET - `/coupon/ReferralCouponCode/{{customerId}}`

* **Sample response:**

```
{ 
 "name": "Referral voucher for Adam Nowak", 
 "description": "A referral Coupon", 
 "discountType": "ABSOLUTE", 
 "discountAbsolute": { 
 "amount": 8.0, 
 "currency": "EUR" 
 }, 
 "allowAnonymous": true, 
 "code": "ABGTP3", 
 "status": "VALID", 
 "maxRedemptions": -1, 
 "redemptionCount": 3, 
 "issuedTo": "C007", 
 }
```

  POST - generates the referral coupon code for a given customer
  
  No data provided
  
  

