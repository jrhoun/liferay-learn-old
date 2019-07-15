# Using FedEx as a Shipping Method

(**Subscribers only**)
Liferay Commerce includes the FedEx method as an option for you to integrate your system with this multinational courier. 


## Prerequisites

Before configuring your store to use FedEX, it is necessary to have the following: 
 
1. FedEx business account number
1. FedEx account password
1. FedEx Web Services Developer Key (available from [FedEx Web Services](https://www.fedex.com/en-us/developer/web-services.html))
1. FedEx Meter Number


This article details how to configure then enable FedEx as a shipping method.

1. Navigate to the _Control Panel_ → _(your site)_ → _Commerce_ → _Settings_. 
1. Click the _Shipping Methods_ tab. 
1. Click _FedEx_.
1. Click the _Configurations_ tab.
1. Enter the following:
    * **URL**: 
    * **Key**: 
    * **Password**:
    * **Account Number**: 
    * **Meter Number**:
1. Select the Dropoff Type.
1. Check any of the _Service Types_ options applicable to your business needs.
1. Select the Packing Type.
1. Enter the _Max Weight_ in both pounds and kilograms.
1. Enter the _Max Size_ in both inches and centimeters.
1. Click _Save_.
1. Click the _Details_ tab.
1. Switch the _Active_ toggle to _YES_.

Your store is now configured to use FedEx as a shipping method. Note that your store can have multiple shipping methods enabled and as long as your credentials are correct, vendorss can select various options to ship their products to their customers.   

## Additional Information

FedEx Web Services Developer Guide

* [FedEx Web Services](https://www.fedex.com/en-us/developer/web-services.html)

To add other shipping methods in Liferay Commerce using exention points:

* [Creating New Shipping Methods](https://help.liferay.com/hc/en-us/articles/360020751831)
