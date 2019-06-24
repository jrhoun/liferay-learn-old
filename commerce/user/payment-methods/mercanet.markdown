# Introduction

This article details how to enable Mercanet as a payment method. Note that Mercanet accepts <u>only</u> **EUR**. The primary currency of the store should therefore be EUR.

# Resolution
Before configuring your Commerce site to use [Mercanet](https://mercanet-bo.bnpparibas.net/Login.jsp), it is necessary to generate a Mercanet Merchant ID, Secret Key, Key Version. Proceed only after you have obtained those values.

As noted before, Mercanet must have Euros as the primary currency. To change the primary currency:

1.  Navigate to _(your Commerce site) → Commerce → Currencies_.
2.  Click the _3-dot icon_ next to Euro.
3.  Click _Set as Primary_.
4.  Click _Save_.

Verify that _Euro_ is now set as the primary currency.  

On the same _Settings_ page:

1.  Click _Payment Methods_.
2.  Click _Mercanet_.
3.  Click _Configuration_.
4.  Enter the following:
    *   Your _Merchant ID_
    *   Your _Secret Key_
    *   Your _Key Version_
5.  Select _Production_ if it is a live site or _Test_ or _Simulation_ if it is a test environment.
6.  Click _Save_.
7.  Click the _3-dot icon_ next to _Mercanet_ then _Activate_.

Once finished, Mercanet has been enabled as a form of accepting payment.

</div>

# Additional Information

For more information, here are some other articles:

*   <a href="">Currencies Administration</a>
*   <a href="">Authorize.Net</a>
*   <a href="">PayPal</a>
*   <a href="">Learn how to add other 3rd party payment systems.</a>
