# ASP.NET Core Blazor

- Article
- 02/09/2024

## In this article

1. [Components](https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-8.0&preserve-view=true#components)
2. [Build a full-stack web app with Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-8.0&preserve-view=true#build-a-full-stack-web-app-with-blazor)
3. [Build a native client app with Blazor Hybrid](https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-8.0&preserve-view=true#build-a-native-client-app-with-blazor-hybrid)
4. [Next steps](https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-8.0&preserve-view=true#next-steps)

_Welcome to Blazor!_

Blazor is a [.NET](https://learn.microsoft.com/en-us/dotnet/standard/tour) frontend web framework that supports both server-side rendering and client interactivity in a single programming model:

- Create rich interactive UIs using [C#](https://learn.microsoft.com/en-us/dotnet/csharp/).
- Share server-side and client-side app logic written in .NET.
- Render the UI as HTML and CSS for wide browser support, including mobile browsers.
- Build hybrid desktop and mobile apps with .NET and Blazor.

Using .NET for client-side web development offers the following advantages:

- Write code in C#, which can improve productivity in app development and maintenance.
- Leverage the existing .NET ecosystem of [.NET libraries](https://learn.microsoft.com/en-us/dotnet/standard/class-libraries).
- Benefit from .NET's performance, reliability, and security.
- Stay productive on Windows, Linux, or macOS with a development environment, such as [Visual Studio](https://visualstudio.microsoft.com/) or [Visual Studio Code](https://code.visualstudio.com/). Integrate with modern hosting platforms, such as [Docker](https://learn.microsoft.com/en-us/dotnet/standard/microservices-architecture/container-docker-introduction/index).
- Build on a common set of languages, frameworks, and tools that are stable, feature-rich, and easy to use.

Note

For a Blazor quick start tutorial, see [Build your first Blazor app](https://dotnet.microsoft.com/learn/aspnet/blazor-tutorial/intro).

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-8.0&preserve-view=true#components)

## Components

Blazor apps are based on _components_. A component in Blazor is an element of UI, such as a page, dialog, or data entry form.

Components are .NET C# classes built into [.NET assemblies](https://learn.microsoft.com/en-us/dotnet/standard/assembly/) that:

- Define flexible UI rendering logic.
- Handle user events.
- Can be nested and reused.
- Can be shared and distributed as [Razor class libraries](https://learn.microsoft.com/en-us/aspnet/core/razor-pages/ui-class?view=aspnetcore-8.0) or [NuGet packages](https://learn.microsoft.com/en-us/nuget/what-is-nuget).

The component class is usually written in the form of a [Razor](https://learn.microsoft.com/en-us/aspnet/core/mvc/views/razor?view=aspnetcore-8.0) markup page with a `.razor` file extension. Components in Blazor are formally referred to as _Razor components_, informally as _Blazor components_. Razor is a syntax for combining HTML markup with C# code designed for developer productivity. Razor allows you to switch between HTML markup and C# in the same file with [IntelliSense](https://learn.microsoft.com/en-us/visualstudio/ide/using-intellisense) programming support in Visual Studio.

Blazor uses natural HTML tags for UI composition. The following Razor markup demonstrates a component that increments a counter when the user selects a button.

razor

```
<PageTitle>Counter</PageTitle>

<h1>Counter</h1>

<p role="status">Current count: @currentCount</p>

<button class="btn btn-primary" @onclick="IncrementCount">Click me</button>

@code {
    private int currentCount = 0;

    private void IncrementCount()
    {
        currentCount++;
    }
}
```

Components render into an in-memory representation of the browser's [Document Object Model (DOM)](https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction) called a _render tree_, which is used to update the UI in a flexible and efficient way.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-8.0&preserve-view=true#build-a-full-stack-web-app-with-blazor)

## Build a full-stack web app with Blazor

Blazor Web Apps provide a component-based architecture with server-side rendering and full client-side interactivity in a single solution, where you can switch between server-side and client-side rendering modes and even mix them in the same page.

Blazor Web Apps can quickly deliver UI to the browser by statically rendering HTML content from the server in response to requests. The page loads fast because UI rendering is performed quickly on the server without the need to download a large JavaScript bundle. Blazor can also further improve the user experience with various progressive enhancements to server rendering, such as enhanced navigation with form posts and streaming rendering of asynchronously-generated content.

Blazor supports _interactive_ server-side rendering (interactive SSR), where UI interactions are handled from the server over a real-time connection with the browser. Interactive SSR enables a rich user experience like one would expect from a client app but without the need to create API endpoints to access server resources. Page content for interactive pages is prerendered, where content on the server is initially generated and sent to the client without enabling event handlers for rendered controls. The server outputs the HTML UI of the page as soon as possible in response to the initial request, which makes the app feel more responsive to users.

Blazor Web Apps support interactivity with client-side rendering (CSR) that relies on a .NET runtime built with [WebAssembly](https://webassembly.org) that you can download with your app. When running Blazor on WebAssembly, your .NET code can access the full functionality of the browser and interop with JavaScript. Your .NET code runs in the browser's security sandbox with the protections that the sandbox provides against malicious actions on the client machine.

Blazor apps can entirely target running on WebAssembly in the browser without the involvement of a server. For a _standalone Blazor WebAssembly app_, assets are deployed as static files to a web server or service capable of serving static content to clients. Once downloaded, standalone Blazor WebAssembly apps can be cached and executed offline as a Progressive Web App (PWA).

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-8.0&preserve-view=true#build-a-native-client-app-with-blazor-hybrid)

## Build a native client app with Blazor Hybrid

_Blazor Hybrid_ enables using Razor components in a native client app with a blend of native and web technologies for web, mobile, and desktop platforms. Code runs natively in the .NET process and renders web UI to an embedded Web View control using a local interop channel. WebAssembly isn't used in Hybrid apps. Hybrid apps are built with [.NET Multi-platform App UI (.NET MAUI)](https://learn.microsoft.com/en-us/dotnet/maui/what-is-maui), which is a cross-platform framework for creating native mobile and desktop apps with C# and XAML.

The Blazor Hybrid supports [Windows Presentation Foundation (WPF)](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/overview/) and [Windows Forms](https://learn.microsoft.com/en-us/dotnet/desktop/winforms/overview/) to transition apps from earlier technology to .NET MAUI.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-8.0&preserve-view=true#next-steps)

---

# ASP.NET Core Blazor supported platforms

- Article
- 07/01/2024

Blazor is supported in the browsers shown in the following table on both mobile and desktop platforms.

|Browser|Version|
|---|---|
|Apple Safari|Current†|
|Google Chrome|Current†|
|Microsoft Edge|Current†|
|Mozilla Firefox|Current†|

†_Current_ refers to the latest version of the browser.

For [Blazor Hybrid apps](https://learn.microsoft.com/en-us/aspnet/core/blazor/hybrid/?view=aspnetcore-8.0), we test on and support the latest platform Web View control versions:

- [Microsoft Edge `WebView2` on Windows](https://learn.microsoft.com/en-us/microsoft-edge/webview2/)
- [Chrome on Android](https://play.google.com/store/apps/details?id=com.android.chrome)
- [Safari on iOS and macOS](https://www.apple.com/safari/)

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/supported-platforms?view=aspnetcore-8.0#additional-resources)

## Additional resources

- [ASP.NET Core Blazor hosting models](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0)
- [ASP.NET Core SignalR supported platforms](https://learn.microsoft.com/en-us/aspnet/core/signalr/supported-platforms?view=aspnetcore-8.0)

Collaborate with us on GitHub

The source for this content can be found on GitHub, where you can also create and review issues and pull requests. For more information, see [our contributor guide](https://learn.microsoft.com/contribute/content/dotnet/dotnet-contribute).

![](https://learn.microsoft.com/media/logos/logo_net.svg)

ASP.NET Core feedback

ASP.NET Core is an open source project. Select a link to provide feedback:

[Open a documentation issue](https://github.com/dotnet/aspnetcore.docs/issues/new?template=customer-feedback.yml&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Faspnet%2Fcore%2Fblazor%2Fsupported-platforms%3Fview%3Daspnetcore-8.0&pageQueryParams=%3Fview%3Daspnetcore-8.0&contentSourceUrl=https%3A%2F%2Fgithub.com%2Fdotnet%2FAspNetCore.Docs%2Fblob%2Fmain%2Faspnetcore%2Fblazor%2Fsupported-platforms.md&documentVersionIndependentId=b03c3cec-a3de-d563-d0f8-45fabfb39758&feedback=%0A%0A%5BEnter+feedback+here%5D%0A&author=%40guardrex&metadata=*+ID%3A+c7957ff6-5b09-31dd-17dd-2bf3660a8ebd+%0A*+Service%3A+**aspnet-core**%0A*+Sub-service%3A+**blazor**&labels=Source+-+Docs.ms%2C%3Awatch%3A+Not+Triaged) [Provide product feedback](https://github.com/dotnet/aspnetcore/blob/main/CONTRIBUTING.md)

---

## Additional resources

Documentation

- [ASP.NET Core Blazor WebAssembly build tools and ahead-of-time (AOT) compilation](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?source=recommendations)
    
    Learn about the WebAssembly build tools and how to compile a Blazor WebAssembly app ahead of deployment with ahead-of-time (AOT) compilation.
    
- [Tooling for ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/tooling?source=recommendations)
    
    Learn about the tools available to build Blazor apps and how to use them.
    
- [ASP.NET Core Blazor hosting models](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?source=recommendations)
    
    Learn about Blazor hosting models and how to pick which one to use.
    

Training

Module

[Build a mobile and desktop app with Blazor Hybrid and .NET MAUI - Training](https://learn.microsoft.com/en-us/training/modules/build-blazor-hybrid/?source=recommendations)

Learn how to set up your development environment and build your first cross-platform hybrid app with Blazor, .NET MAUI, and C#.

---

- [ASP.NET Core Blazor supported platforms](https://learn.microsoft.com/en-us/aspnet/core/blazor/supported-platforms?source=recommendations)
    
    Learn about the supported platforms for ASP.NET Core Blazor.
    
- [Build a Blazor todo list app](https://learn.microsoft.com/en-us/aspnet/core/blazor/tutorials/build-a-blazor-app?source=recommendations)
    
    Build a Blazor app step-by-step.
    
- [ASP.NET Core Blazor fundamentals](https://learn.microsoft.com/en-us/aspnet/core/blazor/fundamentals/?source=recommendations)
    
    Learn foundational concepts of the Blazor application framework.
    
- [ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/?source=recommendations)
    
    Explore ASP.NET Core Blazor, a way to build interactive client-side web UI with .NET in an ASP.NET Core app.
    
- [ASP.NET Core Series: Blazor](https://learn.microsoft.com/en-us/shows/on-dotnet/aspnet-core-series-blazor?source=recommendations)
    
    ASP.NET Core is our open-source, cross-platform framework for building modern, cloud-enabled, Internet-connected apps. In this series of videos we'll be cover many of the interesting features of the framework.There's been ton of interest about Blazor in the community. In the episode, Dan Roth joins Jeremy to talk about how you can do Blazor on the server and in the web browser. Useful Links[01:10] - What is Blazor?[03:36] - What's the different between Blazor server and Blazor WebAssembly[07:
    

Training

Module

[Build rich interactive components with Blazor web apps - Training](https://learn.microsoft.com/en-us/training/modules/blazor-build-rich-interactive-components/?source=recommendations)

Learn how to interoperate Blazor apps with JavaScript code, use templated components, and handle component lifecycle events.

Certification

[Microsoft Certified: Azure Developer Associate - Certifications](https://learn.microsoft.com/en-us/credentials/certifications/azure-developer/?source=recommendations)

Build end-to-end solutions in Microsoft Azure to create Azure Functions, implement and manage web apps, develop solutions utilizing Azure storage, and more.

---

# ASP.NET Core Blazor WebAssembly build tools and ahead-of-time (AOT) compilation

- Article
- 04/12/2024

## In this article

1. [.NET WebAssembly build tools](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#net-webassembly-build-tools)
2. [Ahead-of-time (AOT) compilation](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#ahead-of-time-aot-compilation)
3. [Trim .NET IL after ahead-of-time (AOT) compilation](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#trim-net-il-after-ahead-of-time-aot-compilation)
4. [Heap size for some mobile device browsers](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#heap-size-for-some-mobile-device-browsers)

This article describes the build tools for standalone Blazor WebAssembly apps and how to compile an app ahead of deployment with ahead-of-time (AOT) compilation.

Although the article primarily focuses on standalone Blazor WebAssembly apps, the section on [heap size for some mobile device browsers](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#heap-size-for-some-mobile-device-browsers) also applies to the client-side project (`.Client`) of a Blazor Web App.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#net-webassembly-build-tools)

## .NET WebAssembly build tools

The .NET WebAssembly build tools are based on [Emscripten](https://emscripten.org/), a compiler toolchain for the web platform. To install the build tools, use _**either**_ of the following approaches:

- For the **ASP.NET and web development** workload in the Visual Studio installer, select the **.NET WebAssembly build tools** option from the list of optional components.
- Execute `dotnet workload install wasm-tools` in an administrative command shell.

Note

.NET WebAssembly build tools for .NET 6 projects

The `wasm-tools` workload installs the build tools for the latest release. However, the current version of the build tools are incompatible with existing projects built with .NET 6. Projects using the build tools that must support both .NET 6 and a later release must use multi-targeting.

Use the `wasm-tools-net6` workload for .NET 6 projects when developing apps with the .NET 7 SDK. To install the `wasm-tools-net6` workload, execute the following command from an administrative command shell:

.NET CLI

```
dotnet workload install wasm-tools-net6
```

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#ahead-of-time-aot-compilation)

## Ahead-of-time (AOT) compilation

Blazor WebAssembly supports ahead-of-time (AOT) compilation, where you can compile your .NET code directly into WebAssembly. AOT compilation results in runtime performance improvements at the expense of a larger app size.

Without enabling AOT compilation, Blazor WebAssembly apps run on the browser using a .NET [Intermediate Language (IL)](https://learn.microsoft.com/en-us/dotnet/standard/glossary#il) interpreter implemented in WebAssembly with partial [just-in-time (JIT)](https://learn.microsoft.com/en-us/dotnet/standard/glossary#jit) runtime support, informally referred to as the _Jiterpreter_. Because the .NET IL code is interpreted, apps typically run slower than they would on a server-side .NET JIT runtime without any IL interpretation. AOT compilation addresses this performance issue by compiling an app's .NET code directly into WebAssembly for native WebAssembly execution by the browser. The AOT performance improvement can yield dramatic improvements for apps that execute CPU-intensive tasks. The drawback to using AOT compilation is that AOT-compiled apps are generally larger than their IL-interpreted counterparts, so they usually take longer to download to the client when first requested.

For guidance on installing the .NET WebAssembly build tools, see [ASP.NET Core Blazor WebAssembly build tools and ahead-of-time (AOT) compilation](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0).

To enable WebAssembly AOT compilation, add the `<RunAOTCompilation>` property set to `true` to the Blazor WebAssembly app's project file:

XML

```
<PropertyGroup>
  <RunAOTCompilation>true</RunAOTCompilation>
</PropertyGroup>
```

To compile the app to WebAssembly, publish the app. Publishing the `Release` configuration ensures the .NET Intermediate Language (IL) linking is also run to reduce the size of the published app:

.NET CLI

```
dotnet publish -c Release
```

WebAssembly AOT compilation is only performed when the project is published. AOT compilation isn't used when the project is run during development (`Development` environment) because AOT compilation usually takes several minutes on small projects and potentially much longer for larger projects. Reducing the build time for AOT compilation is under development for future releases of ASP.NET Core.

The size of an AOT-compiled Blazor WebAssembly app is generally larger than the size of the app if compiled into .NET IL:

- Although the size difference depends on the app, most AOT-compiled apps are about twice the size of their IL-compiled versions. This means that using AOT compilation trades off load-time performance for runtime performance. Whether this tradeoff is worth using AOT compilation depends on your app. Blazor WebAssembly apps that are CPU intensive generally benefit the most from AOT compilation.
    
- The larger size of an AOT-compiled app is due to two conditions:
    
    - More code is required to represent high-level .NET IL instructions in native WebAssembly.
    - AOT doesn't trim out managed DLLs when the app is published. Blazor requires the DLLs for [reflection metadata](https://learn.microsoft.com/en-us/dotnet/csharp/advanced-topics/reflection-and-attributes/) and to support certain .NET runtime features. Requiring the DLLs on the client increases the download size but provides a more compatible .NET experience.

Note

For [Mono](https://github.com/mono/mono)/WebAssembly MSBuild properties and targets, see [`WasmApp.Common.targets` (`dotnet/runtime` GitHub repository)](https://github.com/dotnet/runtime/blob/main/src/mono/wasm/build/WasmApp.Common.targets). Official documentation for common MSBuild properties is planned per [Document blazor msbuild configuration options (`dotnet/docs` #27395)](https://github.com/dotnet/docs/issues/27395).

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#trim-net-il-after-ahead-of-time-aot-compilation)

## Trim .NET IL after ahead-of-time (AOT) compilation

The `WasmStripILAfterAOT` MSBuild option enables removing the .NET Intermediate Language (IL) for compiled methods after performing AOT compilation to WebAssembly, which reduces the size of the `_framework` folder.

In the app's project file:

XML

```
<PropertyGroup>
  <RunAOTCompilation>true</RunAOTCompilation>
  <WasmStripILAfterAOT>true</WasmStripILAfterAOT>
</PropertyGroup>
```

This setting trims away the IL code for most compiled methods, including methods from libraries and methods in the app. Not all compiled methods can be trimmed, as some are still required by the .NET interpreter at runtime.

To report a problem with the trimming option, [open an issue on the `dotnet/runtime` GitHub repository](https://github.com/dotnet/runtime/issues).

Disable the trimming property if it prevents your app from running normally:

XML

```
<WasmStripILAfterAOT>false</WasmStripILAfterAOT>
```

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#heap-size-for-some-mobile-device-browsers)

## Heap size for some mobile device browsers

When building a Blazor app that runs on the client and targets mobile device browsers, especially Safari on iOS, decreasing the maximum memory for the app with the MSBuild property `EmccMaximumHeapSize` may be required. For more information, see [Host and deploy ASP.NET Core Blazor WebAssembly](https://learn.microsoft.com/en-us/aspnet/core/blazor/host-and-deploy/webassembly?view=aspnetcore-8.0#decrease-maximum-heap-size-for-some-mobile-device-browsers).

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#runtime-relinking)

## Runtime relinking

One of the largest parts of a Blazor WebAssembly app is the WebAssembly-based .NET runtime (`dotnet.wasm`) that the browser must download when the app is first accessed by a user's browser. Relinking the .NET WebAssembly runtime trims unused runtime code and thus improves download speed.

Runtime relinking requires installation of the .NET WebAssembly build tools. For more information, see [Tooling for ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/tooling?view=aspnetcore-8.0#net-webassembly-build-tools).

With the .NET WebAssembly build tools installed, runtime relinking is performed automatically when an app is **published** in the `Release` configuration. The size reduction is particularly dramatic when disabling globalization. For more information, see [ASP.NET Core Blazor globalization and localization](https://learn.microsoft.com/en-us/aspnet/core/blazor/globalization-localization?view=aspnetcore-8.0#invariant-globalization).

Important

Runtime relinking trims class instance JavaScript-invokable .NET methods unless they're protected. For more information, see [Call .NET methods from JavaScript functions in ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/javascript-interoperability/call-dotnet-from-javascript?view=aspnetcore-8.0#avoid-trimming-javascript-invokable-net-methods).

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#single-instruction-multiple-data-simd)

## Single Instruction, Multiple Data (SIMD)

Blazor uses [WebAssembly Single Instruction, Multiple Data (SIMD)](https://wikipedia.org/wiki/Single_instruction,_multiple_data) to improve the throughput of vectorized computations by performing an operation on multiple pieces of data in parallel using a single instruction.

To disable SIMD, for example when targeting old browsers or browsers on mobile devices that don't support SIMD, set the `<WasmEnableSIMD>` property to `false` in the app's project file (`.csproj`):

XML

```
<PropertyGroup>
  <WasmEnableSIMD>false</WasmEnableSIMD>
</PropertyGroup>
```

For more information, see [Configuring and hosting .NET WebAssembly applications: SIMD - Single instruction, multiple data](https://aka.ms/dotnet-wasm-features#simd---single-instruction-multiple-data) and note that the guidance isn't versioned and applies to the latest public release.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#exception-handling)

## Exception handling

Exception handling is enabled by default. To disable exception handling, add the `<WasmEnableExceptionHandling>` property with a value of `false` in the app's project file (`.csproj`):

XML

```
<PropertyGroup>
  <WasmEnableExceptionHandling>false</WasmEnableExceptionHandling>
</PropertyGroup>
```

For more information, see the following resources:

- [Configuring and hosting .NET WebAssembly applications: EH - Exception handling](https://github.com/dotnet/runtime/blob/main/src/mono/wasm/features.md#eh---exception-handling)
- [Exception handling](https://github.com/WebAssembly/exception-handling/blob/master/proposals/exception-handling/Exceptions.md)

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#additional-resources)

## Additional resources

- [ASP.NET Core Blazor WebAssembly native dependencies](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-native-dependencies?view=aspnetcore-8.0)
- [Webcil packaging format for .NET assemblies](https://learn.microsoft.com/en-us/aspnet/core/blazor/host-and-deploy/webassembly?view=aspnetcore-8.0#webcil-packaging-format-for-net-assemblies)

---
# ASP.NET Core Blazor hosting models

- Article
- 02/09/2024

## In this article

1. [Blazor Server](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#blazor-server)
2. [Blazor WebAssembly](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#blazor-webassembly)
3. [Blazor Hybrid](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#blazor-hybrid)
4. [Which Blazor hosting model should I choose?](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#which-blazor-hosting-model-should-i-choose)
5. [Setting a component's hosting model](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#setting-a-components-hosting-model)

This article explains Blazor hosting models, primarily focused on Blazor Server and Blazor WebAssembly apps in versions of .NET earlier than .NET 8. The guidance in this article is relevant under all .NET releases for Blazor Hybrid apps that run on native mobile and desktop platforms. Blazor Web Apps in .NET 8 or later are better conceptualized by how Razor components are rendered, which is described as their _render mode_. Render modes are briefly touched on in the _Fundamentals_ overview article and covered in detail in [ASP.NET Core Blazor render modes](https://learn.microsoft.com/en-us/aspnet/core/blazor/components/render-modes?view=aspnetcore-8.0) of the _Components_ node.

Blazor is a web framework for building web UI components ([Razor components](https://learn.microsoft.com/en-us/aspnet/core/blazor/components/?view=aspnetcore-8.0)) that can be hosted in different ways. Razor components can run server-side in ASP.NET Core (_Blazor Server_) versus client-side in the browser on a [WebAssembly](https://webassembly.org/)-based .NET runtime (_Blazor WebAssembly_, _Blazor WASM_). You can also host Razor components in native mobile and desktop apps that render to an embedded Web View control (_Blazor Hybrid_). Regardless of the hosting model, the way you build Razor components _is the same_. The same Razor components can be used with any of the hosting models unchanged.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#blazor-server)

## Blazor Server

With the Blazor Server hosting model, components are executed on the server from within an ASP.NET Core app. UI updates, event handling, and JavaScript calls are handled over a [SignalR](https://learn.microsoft.com/en-us/aspnet/core/signalr/introduction?view=aspnetcore-8.0) connection using the [WebSockets protocol](https://learn.microsoft.com/en-us/aspnet/core/fundamentals/websockets?view=aspnetcore-8.0). The state on the server associated with each connected client is called a _circuit_. Circuits aren't tied to a specific network connection and can tolerate temporary network interruptions and attempts by the client to reconnect to the server when the connection is lost.

In a traditional server-rendered app, opening the same app in multiple browser screens (tabs or `iframes`) typically doesn't translate into additional resource demands on the server. For the Blazor Server hosting model, each browser screen requires a separate circuit and separate instances of server-managed component state. Blazor considers closing a browser tab or navigating to an external URL a _graceful_ termination. In the event of a graceful termination, the circuit and associated resources are immediately released. A client may also disconnect non-gracefully, for instance due to a network interruption. Blazor Server stores disconnected circuits for a configurable interval to allow the client to reconnect.

![The browser interacts with Blazor (hosted inside of an ASP.NET Core app) on the server over a SignalR connection.](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models/_static/blazor-server.png?view=aspnetcore-8.0)

On the client, the Blazor script establishes the SignalR connection with the server. The script is served from an embedded resource in the ASP.NET Core shared framework.

The Blazor Server hosting model offers several benefits:

- Download size is significantly smaller than when the Blazor WebAssembly hosting model is used, and the app loads much faster.
- The app takes full advantage of server capabilities, including the use of .NET Core APIs.
- .NET Core on the server is used to run the app, so existing .NET tooling, such as debugging, works as expected.
- Thin clients are supported. For example, Blazor Server works with browsers that don't support WebAssembly and on resource-constrained devices.
- The app's .NET/C# code base, including the app's component code, isn't served to clients.

The Blazor Server hosting model has the following limitations:

- Higher latency usually exists. Every user interaction involves a network hop.
- There's no offline support. If the client connection fails, interactivity fails.
- Scaling apps with many users requires server resources to handle multiple client connections and client state.
- An ASP.NET Core server is required to serve the app. Serverless deployment scenarios aren't possible, such as serving the app from a Content Delivery Network (CDN).

We recommend using the [Azure SignalR Service](https://learn.microsoft.com/en-us/azure/azure-signalr) for apps that adopt the Blazor Server hosting model. The service allows for scaling up a Blazor Server app to a large number of concurrent SignalR connections.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#blazor-webassembly)

## Blazor WebAssembly

The Blazor WebAssembly hosting model runs components client-side in the browser on a WebAssembly-based .NET runtime. Razor components, their dependencies, and the .NET runtime are downloaded to the browser. Components are executed directly on the browser UI thread. UI updates and event handling occur within the same process. Assets are deployed as static files to a web server or service capable of serving static content to clients.

![Blazor WebAssembly: Blazor runs on a UI thread inside the browser.](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models/_static/blazor-webassembly.png?view=aspnetcore-8.0)

Blazor web apps can use the Blazor WebAssembly hosting model to enable client-side interactivity. When an app is created that exclusively runs on the Blazor WebAssembly hosting model without server-side rendering and interactivity, the app is called a _standalone_ Blazor WebAssembly app.

When a standalone Blazor WebAssembly app uses a backend ASP.NET Core app to serve its files, the app is called a _hosted_ Blazor WebAssembly app. Using hosted Blazor WebAssembly, you get a full-stack web development experience with .NET, including the ability to share code between the client and server apps, support for prerendering, and integration with MVC and Razor Pages. A hosted client app can interact with its backend server app over the network using a variety of messaging frameworks and protocols, such as [web API](https://learn.microsoft.com/en-us/aspnet/core/web-api/?view=aspnetcore-8.0), [gRPC-web](https://learn.microsoft.com/en-us/aspnet/core/grpc/?view=aspnetcore-8.0), and [SignalR](https://learn.microsoft.com/en-us/aspnet/core/signalr/introduction?view=aspnetcore-8.0) ([Use ASP.NET Core SignalR with Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/tutorials/signalr-blazor?view=aspnetcore-8.0)).

A Blazor WebAssembly app built as a [Progressive Web App (PWA)](https://learn.microsoft.com/en-us/aspnet/core/blazor/progressive-web-app?view=aspnetcore-8.0) uses modern browser APIs to enable many of the capabilities of a native client app, such as working offline, running in its own app window, launching from the host's operating system, receiving push notifications, and automatically updating in the background.

The Blazor script handles:

- Downloading the .NET runtime, Razor components, and the component's dependencies.
- Initialization of the runtime.

The size of the published app, its _payload size_, is a critical performance factor for an app's usability. A large app takes a relatively long time to download to a browser, which diminishes the user experience. Blazor WebAssembly optimizes payload size to reduce download times:

- Unused code is stripped out of the app when it's published by the [Intermediate Language (IL) Trimmer](https://learn.microsoft.com/en-us/aspnet/core/blazor/host-and-deploy/configure-trimmer?view=aspnetcore-8.0).
- HTTP responses are compressed.
- The .NET runtime and assemblies are cached in the browser.

The Blazor WebAssembly hosting model offers several benefits:

- For standalone Blazor WebAssembly apps, there's no .NET server-side dependency after the app is downloaded from the server, so the app remains functional if the server goes offline.
- Client resources and capabilities are fully leveraged.
- Work is offloaded from the server to the client.
- For standalone Blazor WebAssembly apps, an ASP.NET Core web server isn't required to host the app. Serverless deployment scenarios are possible, such as serving the app from a Content Delivery Network (CDN).

The Blazor WebAssembly hosting model has the following limitations:

- Razor components are restricted to the capabilities of the browser.
- Capable client hardware and software (for example, WebAssembly support) is required.
- Download size is larger, and components take longer to load.
- Code sent to the client can't be protected from inspection and tampering by users.

The .NET [Intermediate Language (IL)](https://learn.microsoft.com/en-us/dotnet/standard/glossary#il) interpreter includes partial [just-in-time (JIT)](https://learn.microsoft.com/en-us/dotnet/standard/glossary#jit) runtime support to achieve improved runtime performance. The JIT interpreter optimizes execution of interpreter bytecodes by replacing them with tiny blobs of WebAssembly code. The JIT interpreter is automatically enabled for Blazor WebAssembly apps except when debugging.

Blazor supports ahead-of-time (AOT) compilation, where you can compile your .NET code directly into WebAssembly. AOT compilation results in runtime performance improvements at the expense of a larger app size. For more information, see [ASP.NET Core Blazor WebAssembly build tools and ahead-of-time (AOT) compilation](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#ahead-of-time-aot-compilation).

The same [.NET WebAssembly build tools](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0) used for AOT compilation also [relink the .NET WebAssembly runtime](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#runtime-relinking) to trim unused runtime code. Blazor also trims unused code from .NET framework libraries. The .NET compiler further precompresses a standalone Blazor WebAssembly app for a smaller app payload.

WebAssembly-rendered Razor components can use [native dependencies](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-native-dependencies?view=aspnetcore-8.0) built to run on WebAssembly.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#blazor-hybrid)

## Blazor Hybrid

Blazor can also be used to build native client apps using a hybrid approach. Hybrid apps are native apps that leverage web technologies for their functionality. In a Blazor Hybrid app, Razor components run directly in the native app (not on WebAssembly) along with any other .NET code and render web UI based on HTML and CSS to an embedded Web View control through a local interop channel.

![Hybrid apps with .NET and Blazor render UI in a Web View control, where the HTML DOM interacts with Blazor and .NET of the native desktop or mobile app.](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models/_static/hybrid-apps-1.png?view=aspnetcore-8.0)

Blazor Hybrid apps can be built using different .NET native app frameworks, including .NET MAUI, WPF, and Windows Forms. Blazor provides `BlazorWebView` controls for adding Razor components to apps built with these frameworks. Using Blazor with .NET MAUI offers a convenient way to build cross-platform Blazor Hybrid apps for mobile and desktop, while Blazor integration with WPF and Windows Forms can be a great way to modernize existing apps.

Because Blazor Hybrid apps are native apps, they can support functionality that isn't available with only the web platform. Blazor Hybrid apps have full access to native platform capabilities through normal .NET APIs. Blazor Hybrid apps can also share and reuse components with existing Blazor Server or Blazor WebAssembly apps. Blazor Hybrid apps combine the benefits of the web, native apps, and the .NET platform.

The Blazor Hybrid hosting model offers several benefits:

- Reuse existing components that can be shared across mobile, desktop, and web.
- Leverage web development skills, experience, and resources.
- Apps have full access to the native capabilities of the device.

The Blazor Hybrid hosting model has the following limitations:

- Separate native client apps must be built, deployed, and maintained for each target platform.
- Native client apps usually take longer to find, download, and install over accessing a web app in a browser.

For more information, see [ASP.NET Core Blazor Hybrid](https://learn.microsoft.com/en-us/aspnet/core/blazor/hybrid/?view=aspnetcore-8.0).

For more information on Microsoft native client frameworks, see the following resources:

- [.NET Multi-platform App UI (.NET MAUI)](https://learn.microsoft.com/en-us/dotnet/maui/what-is-maui)
- [Windows Presentation Foundation (WPF)](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/overview/)
- [Windows Forms](https://learn.microsoft.com/en-us/dotnet/desktop/winforms/overview/)

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#which-blazor-hosting-model-should-i-choose)

## Which Blazor hosting model should I choose?

A component's hosting model is set by its _render mode_, either at compile time or runtime, which is described with examples in [ASP.NET Core Blazor render modes](https://learn.microsoft.com/en-us/aspnet/core/blazor/components/render-modes?view=aspnetcore-8.0). The following table shows the primary considerations for setting the render mode to determine a component's hosting model. For standalone Blazor WebAssembly apps, all of the app's components are rendered on the client with the Blazor WebAssembly hosting model.

Blazor Hybrid apps include .NET MAUI, WPF, and Windows Forms framework apps.

|Feature|Blazor Server|Blazor WebAssembly (WASM)|Blazor Hybrid|
|---|---|---|---|
|[Complete .NET API compatibility](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#complete-net-api-compatibility)|✔️Supported|❌Not supported|✔️Supported|
|[Direct access to server and network resources](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#direct-access-to-server-and-network-resources)|✔️Supported|❌Not supported†|❌Not supported†|
|[Small payload size with fast initial load time](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#small-payload-size-with-fast-initial-load-time)|✔️Supported|❌Not supported|❌Not supported|
|[Near native execution speed](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#near-native-execution-speed)|✔️Supported|✔️Supported‡|✔️Supported|
|[App code secure and private on the server](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#app-code-secure-and-private-on-the-server)|✔️Supported|❌Not supported†|❌Not supported†|
|[Run apps offline once downloaded](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#run-apps-offline-once-downloaded)|❌Not supported|✔️Supported|✔️Supported|
|[Static site hosting](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#static-site-hosting)|❌Not supported|✔️Supported|❌Not supported|
|[Offloads processing to clients](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#offloads-processing-to-clients)|❌Not supported|✔️Supported|✔️Supported|
|[Full access to native client capabilities](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#full-access-to-native-client-capabilities)|❌Not supported|❌Not supported|✔️Supported|
|[Web-based deployment](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#web-based-deployment)|✔️Supported|✔️Supported|❌Not supported|

†Blazor WebAssembly and Blazor Hybrid apps can use server-based APIs to access server/network resources and access private and secure app code.  
‡Blazor WebAssembly only reaches near-native performance with [ahead-of-time (AOT) compilation](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#ahead-of-time-aot-compilation).

After you choose the app's hosting model, you can generate a Blazor Server or Blazor WebAssembly app from a Blazor project template. For more information, see [Tooling for ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/tooling?view=aspnetcore-8.0#blazor-template-options).

To create a Blazor Hybrid app, see the articles under [ASP.NET Core Blazor Hybrid tutorials](https://learn.microsoft.com/en-us/aspnet/core/blazor/hybrid/tutorials/?view=aspnetcore-8.0).

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#complete-net-api-compatibility)

### Complete .NET API compatibility

Components rendered for the Blazor Server hosting model and Blazor Hybrid apps have complete .NET API compatibility, while components rendered for Blazor WebAssembly are limited to a [subset of .NET APIs](https://learn.microsoft.com/en-us/aspnet/core/blazor/fundamentals/?view=aspnetcore-8.0#subset-of-net-apis-for-blazor-webassembly-apps). When an app's specification requires one or more .NET APIs that are unavailable to WebAssembly-rendered components, then choose to render components for Blazor Server or use Blazor Hybrid.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#direct-access-to-server-and-network-resources)

### Direct access to server and network resources

Components rendered for the Blazor Server hosting model have direct access to server and network resources where the app is executing. Because components hosted using Blazor WebAssembly or Blazor Hybrid execute on a client, they don't have direct access to server and network resources. Components can access server and network resources _indirectly_ via protected server-based APIs. Server-based APIs might be available via third-party libraries, packages, and services. Take into account the following considerations:

- Third-party libraries, packages, and services might be costly to implement and maintain, weakly supported, or introduce security risks.
- If one or more server-based APIs are developed internally by your organization, additional resources are required to build and maintain them.

Use the Blazor Server hosting model to avoid the need to expose APIs from the server environment.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#small-payload-size-with-fast-initial-load-time)

### Small payload size with fast initial load time

Rendering components from the server reduces the app payload size and improves initial load times. When a fast initial load time is desired, use the Blazor Server hosting model or consider static server-side rendering.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#near-native-execution-speed)

### Near native execution speed

Blazor Hybrid apps run using the .NET runtime natively on the target platform, which offers the best possible speed.

Components rendered for the Blazor WebAssembly hosting model, including Progressive Web Apps (PWAs), and standalone Blazor WebAssembly apps run using the .NET runtime for WebAssembly, which is slower than running directly on the platform. Consider using [ahead-of-time (AOT) compiled](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?view=aspnetcore-8.0#ahead-of-time-aot-compilation) to improve runtime performance when using Blazor WebAssembly.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#app-code-secure-and-private-on-the-server)

### App code secure and private on the server

Maintaining app code securely and privately on the server is a built-in feature of components rendered for the Blazor Server hosting model. Components rendered using the Blazor WebAssembly or Blazor Hybrid hosting models can use server-based APIs to access functionality that must be kept private and secure. The considerations for developing and maintaining server-based APIs described in the [Direct access to server and network resources](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#direct-access-to-server-and-network-resources) section apply. If the development and maintenance of server-based APIs isn't desirable for maintaining secure and private app code, render components for the Blazor Server hosting model.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#run-apps-offline-once-downloaded)

### Run apps offline once downloaded

Standalone Blazor WebAssembly apps built as Progressive Web Apps (PWAs) and Blazor Hybrid apps can run offline, which is particularly useful when clients aren't able to connect to the Internet. Components rendered for the Blazor Server hosting model fail to run when the connection to the server is lost. If an app must run offline, standalone Blazor WebAssembly and Blazor Hybrid are the best choices.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#static-site-hosting)

### Static site hosting

Static site hosting is possible with standalone Blazor WebAssembly apps because they're downloaded to clients as a set of static files. Standalone Blazor WebAssembly apps don't require a server to execute server-side code in order to download and run and can be delivered via a [Content Delivery Network (CDN)](https://developer.mozilla.org/docs/Glossary/CDN) (for example, [Azure CDN](https://azure.microsoft.com/services/cdn/)).

Although Blazor Hybrid apps are compiled into one or more self-contained deployment assets, the assets are usually provided to clients through a third-party app store. If static hosting is an app requirement, select standalone Blazor WebAssembly.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#offloads-processing-to-clients)

### Offloads processing to clients

Blazor WebAssembly and Blazor Hybrid apps execute on clients and thus offload processing to clients. Blazor Server apps execute on a server, so server resource demand typically increases with the number of users and the amount of processing required per user. When it's possible to offload most or all of an app's processing to clients and the app processes a significant amount of data, Blazor WebAssembly or Blazor Hybrid is the best choice.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#full-access-to-native-client-capabilities)

### Full access to native client capabilities

Blazor Hybrid apps have full access to native client API capabilities via .NET native app frameworks. In Blazor Hybrid apps, Razor components run directly in the native app, not on [WebAssembly](https://developer.mozilla.org/docs/WebAssembly). When full client capabilities are a requirement, Blazor Hybrid is the best choice.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#web-based-deployment)

### Web-based deployment

Blazor web apps are updated on the next app refresh from the browser.

Blazor Hybrid apps are native client apps that typically require an installer and platform-specific deployment mechanism.

[](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?view=aspnetcore-8.0#setting-a-components-hosting-model)

## Setting a component's hosting model

To set a component's hosting model to Blazor Server or Blazor WebAssembly at compile-time or dynamically at runtime, you set its _render mode_. Render modes are fully explained and demonstrated in the [ASP.NET Core Blazor render modes](https://learn.microsoft.com/en-us/aspnet/core/blazor/components/render-modes?view=aspnetcore-8.0) article. We don't recommend that you jump from this article directly to the _Render modes_ article without reading the content in the articles between these two articles. For example, render modes are more easily understood by looking at Razor component examples, but basic Razor component structure and function isn't covered until the [ASP.NET Core Blazor fundamentals](https://learn.microsoft.com/en-us/aspnet/core/blazor/fundamentals/?view=aspnetcore-8.0) article is reached. It's also helpful to learn about Blazor's project templates and tooling before working with the component examples in the _Render modes_ article.

Collaborate with us on GitHub

The source for this content can be found on GitHub, where you can also create and review issues and pull requests. For more information, see [our contributor guide](https://learn.microsoft.com/contribute/content/dotnet/dotnet-contribute).

![](https://learn.microsoft.com/media/logos/logo_net.svg)

ASP.NET Core feedback

ASP.NET Core is an open source project. Select a link to provide feedback:

[Open a documentation issue](https://github.com/dotnet/aspnetcore.docs/issues/new?template=customer-feedback.yml&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Faspnet%2Fcore%2Fblazor%2Fhosting-models%3Fview%3Daspnetcore-8.0&pageQueryParams=%3Fview%3Daspnetcore-8.0&contentSourceUrl=https%3A%2F%2Fgithub.com%2Fdotnet%2FAspNetCore.Docs%2Fblob%2Fmain%2Faspnetcore%2Fblazor%2Fhosting-models.md&documentVersionIndependentId=72c2a844-ffb2-4799-2c7a-a7a73d3b6833&feedback=%0A%0A%5BEnter+feedback+here%5D%0A&author=%40guardrex&metadata=*+ID%3A+542f38c4-1502-f739-372a-80c86c377491+%0A*+Service%3A+**aspnet-core**%0A*+Sub-service%3A+**blazor**&labels=Source+-+Docs.ms%2C%3Awatch%3A+Not+Triaged) [Provide product feedback](https://github.com/dotnet/aspnetcore/blob/main/CONTRIBUTING.md)

---

## Additional resources

Documentation

- [ASP.NET Core Blazor project structure](https://learn.microsoft.com/en-us/aspnet/core/blazor/project-structure?source=recommendations)
    
    Learn about ASP.NET Core Blazor app project structure.
    
- [Tooling for ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/tooling?source=recommendations)
    
    Learn about the tools available to build Blazor apps and how to use them.
    
- [ASP.NET Core Blazor WebAssembly build tools and ahead-of-time (AOT) compilation](https://learn.microsoft.com/en-us/aspnet/core/blazor/webassembly-build-tools-and-aot?source=recommendations)
    
    Learn about the WebAssembly build tools and how to compile a Blazor WebAssembly app ahead of deployment with ahead-of-time (AOT) compilation.
    
- [ASP.NET Core Blazor fundamentals](https://learn.microsoft.com/en-us/aspnet/core/blazor/fundamentals/?source=recommendations)
    
    Learn foundational concepts of the Blazor application framework.
    
- [ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/?source=recommendations)
    
    Explore ASP.NET Core Blazor, a way to build interactive client-side web UI with .NET in an ASP.NET Core app.
    
- [ASP.NET Core Blazor supported platforms](https://learn.microsoft.com/en-us/aspnet/core/blazor/supported-platforms?source=recommendations)
    
    Learn about the supported platforms for ASP.NET Core Blazor.
    
- [Build a Blazor todo list app](https://learn.microsoft.com/en-us/aspnet/core/blazor/tutorials/build-a-blazor-app?source=recommendations)
    
    Build a Blazor app step-by-step.
    
- [ASP.NET Core Blazor render modes](https://learn.microsoft.com/en-us/aspnet/core/blazor/components/render-modes?source=recommendations)
    
    Learn about Blazor render modes and how to apply them in Blazor Web Apps.
---

# ASP.NET Core Blazor tutorials

- Article
- 08/26/2024

The following tutorials provide basic working experiences for building Blazor apps.

For an overview of Blazor, see [ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/?view=aspnetcore-8.0).

- [Build your first Blazor app](https://dotnet.microsoft.com/learn/aspnet/blazor-tutorial/intro)
    
- [Build a Blazor todo list app](https://learn.microsoft.com/en-us/aspnet/core/blazor/tutorials/build-a-blazor-app?view=aspnetcore-8.0) (Blazor Web App)
    
- [Build a Blazor movie database app (Overview)](https://learn.microsoft.com/en-us/aspnet/core/blazor/tutorials/movie-database-app/?view=aspnetcore-8.0) (Blazor Web App)
    
- [Use ASP.NET Core SignalR with Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/tutorials/signalr-blazor?view=aspnetcore-8.0) (Blazor Web App)
    
- [ASP.NET Core Blazor Hybrid tutorials](https://learn.microsoft.com/en-us/aspnet/core/blazor/hybrid/tutorials/?view=aspnetcore-8.0)
    
- Microsoft Learn
    
    - [Blazor Learning Path](https://learn.microsoft.com/en-us/training/paths/build-web-apps-with-blazor/)
    - [Blazor Learn Modules](https://learn.microsoft.com/en-us/training/browse/?expanded=dotnet&products=blazor)

Collaborate with us on GitHub

The source for this content can be found on GitHub, where you can also create and review issues and pull requests. For more information, see [our contributor guide](https://learn.microsoft.com/contribute/content/dotnet/dotnet-contribute).

![](https://learn.microsoft.com/media/logos/logo_net.svg)

ASP.NET Core feedback

ASP.NET Core is an open source project. Select a link to provide feedback:

[Open a documentation issue](https://github.com/dotnet/aspnetcore.docs/issues/new?template=customer-feedback.yml&pageUrl=https%3A%2F%2Flearn.microsoft.com%2Fen-us%2Faspnet%2Fcore%2Fblazor%2Ftutorials%2F%3Fview%3Daspnetcore-8.0&pageQueryParams=%3Fview%3Daspnetcore-8.0&contentSourceUrl=https%3A%2F%2Fgithub.com%2Fdotnet%2FAspNetCore.Docs%2Fblob%2Fmain%2Faspnetcore%2Fblazor%2Ftutorials%2Findex.md&documentVersionIndependentId=1a2f2ad2-3a29-a5cc-a7aa-1003f7588a8a&feedback=%0A%0A%5BEnter+feedback+here%5D%0A&author=%40guardrex&metadata=*+ID%3A+1a2f2ad2-3a29-a5cc-a7aa-1003f7588a8a+%0A*+Service%3A+**aspnet-core**%0A*+Sub-service%3A+**blazor**&labels=Source+-+Docs.ms%2C%3Awatch%3A+Not+Triaged) [Provide product feedback](https://github.com/dotnet/aspnetcore/blob/main/CONTRIBUTING.md)

---

## Additional resources

Documentation

- [ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/?source=recommendations)
    
    Explore ASP.NET Core Blazor, a way to build interactive client-side web UI with .NET in an ASP.NET Core app.
    
- [Build a Blazor todo list app](https://learn.microsoft.com/en-us/aspnet/core/blazor/tutorials/build-a-blazor-app?source=recommendations)
    
    Build a Blazor app step-by-step.
    
- [ASP.NET Core Series: Blazor](https://learn.microsoft.com/en-us/shows/on-dotnet/aspnet-core-series-blazor?source=recommendations)
    
    ASP.NET Core is our open-source, cross-platform framework for building modern, cloud-enabled, Internet-connected apps. In this series of videos we'll be cover many of the interesting features of the framework.There's been ton of interest about Blazor in the community. In the episode, Dan Roth joins Jeremy to talk about how you can do Blazor on the server and in the web browser. Useful Links[01:10] - What is Blazor?[03:36] - What's the different between Blazor server and Blazor WebAssembly[07:
    
- [ASP.NET Core Blazor supported platforms](https://learn.microsoft.com/en-us/aspnet/core/blazor/supported-platforms?source=recommendations)
    
    Learn about the supported platforms for ASP.NET Core Blazor.
    
- [Full stack web UI with Blazor in .NET 8](https://learn.microsoft.com/en-us/shows/dotnetconf-2023/full-stack-web-ui-with-blazor-in-dotnet-8?source=recommendations)
    
    In .NET 8 you can deliver the best web app experiences entirely in Blazor using Blazor's convenient component model. You can build your entire web app in Blazor without the need for writing JavaScript or mixing web frameworks. In this session, you'll see how you can use Blazor's new server-side rendering support to power your web apps from the server for maximum performance and scalability. You'll see how you can easily add advanced capabilities like streaming rendering and enhanced navigation & form ha
    
- [Choose an ASP.NET Core UI](https://learn.microsoft.com/en-us/aspnet/core/tutorials/choose-web-ui?source=recommendations)
    
    Learn when to use which ASP.NET Core web UI technologies. Understand the server, client and hybrid options.
    
- [ASP.NET Core Blazor hosting models](https://learn.microsoft.com/en-us/aspnet/core/blazor/hosting-models?source=recommendations)
    
    Learn about Blazor hosting models and how to pick which one to use.
    
- [Tooling for ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/tooling?source=recommendations)
    
    Learn about the tools available to build Blazor apps and how to use them.
    

Training

Learning path

[Build web apps with Blazor learning path - Training](https://learn.microsoft.com/en-us/training/paths/build-web-apps-with-blazor/?source=recommendations)

Learn how to build your first web app with the free and open-source Blazor web user-interface framework.

Certification

[Microsoft Certified: Azure Developer Associate - Certifications](https://learn.microsoft.com/en-us/credentials/certifications/azure-developer/?source=recommendations)

Build end-to-end solutions in Microsoft Azure to create Azure Functions, implement and manage web apps, develop solutions utilizing Azure storage, and more.

---

[[Build your first web app with ASPNET Core using Blazor]]
