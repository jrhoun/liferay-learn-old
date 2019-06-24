# Introduction

This article details to how to enable Authorize.Net as a payment method. [Authorize.Net](https://www.authorize.net/about-us/) is a subsidiary of Visa and a provider of payment gateway services that manages the submission of billions of transactions to processing networks on behalf of merchant customers.

# Resolution

Before configuring your Commerce site to use Authorize.Net, it is necessary to generate [an API Login ID and a Transaction Key](https://support.authorize.net/s/article/How-do-I-obtain-my-API-Login-ID-and-Transaction-Key) for more information.

1.  Navigate to _(your Commerce site) → Commerce → Settings → Payment Methods_.
2.  Click _Authorize.Net_.
3.  Click _Configuration_.
4.  Enter the following:
    *   Your **API Login ID**
    *   Your **Transaction Key**
5.  Select _Production_ if it is a live site or _Sandbox_ if it is a test environment.
6.  Check the checkboxes to enable the optional Display configurations for:
    *   _Show Bank Account_
    *   _Show Credit Card_
    *   _Show Store Name_
7.  Check the checkboxes to enable to optional Security configurations:
    *   Require CAPTCHA
    *   Require Card Code Verification
8.  Click _Save_.
9.  Click the _3-dot icon_ next to _Authorize.Net_ then _Activate_.

Once finished, Authorize.Net has been enabled as a form of accepting payment.

# Additional Information

For more information, here are some other articles:

*   <a href="">Currencies Administration</a>
*   <a href="">Mercanet</a>
*   <a href="">PayPal</a>
*   <a href="">Learn how to add other 3rd party payment systems.</a>
