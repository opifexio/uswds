# USWDS Razor Class Library (RCL)

This project is a .NET Razor class library (RCL) that contains references for ditributable USWDS static assets such as CSS and JS files.

While other integrations for USWDS do exist, there isn't an easy way to reference it in a .NET Blazor app without significant overhead. This package provides a quick and easy reference to include the `dist` folder of the USWDS build in your Razor/Blazor projects.

Currently, its use has only been tested with Blazor Client projects, i.e. `blazorwasm`, but it only includes static assets, and can potentially be included in any other type of project that can leverage [Razor class libraries](https://docs.microsoft.com/en-us/aspnet/core/razor-pages/ui-class?view=aspnetcore-6.0&tabs=visual-studio).

The versioning for this library follows the **major and minor** [release versions of USWDS](https://github.com/uswds/uswds/releases). Patch versions may differ and suffixes may be added in case siginificant breaking changes need to be addressed.

### Getting started
1. Install the package on your project by using the NuGet package manager using your tool of choice. Methods to install are listed on the [NuGet page](https://www.nuget.org/packages/Opifex.Uswds) for the project.

2. Include references to the CSS and JS files as described in the [Documentation](https://designsystem.digital.gov/documentation/developers/) as described in the section *Using USWDS CSS and JavaScript in your project*.

    Instead of using the path `assets/uswds/dist/` as specified in the documentation, you will be using the path `_content/Opifex.Uswds/` to retrieve the various resources.

    So the a minimal `index.html` file would look like:

    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8" />
        <meta http-equiv="X-UA-Compatible" content="IE=edge" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>My Example Project</title>
        <script src="_content/Opifex.Uswds/js/uswds-init.min.js"></script>
        <link rel="stylesheet" href="_content/Opifex.Uswds/css/uswds.min.css" />
    </head>
    <body>
        <script src="_content/Opifex.Uswds/js/uswds.min.js"></script>
    </body>
    </html>
    ```

    This is a consequence of how static assets are packaged in an RCL. To read more about this, see [Consume content from a referenced RCL](https://docs.microsoft.com/en-us/aspnet/core/razor-pages/ui-class?view=aspnetcore-6.0&tabs=visual-studio#consume-content-from-a-referenced-rcl).

For a more in-depth understanding of how to integrate it with a Blazor Client project, see the [landing page sample project](/samples/LandingPageSample/), which was adapted from the [landing page template](https://designsystem.digital.gov/templates/landing-page/).

### Contributing
Please follow GitHub community guidelines and contribute by opening issues or pull requests accordingly. 






