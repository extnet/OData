Ext.NET.OData
=============

Library of OData helpers

##[XQueryable] Attribute for ApiController Actions##

Adding the [XQueryable] Attribute to an ApiController Action will enable support for returning OData metadata to the caller, such as $inlinecount.

**Example**

    // GET api/Products
    [XQueryable]
    public IQueryable<Product> GetProducts()
    {
        return data.Products;
    }


##JsonpFormatter##

Enables support for automatically wrapping Json response in a callback function if 'callback' parameter is sent in request.

To enable, within `Application_Start()`, add the following JsonpFormatter:

**Example**

    var config = GlobalConfiguration.Configuration;
    
    config.Formatters.Insert(0, new JsonpFormatter { });
