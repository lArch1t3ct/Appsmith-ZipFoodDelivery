![](https://raw.githubusercontent.com/appsmithorg/appsmith/release/static/appsmith_logo_primary.png)

Low Code No Code (LCNC) is a technique of designing and developing applications with the aim of deploying applications rapidly reducing the cost and time required for traditional software development.

Appsmith_ provides a Low-Code application platform exactly for this purpose.

### [Github](https://github.com/appsmithorg/appsmith) • [Docs](https://docs.appsmith.com/?utm_source=github&utm_medium=social&utm_content=appsmith_docs&utm_campaign=null&utm_term=appsmith_docs) • [Community](https://community.appsmith.com/) • [Tutorials](https://github.com/appsmithorg/appsmith/tree/update/readme#tutorials) • [Youtube](https://www.youtube.com/appsmith) • [Discord](https://discord.gg/rBTTVJp)


# Appsmith-ZipFoodDelivery
During my research of Low Code / No Code (LCNC) development, I created an app with the guideline from @kubowania via freecodecamp.

##### You can visit the application using the below link
[Application](https://app.appsmith.com/app/order-application/zip-food-delivery-664dc905d8dfb212590a1908)


## Corrections
### List2 Widget
The link to the application that @kubowania provides point to an invalid resource on Appsmith_.
This is normal since the tutorial was published around two years ago and the platform has undergo a great deal of transformation.

In the add_modal, the code for __List2__ UI element which fetches the products that the user selected in our select list should be the following:
```javascript
{{
    product_multiselect.selectedOptionValues.map(
        (item) => {
            return fetch_product_catalog.data.find(
                (product) => product.Item == item
            );
        }
    );
}}
```

### add_order Query
`customer_select.selectedOptionValue` returns the full name and we need the user's ID. Thus we need something like this:
```javascript
{
	"Order Id" : {{this.params.id}},
	"Date" : {{moment().format("YYYY-MM-DD")}},
	"Delivery Address" : {{address_input.text}},
	"Total Amount" : {{amount_input.text}},
	"Status" : {{status_input.selectedOptionValue}},
	"Stripe Purchase Id" : {{stripe_input.text}},
	"Customer Id" : {{fetch_all_users.data.reduce((targetId, currentValue) => {
		if(currentValue["First Name"] + " " + currentValue["Last Name"] === customer_select.selectedOptionValue){
			targetId = currentValue.Id;
		}
		return targetId;
	},0);
	}}
}
```

### Disclaimer
As I followed this tutorial for understanding what Low Code No Code approach is, I decided to stop following the tutorial further as something are not the same and it takes some time to debug and move forward.

That being said, I am deploying the app despite its incompleteness.

#### Find The Tutorial Here
[Low-Code for Freelance Developers & Startups – Tutorial](https://www.youtube.com/watch?v=hDzgO2FB_ms)
