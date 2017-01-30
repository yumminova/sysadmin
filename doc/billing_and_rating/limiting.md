## Kazoo Service Limits

Limits : Concepts

How limits work...
Enabling limits:
Ensure the default values are appropriate in system_config/jonny5
And those are....
Ensure jonny5 is configured to start in system_config/whapps_controller
Ensure jonny5 is running
Ensure you have a "default_to" email address in system_config/notify.system_alert to receive notices
Set "authz_enabled" to true on system_config/ecallmgr
Set "authz_default_action" to either "allow" or "deny" on system_config/ecallmgr.  This is used when jonny5 fails to reply.
If you just want to test (and not actually limit) set "authz_dry_run" to true on system_config/ecallmgr.
LikeBe the first to like this



**Kazoo** provides facilities to limit what services are being used by a particular client. Limits can involve simultaneous outbound channels, simultaneous inbound channels, total channel count, and enforcement of credit minimums.

**These features can be used to provide:**

1. Two-way SIP Trunks
2. Inbound SIP Trunks
3. Per-Minute SIP Trunks
4. Per-Minute Hosted PBX Calling
5. General Resource Consumption Limits
6. Pre-Pay Cost Tracking
7. Post-Pay Cost Tracking
8. Basic Fraud Limitations (Prevent post-pay accounts from dipping
 too deep into their credit)
 
**Talking Points:**

1. How to tell if a call was rated as a per-minute or a flat-rate.
2. How to tell if a call was billed properly or not (accounting table?).
3. How to double-check billing, if possible.
4. Tools to run to re-run billing, if possible, for a CDR.
 


## Jonny5 Account Limits

`twoway_trunks`: 0, two way flat rate trunks can only be used if `system_config.jonny5.` `flat_rate_whitelist` `regex` matches AND `system_config.jonny5.` `flat_rate_blacklist` does not. This can also be specified as a `pvt_twoway_trunks`, the lower will be used.  

`inbound_trunks`: 0, exactly the same as two-way trunks but only used for inbound calls. If there are more inbound calls then trunks two-way trunks will be checked next.

`resource_consuming_calls` : -1, hard limit on the number of calls that can consume one or more resources (IE: inbound to outbound forwarded number is one resource consuming call), can also be specified as `pvt_resource_consuming_calls`, the smallest of the two is used.

`calls` : -1, total number of calls (resource consuming OR NOT) that an account can have, can also be specified as `pvt_calls`, the smallest of the two is used.

`allow_prepay` : true, allows the customer to disable per_minute authorizations relying solely on trunks and/or allotments, this will be overridden by `pvt_allow prepay`.

`pvt_type`: "limits",

`pvt_vsn`: "1",

`pvt_account_id`: "d75312345678901234567890",

`pvt_account_db`: "account%2Fd7%2F53%12345678901234567890",

`pvt_created`: 63518278682,

`pvt_modified`: 63518278682,

`pvt_soft_limit_outbound`: false, allows otherwise unauthorized outbound calls to continue

`pvt_soft_limit_inbound`: true, allows otherwise unauthorized inbound calls to conitnue

`pvt_allow_prepay`: true,

`pvt_allow_postpay`: true, whether or not to allow the account to go negative

`pvt_max_postpay_amount`: 100, the maximum negative amount that is acceptable

`pvt_allotments`:

`did_us`: then classification of a number as per system_config.number_manager.classifiers

`amount`: 120, the allotment in seconds

`cycle`: "hourly" the allotment reset period: yearly, monthly, weekly, daily, hourly, minutely

`pvt_discounts`:

`did_us`:  then classification of a number as per system_config.number_manager.classifiers

`percentage`: 10 - a percentage discount off the rate of EVERY per_minute call

`pvt_enabeld`: true,  should limits be enforced for this account, IF FALSE THE ACCOUNT IS UNRESTRICTED
