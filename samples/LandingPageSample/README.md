# Landing Page Sample

This sample project has been scaffolded as a Blazor WebAssembly project. The following is a walkthrough of how this project was setup.

### Tutorial

Create a new project by running the following command:

```dotnetcli
dotnet new blazorwasm -o LandingPageSample
```

Install the `Opifex.Uswds` package by running:
```dotnetcli
dotnet add package Opifex.Uswds
```
This will download and install the package, while also updating `LandingPageSample.csproj` with the following element:
```xml
<ItemGroup>
    ...
    <PackageReference Include="Opifex.Uswds" Version="3.1.0" />
</ItemGroup>
```

Update [`index.html`](wwwroot/index.html) with the following code:
```html
<!DOCTYPE html>
<html lang="en">

<head>
    ...
    <script src="_content/Opifex.Uswds/js/uswds-init.min.js"></script>
    <link href="_content/Opifex.Uswds/css/uswds.min.css" rel="stylesheet" />
</head>

<body>
    ...
    <script src="_content/Opifex.Uswds/js/uswds.min.js"></script>
    ...
</body>

</html>
```
Extract the header and footer from the [landing page](https://designsystem.digital.gov/templates/landing-page/), and then update [`Shared\MainLayout.razor`](Shared/MainLayout.razor) with the header and footer elements, while maintaining the `main` section as follows:
```html
...
<main id="main-content">
    @Body
</main>
...
```
Finally, update [`Pages\Index.razor`](Pages/Index.razor) with the various `<section>` content elements from the [landing page](https://designsystem.digital.gov/templates/landing-page/), that are not part of the header and footer.

> **NOTE:** For both `Pages\Index.razor` and `Shared\MainLayout.razor` remember to update all the references to images from `assets/img` to `_content/Opifex.Uswds/img`. 

If desired, clean up any extraneous files that are unused.

To validate the look and feel run:
```dotnetcli
dotnet run
```
Open the browser and navigate to https://localhost:7088. The landing page should render as expected.

If you have any problems with this tutorial, please open an [issue](https://github.com/pkothare/opifex-uswds/issues).


