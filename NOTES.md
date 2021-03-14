1.a) 
    Files changed: productFilter.html, productFilter.js, ProductController.cls
    added new section for Frame Color in productFilter.html
    added new getPicklistValues call in productFilter.js to set the frameColors variable
    added initiliazation of frameColor in the filters array in the handleCheckboxChange method
    in ProductController.getProduct(), added logic to check for the frameColor filter and add filter to the query if it is set

2.a)
    Files changed: productTileList.js, productTileList.html, ProductController.cls
    removed the PAGE_SIZE variable in ProductController and added a new parameter to getProduct(), pageSize
    changed logic in getProduct() to use the pageSize parameter instead of the class variable PAGE_SIZE
    added variable $pageSize to the getProduct callout in productTileList.js
    set the default of pageSize variable to '5' in productTileList.js
    added get bikesPerPageOptions and a handleItemsPerPageChange event for the dropdown to call in productTileList.js
    added lightning-combobox in productTileList.html for the itemsPerPage selecter that called the handleItemsPerPageChange event on change

3.a) 
    Files changed: productCard.html
    changed all the <section> elements to be <lightning-accordion-section> elements
    wrapped all of these elements in a <lightning-accordion> and set the allow-multiple-sections-open so multiple accordions can be opened at once


4.a)
    Files changed: productCard.html, productCard.js, ProductController.cls
    added a new method ProductController.getProductInStockQuantity(string productName) that will be called from the lwc and perform the REST callout
    added an import to the productCard.js for the new apex method and added a callout to this apex method in the handleRecordLoaded
    added a new field inStockQuantity in the productCard.js to keep track of the quantity that comes back from the apex callout
    added an output in the productCard.html file for the Quantity In Stock value that comes back from the apex callout



Unexpected issues:
1) The links in the PDF do not work. I was able to find everything I needed but links would make things a little quicker
2) The E-Bikes example setup documentation is out of date, so setting up everything was a little bit of a hassle. Instead of creating the communities the old way,
    there is a new way (Digital Experiences in Setup instead of Communities)
3) Let the person know they need to clone the repo to their own repo so they can commit and push to it for later sharing with Viasant, this part just wasn't in the
    instructions so I needed to backtrack to do it
4) Sample REST callout provided in 4.a.i returns an error for the DYNAMO X3 product. This works with other products, but that particular one fails
5) None of the products are setup with a Frame_Color__c, so if you want the filter to work those need to be added to the products (not sure if this is intended to
    problem solve or just overlooked)
6) Adding the callout url as a Remote Site Setting is required and not documented (not sure if this is intended to problem solve or just overlooked)