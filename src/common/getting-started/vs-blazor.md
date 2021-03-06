<!-- markdownlint-disable MD024 -->

# Getting started with Syncfusion Blazor - WebAssembly App in Visual Studio 2019

This article provides a step-by-step introduction to configure Syncfusion Blazor setup, build and run a simple Blazor WebAssembly application using [Visual Studio 2019](https://visualstudio.microsoft.com/vs/).

> **Note:** Starting with version 17.4.0.39 (2019 Volume 4), you need to include a valid license key (either paid or trial key) within your applications. Please refer to this [help topic](https://help.syncfusion.com/common/essential-studio/licensing/license-key#blazor) for more information.

## Prerequisites

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [.NET Core SDK 3.1.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

> **Note:** .NET Core 3.1 requires Visual Studio 2019 16.4 or later.

## Create a Blazor WebAssembly project in Visual Studio 2019

1. Install the essential project templates in the Visual Studio 2019 by running the below command line in the command prompt.

    ```bash
    dotnet new -i Microsoft.AspNetCore.Blazor.Templates::3.2.0-preview1.20073.1
    ````

2. Choose **Create a new project** from the Visual Studio dashboard.

    ![new project in aspnetcore blazor](images/new-project.png)

3. Select **Blazor App** from the template and click **Next** button.

    ![blazor template](images/blazor-template.png)

4. Now, the project configuration window will popup. Click **Create** button to create a new project with the default project configuration.

    ![asp.net core project configuration](images/project-configuration.png)

5. Choose **Blazor WebAssembly App** from the dashboard and click **Create** button to create a new Blazor WebAssembly application. Make sure **.NET Core** and **ASP.NET Core 3.1** are selected at the top.

    ![select framework](images/blazor-client-template.png)

    > **Note:** ASP.NET Core 3.1 available in Visual Studio 2019 version.
  
## Importing Syncfusion Blazor component in the application

1. Now, install **Syncfusion.EJ2.Blazor** NuGet package to the newly created application by using the `NuGet Package Manager`. Right-click the project and select Manage NuGet Packages.

    ![nuget explorer](images/nuget-explorer.png)

2. Search **Syncfusion.EJ2.Blazor** keyword in the Browse tab and install **Syncfusion.EJ2.Blazor** NuGet package in the application.

    ![select nuget](images/select-nuget.png)

3. The Syncfusion Blazor package will be installed in the project, once the installation process is completed.

4. Open **~/_Imports.razor** file and import the `Syncfusion.EJ2.Blazor`.

    ```csharp
    @using Syncfusion.EJ2.Blazor
    @using Syncfusion.EJ2.Blazor.Calendars
    ```

5. Open the **~/Program.cs** file and register the Syncfusion Blazor Service.

    ```csharp
    using Syncfusion.EJ2.Blazor;

    namespace WebApplication1
    {
        public class Program
        {
            public static async Task Main(string[] args)
            {
                ....
                ....
                builder.Services.AddSyncfusionBlazor();
                await.builder.Build.RunAsync();
            }
        }
    }
    ```

6. Add the client-side resource through CDN or local npm package in the `<head>` element of the **~/wwwroot/index.html** page.

    ```html
    <head>
        ....
        ....
  
        <link href="https://cdn.syncfusion.com/ej2/{:version:}/material.css" rel="stylesheet" />
        <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ej2.min.js"></script>
        <script src="https://cdn.syncfusion.com/ej2/{:version:}/dist/ejs.interop.min.js"></script>
    </head>
    ```

    > **Note:** For production purpose and minimal requirement, Syncfusion provides an option to generate scripts and styles of selective control by using the Custom Resource Generator ([CRG](https://crg.syncfusion.com/)) web tool. Refer to this help documentation [link](../common/custom-resource-generator) for more details on CRG.

7. Now, add the Syncfusion Blazor components in any web page (razor) in the `Pages` folder. For example, the calendar component is added in the **~/Pages/Index.razor** page.

    ```csharp
    <EjsCalendar TValue="DateTime"></EjsCalendar>
    ```

8. Run the application. The Syncfusion Blazor Calendar component will render in the web browser.

    ![output](images/browser-output.png)
