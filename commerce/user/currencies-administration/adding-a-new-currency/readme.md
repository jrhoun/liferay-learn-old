# Adding a New Currency

Liferay Commerce offers multiple currencies in payment options. Furthermore, any currency can function as the primary currency depending on business needs. 

This article details how to add a new currency and if necessary enable the currency as the primary. 

1. Navigate to the _Control Panel_ → _Commerce_ → _Settings_ 
1. Click the _Currencies_ tab. The _Currency_ tab shows ten possible currencies with USD set as the primary currency.
1. Click the _Add Currency_ button.
1. Enter the following:
    *Name:* New Zealand Dollar    
    *Code:* NZD (ISO code)    
    *Format Pattern:* $###,##0.00    
    *Maximum Decimal places:* 2    
    *Minimum Decimal places:* 2    
    *Rounding Mode:* HALF EVEN    
    *Exchange Rate:* 1.49701    
    *Priority:* 11    
1. Leave the radio button toggle to _NO_.    
    <img src="./images/01.png" width="700px">

1. Toggle the _Active_ radio button to _Yes_.
1. Click _Save_.

## Additional Information
### Notes:
The _Format Pattern_ requires the currency’s sign, the number of digits to come between commas, and which places are displayed. For example, in the format $###,##0.00 for US dollars, the places held by _0_ are always displayed (as 0 if no other digit is present) while the places held by _#_ are only displayed if occupied. A value of 0.01 in the above format would be displayed as $0.01.

The _Rounding Mode_ requires a type of [rounding mode](https://en.wikipedia.org/wiki/Rounding#Directed_rounding_to_an_integer) from the drop-down menu.

Using [Mercanet](./../payment-methods/mercanet/readme.md) requires EUR as the primary currency. Therefore, leave the default settings for Primary Currency to _No_ if using Mercanet.