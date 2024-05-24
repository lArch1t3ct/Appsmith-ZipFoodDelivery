![](https://raw.githubusercontent.com/appsmithorg/appsmith/release/static/appsmith_logo_primary.png)

Low Code No Code (LCNC) is a technique of designing and developing applications with the aim of deploying applications rapidly reducing the cost and time required for traditional software development.

Appsmith_ provides a Low-Code application platform exactly for this purpose.

### [Github](https://github.com/appsmithorg/appsmith) • [Docs](https://docs.appsmith.com/?utm_source=github&utm_medium=social&utm_content=appsmith_docs&utm_campaign=null&utm_term=appsmith_docs) • [Community](https://community.appsmith.com/) • [Tutorials](https://github.com/appsmithorg/appsmith/tree/update/readme#tutorials) • [Youtube](https://www.youtube.com/appsmith) • [Discord](https://discord.gg/rBTTVJp)


# Appsmith-ZipFoodDelivery
During my research of Low Code / No Code (LCNC) development, I created an app with the guideline from @kubowania via freecodecamp.

##### You can visit the application using the below link
Under Development

## Corrections
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

#### Find The Tutorial Here
[Low-Code for Freelance Developers & Startups – Tutorial](https://www.youtube.com/watch?v=hDzgO2FB_ms)