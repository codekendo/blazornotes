
# Component Structure

Learn the code structure of Razor components in Blazor WebAssembly.

We'll cover the following

- [Directives](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/component-structure#Directives)
- [Markup](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/component-structure#Markup)
- [Code block](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/component-structure#Code-block)

The following diagram shows code from the `Counter` component of the `Demo` project that we will create in this chapter:

Press

+

to interact

![](data:image/svg+xml,%3csvg%20xmlns=%27http://www.w3.org/2000/svg%27%20version=%271.1%27%20width=%27658%27%20height=%27318.06999999999994%27/%3e)![Component structure](https://www.educative.io/api/collection/10370001/6577457724653568/page/6219678526734336/image/6125665636843520?page_type=collection_lesson&get_optimised=true)

Component structure

The code in the preceding example is divided into three sections:

- Directives
- Markup
- Code block

Each of the sections has a different purpose.

## Directives[](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/component-structure#Directives)

Directives are used to add special functionality, such as routing, layout, and dependency injection. They are defined within Razor and we cannot define own own directives.

In the preceding example, there is only one directive used—the `@page` directive. The `@page` directive is used for routing. In this example, the following URL will route the user to the `Counter` component:

Press

+

to interact

Ace Editor

URL to Counter component

A typical page can include many directives at the top of the page. Also, many pages have more than one `@page` directive.

Most of the directives in Razor can be used in a Blazor WebAssembly application. These are the Razor directives that are used in Blazor, in alphabetical order:

- `@attribute`: This directive adds a class-level attribute to the component. The following example adds the `[Authorize]` attribute:

Press

+

to interact

Ace Editor

Adding the Authorize attribute

- `@code`: This directive adds class members to the component. In the example, it is used to distinguish the code block.
- `@implements`: This directive implements the specified class.
- `@inherits`: This directive provides full control of the class that the view inherits.
- `@inject`: This directive is used for dependency injection. It enables the component to inject a service from the dependency injection container into the view. The following example injects `HttpClient` defined in the `Program.cs` file into the component:

Press

+

to interact

Ace Editor

Injecting HttpClient

- `@layout`: This directive is used to specify a layout for the Razor component.
    
- `@namespace`: This directive sets the component’s namespace. We only need to use this directive if we do not want to use the default namespace for the component. The default namespace is based on the location of the component.
    
- `@page`: This directive is used for routing.
    
- `@typeparam`: This directive sets a type parameter for the component.
    
- `@using`: This directive controls the components that are in scope.
    

## Markup[](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/component-structure#Markup)

This is HTML with Razor syntax. The Razor syntax can be used to render text and allows C# to be used as part of the markup. We will cover more about Razor syntax in later lessons.

## Code block[](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/component-structure#Code-block)

The code block contains the logic for the page. It begins with the `@code` directive. By convention, the `@code` directive is at the bottom of the page. It is the only file-level directive that is not placed at the top of the page.

The code block is where we add C# fields, properties, and methods to the component. In upcoming lessons, we will move the code block to a separate code-behind file.

Razor components are the building blocks of a Blazor WebAssembly application. They are easy to use since they are simply a combination of HTML markup and C# code.


---
# Routing in Blazor WebAssembly

Learn how routing works in Blazor WebAssembly.

We'll cover the following

- [Route parameters](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/routing-in-blazor-webassembly#Route-parameters)
- [Test yourself](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/routing-in-blazor-webassembly#Test-yourself)
- [Catch-all route parameters](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/routing-in-blazor-webassembly#Catch-all-route-parameters)
- [Test yourself](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/routing-in-blazor-webassembly#Test-yourself)
- [Route constraints](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/routing-in-blazor-webassembly#Route-constraints)

In Blazor WebAssembly, routing is handled on the client, not on the server. As we navigate in the browser, Blazor intercepts that navigation and renders the component with the matching route.

The URLs are resolved relative to the base path that is specified in the `wwwroot/index.html` file. It is specified in the `head` element using the following syntax:

Press

+

to interact

Ace Editor

Base path

Unlike other frameworks that we may have used, the route is not inferred from the location of its file. For example, in the `Demo` project, the `Counter` component is in the `/Pages/Counter` folder, yet it uses the following route:

Press

+

to interact

Ace Editor

Route to Counter component

## Route parameters[](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/routing-in-blazor-webassembly#Route-parameters)

The `Router` component uses route parameters to populate the parameters of the corresponding component. The parameters of both the component and the route must have the same name, but they are not case sensitive.

Since optional route parameters are not supported, we may need to provide more than one `@page` directive to a component to simulate optional parameters. The following example shows how to include multiple `@page` parameters:

Press

+

to interact

Ace Editor

RoutingExample.razor

In the preceding code, the first `@page` directive allows navigation to the component without a parameter and the second `@page` directive allows a route parameter. If a value for `text` is provided, it is assigned to the `Text` property of the component. If the `Text` property of the component is null, it is set to `fantastic`.

## Test yourself[](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/routing-in-blazor-webassembly#Test-yourself)

The output of the code snippets above can be tested by running the app below:

###### /

Demo

wwwroot

Program.cs

Pages

RoutingExample.razor

Index.razor

Properties

Shared

Ace Editor

 

**Your app can be found at:** [https://ed-4609566021517312.educative.run/routing/amazing](https://ed-4609566021517312.educative.run/routing/amazing)

RoutingExample component

> **Note:** Remove the “amazing” from the end of the URL and check the results again at https://ed-XXXX_XXXX_XX_XXX.educative.run/routing.

The following URL will route the user to the `RoutingExample` component:

`/routing`

The following URL will also route the user to the `RoutingExample` component, but this time the `Text` parameter will be set by the route:

`/routing/amazing`

This screenshot shows the results of using the indicated route:

Press

+

to interact

![](data:image/svg+xml,%3csvg%20xmlns=%27http://www.w3.org/2000/svg%27%20version=%271.1%27%20width=%27558%27%20height=%2782%27/%3e)![RoutingExample component](https://www.educative.io/api/collection/10370001/6577457724653568/page/4824913792991232/image/6648265098133504?page_type=collection_lesson&get_optimised=true)

RoutingExample component

> **Note:** Route parameters are not case sensitive.

## Catch-all route parameters[](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/routing-in-blazor-webassembly#Catch-all-route-parameters)

Catch-all route parameters are used to capture paths across multiple folder boundaries. This type of route parameter is a `string` type and can only be placed at the end of the URL. This is a sample component that uses a catch-all route parameter:

Press

+

to interact

Ace Editor

CatchAll.razor

## Test yourself[](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/routing-in-blazor-webassembly#Test-yourself)

The output of the code snippets above can be tested by running the app below:

###### /

Demo

wwwroot

Pages

CatchAll.razor

Index.razor

Properties

Shared

Ace Editor

 

**Your app can be found at:** [https://ed-4609566021517312.educative.run/error/type/3](https://ed-4609566021517312.educative.run/error/type/3)

Catch-all route component

For the `/error/type/3` URL, the preceding code will set the value of the `Path` parameter to `error/type/3`:

Press

+

to interact

![](data:image/svg+xml,%3csvg%20xmlns=%27http://www.w3.org/2000/svg%27%20version=%271.1%27%20width=%27301%27%20height=%27114%27/%3e)![Catch-all route parameter example](https://www.educative.io/api/collection/10370001/6577457724653568/page/4824913792991232/image/4573376879001600?page_type=collection_lesson&get_optimised=true)

Catch-all route parameter example

## Route constraints[](https://www.educative.io/courses/building-real-life-applications-with-blazor-webassembly/routing-in-blazor-webassembly#Route-constraints)

Route constraints are used to enforce the datatype of a route parameter. To define a constraint, add a colon followed by the constraint type to the parameter. In the following example, the route is expecting a route parameter named `Increment` with the type of `int`:

Press

+

to interact

Ace Editor

Route with parameter

The following route constraints are supported:

## Supported Route Constraints

|   |   |   |
|---|---|---|
|**Constraint**|**.NET Type**|**Sample Valid Values**|
|bool|System.Boolean|TRUE, false|
|datetime|System.DateTime|2020-12-31, 2020-12-31 5:26pm|
|decimal|System.Decimal|42.99, -1,000.01|
|double|System.Double|1.234, -1,001.01e8|
|float|System.Single|1.234, -1,001.01e8|
|guid|System.Guid|CD2C1638-1638-72D5-1638-DEADBEEF1638, {CD2C1638-1638-72D5-1638-DEADBEEF1638}|
|int|System.Int32|123456789, -123456789|

The following types are not currently supported as constraints:

- Regular expressions
- Enums
- Custom constraints

Routing is handled on the client. We can use both route parameters and catch-all route parameters to enable routing. Route constraints are used to ensure that a route parameter is of the required datatype. Razor components use Razor syntax to seamlessly merge HTML with C# code.