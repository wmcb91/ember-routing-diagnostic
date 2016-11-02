# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    Inside the router, you map out the routes your app will be using by pointing
    to the names of the model hooks in the individual routes. Ember routes have
    the model for each module you want to include.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember generate route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    In a template, write {{#link-to 'campus.boston'}}Boston{{/link-to}}
    ```

1.  Explain **at least** two differences between the following two route
    definitions.

    ```js
    this.route('products', function () {
      this.route('product', { path: '/:product_id' }); // <= 👀here
    });

    this.route('product', { path: '/products/:product_id' }); // <= 👀 here
    ```

    ```md
    One difference would be what is typed into the url, the first would just
    type the product id after the route, and that is weird. The second difference
    is that one is a nested route and the other is not. The nested route would
    prevent 'products' from having a route of it's own, so it would lack a model.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    In the movies route you can pass 123 as a parameter.
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    You can use model.whatever to reference the data from the route.
    ```
