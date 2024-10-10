## Intro

### Purpose

Build your first web app with ASP.NET Core using Blazor.

### Prerequisites

macOS 12.0 or later versions.

### Time to Complete

10-15 minutes + download/installation time

### Scenario

Create, use, and modify a simple counter component.

---

## Download and install

To start building .NET apps, download and install the .NET SDK.

[Download .NET 8 SDK x64 (Intel)](https://download.visualstudio.microsoft.com/download/pr/d6b3fe61-3c0e-45da-9e37-cef64d4fd3eb/28d536e0ecfbb330ab49454a5e3962f6/dotnet-sdk-8.0.403-osx-x64.pkg)

[](https://download.visualstudio.microsoft.com/download/pr/d6b3fe61-3c0e-45da-9e37-cef64d4fd3eb/28d536e0ecfbb330ab49454a5e3962f6/dotnet-sdk-8.0.403-osx-x64.pkg)  
[Download .NET 8 SDK Arm64 (Apple Silicon)](https://download.visualstudio.microsoft.com/download/pr/35b0fb29-cadc-4083-aa26-6cecd2e7ffa1/1a9972a435b73ffdd0b462f979ea5b23/dotnet-sdk-8.0.403-osx-arm64.pkg)

If you're on a Mac with an Apple M1 or M2 chip, you need to install the Arm64 version of the SDK.

### Check everything installed correctly

Once you've installed, open a **new** terminal and run the following command:

Terminal

```
dotnet --version
```

If the installation succeeded, you should see version 8.0.100 or higher outputted:

Terminal

```
8.0.100
```

If everything looks good, select the **Continue** button below to go to the next step.

### Got an error?

If you receive a **zsh: command not found: dotnet** error, make sure you opened a **new** terminal window. If you can't resolve the issue, use the **I ran into an issue** button to get help fixing the problem.


---

## Create your app

In your terminal, run the following command to create your app:

Terminal

```
dotnet new blazor -o BlazorApp
```

This command creates your new Blazor Web App project and places it in a new directory called `BlazorApp` inside your current location.

Navigate to the new `BlazorApp` directory created by the previous command:

Terminal

```
cd BlazorApp
```

Take a quick look at the contents of the `BlazorApp` directory.

Terminal

```
ls
```

Several files were created in the `BlazorApp` directory, to give you a simple Blazor app that is ready to run.

- `Program.cs` is the entry point for the app that starts the server and where you configure the app services and middleware.
- Inside the `Components` directory:
    
    - `App.razor` is the root component for the app.
    - `Routes.razor` configures the Blazor router.
    - The `Pages` directory contains some example web pages for the app.
- `BlazorApp.csproj` defines the app project and its dependencies.
- The `launchSettings.json` file inside the `Properties` directory defines different profile settings for the local development environment. A port number is automatically assigned at project creation and saved on this file.

Take note of the `BlazorApp` directory path as you will use it later in the tutorial.

If everything looks good, select the **Continue** button below to go to the next step.


---

## Run your app

In your terminal, run the following command:

Terminal

```
dotnet watch
```

The `dotnet watch` command will build and start the app, and then update the app whenever you make code changes. You can stop the app at any time by selecting Ctrl+C.

Wait for the app to display that it's listening on `http://localhost:<port number>` and for the browser to launch at that address.

Once you get to the following page, you have successfully run your first Blazor app!

![The home page of your site contains some text and presents several tabs on the left to click and explore.](https://dotnet.microsoft.com/blob-assets/images/tutorials/blazor/screenshot-blazor-tutorial-run.png)

The displayed page is defined by the `Home.razor` file located inside the `Components/Pages` directory. This is what its contents look like:

Components/Pages/Home.razor

```
@page "/"

<PageTitle>Home</PageTitle>

<h1>Hello, world!</h1>

Welcome to your new app.
```

It already contains the code that sets it as the homepage and displays the text `Hello, world!` and `Welcome to your new app`. The `PageTitle` component sets the title for the current page so that it shows up in the browser tab.

---



## Try the counter

In the running app, navigate to the Counter page by clicking the Counter tab in the sidebar on the left. The following page should then be displayed:

![The Counter page presents a Click me button to increment the count showed on the page.](https://dotnet.microsoft.com/blob-assets/images/tutorials/blazor/screenshot-blazor-tutorial-try.png)

Select the **Click me** button to increment the count without a page refresh. Incrementing a counter in a webpage normally requires writing JavaScript, but with Blazor you can use C#.

You can find the implementation of the `Counter` component at `Counter.razor` file located inside the `Components/Pages` directory.

Components/Pages/Counter.razor

```cshtml
@page "/counter"
@rendermode InteractiveServer

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

A request for `/counter` in the browser, as specified by the `@page` directive at the top, causes the `Counter` component to render its content. The `@rendermode` directive enables interactive server rendering for the component, so that it can handle user interface events from the browser.

Each time the **Click me** button is selected:

- The `onclick` event is fired.
- The `IncrementCount` method is called.
- The `currentCount` is incremented.
- The component is rendered to show the updated count.

---

## Add a component

Each of the .razor files defines a UI component that can be reused.

Open the `Home.razor` file in a text editor of your choice. The `Home.razor` file already exists, and it was created when you ran the `dotnet new` command. It's located in the `Components/Pages` folder inside the `BlazorApp` directory that was created earlier.

Add a `Counter` component to the app's homepage by adding a `<Counter />` element at the end of the `Home.razor` file.

Components/Pages/Home.razor

```cshtml
@page "/"

<PageTitle>Home</PageTitle>

<h1>Hello, world!</h1>

Welcome to your new app.

<Counter /> 
```

Once this change is saved, the `dotnet watch` command will apply the change to the running app so that the `Counter` component shows up on the home page.


![[Pasted image 20241010012531.png]]




## Next steps

Congratulations, you've built and run your first Blazor app!

## Keep learning

Now that you've got the basics, continue building your first Blazor app with Blazor self-guided learning module on Microsoft Learn where you will build a to-do list app.

[Microsoft Learn: Build a Blazor todo list app](https://learn.microsoft.com/training/modules/build-blazor-todo-list?WT.mc_id=dotnet-35129-website)

[](https://learn.microsoft.com/training/modules/build-blazor-todo-list?WT.mc_id=dotnet-35129-website)

## Blazor for Beginners

Learn how to build a full Blazor app from start to finish:

[[MS Build a TODO-LIST APP WITH BLAZOR]]