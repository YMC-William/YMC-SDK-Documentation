### Server Administration
* A primary contact for all Server Operations has been specified on the Development Team
* Initial Server Configurations are completed
* Initial Server Configurations have been tested and verified
* Any software licences required for server operations are specified and have been communicated to YMC
  Note: User the Server tab on Developer.Ymcgames.com to specify required Server Configurations.

### Server Scaling
* A detailed Server Scaling Plan has been provided to YMC

### Server Stability
* All appropriate measures (monitoring, backups, alerts, etc) have been implemented to ensure server stability
* Steps have been taken to ensure Server Availability of 99.9% (not including scheduled maintenance time)

  Regarding Outages:

  * The Server Administrator agrees to the following standards:
  * An Average-Time-To-Respond of 2 hours to outages
  * A Mean-Time-To-Repair of 4 hours for all outages

### Server Monitoring
The following server data is available to both the Development Team Server Administrator, and YMC's Server Contact:
1. CPU Load
2. Network Load
3. HDD status
4. Memory Status

### Support for Sandbox purchases on Production Server
#### Required:
**IAPs (in-app-purchases) must always be testable - as such, the game server must support sandbox IAPs.**
Prior to the delivery or your submission candidate, you must ensure that
* IAPs are supported on both testing and production environments

If you require a Sandbox account for testing, YMC will provide one.
For technical documentation, please refer to: https://developer.apple.com/library/ios/technotes/tn2259/_index.html
See the FAQ at the bottom, specifically item 16.

```
$result = send_receipt_to_verify( "https://buy.itunes.apple.com/verifyReceipt", receipt )
if $result == 21007
{
$result = send_receipt_to_verify( "https://sandbox.itunes.apple.com/verifyReceipt", receipt )
}
```

