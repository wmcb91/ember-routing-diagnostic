# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    We specify route definitions inside the Application Router.

    In a Route, we specify how to load model data using the model hook.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember generate route campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to 'campus.boston'}}Boston{{/link-to}}
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
    The first `'product'` route definition is nested under the `'products'`
    definition, whereas the second `'product'` route definition is a sibling of
    the `'products'` definition.

    Nested route definitions, like the first `'product'` route above, require
    a nested file structure, such that Route and Template files for `'product'`
    are expected to be found at `app/products/product`. For sibling routes,
    folders are siblings as well.

    The first `'product'` route definition instructs Ember to render
    `app/products/product/template.hbs` in the context (the `outlet`) of the
    parent `app/products/template.hbs`. The second `'product'` route definition
    instructs Ember to render `app/product/template.hbs` in the context of the
    application template.

    These two route definitions do **not** have different paths.
    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    params.movie_id
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    model
    ```
