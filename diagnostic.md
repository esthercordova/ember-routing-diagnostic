# Ember Routing Diagnostic

Record your responses inside the fenced code blocks below each question.

1.  What are the main task(s) you perform inside the Ember Application Router,
    and what are the main task(s) you perform inside an Ember Route?

    ```md
    The Router lives in router.js and holds all the url paths for the application to display. You can also have nestes paths inside the Router.

    In the route (route.js) once should store data that will be available for the respective template.hbs.
    ```

1.  What is the command to generate a route named `boston` nested under
    `campus`?

    ```md
    ember generate route /campus/boston
    ```

1.  Suppose you have a nested route at the URL `/campus/boston`. How would you
    use the `link-to` helper to generate an appropriate link?

    ```md
    {{#link-to "boston"}} Boston {{/link-to}}
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
     The first route has two urls. The /products path and the nested /products/product_id. If you go to AppName/products you will find a view and at AppName/products/3 you will find a view.

     The second one only offers one url, the /products/:product_id. Only one view. 


    ```

1.  Suppose we have the following route definition:

    ```js
    this.route('movie', { path: '/movies/:movie_id' }); // <= 👀 here
    ```

    If we navigate in the browser to `/movies/123`, how can we reference the
    value `'123'` inside a Route?

    ```md
    As an id in the model.

    You create a model and give it data. Each data piece will need an id to be references for the url. In our case a title for the movies would probably be provided too.
    ```

1.  Inside a template, how do we reference data provided by a Route?

    ```md
    with handelbars {{}}, one can use a
    {{#each model as |modelName|}}

    {{modelName.propertyName}}

    {{/each}}

    All that needs to go in an outlet {{outlet}}, that needs to be provided at the template where it's going to be shown.
    ```
