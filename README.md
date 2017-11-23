# WpfLocalization

This project provides a simple, yet powerful and feature-rich way to localize a WPF application. It is focused on 
simplicity and easy-of-use and is an alternative to the WPF localization method provided by Microsoft.

The project is a replacement (a complete rewrite and redesign) of an earlier localization solution posted on 
CodeProject in 2009 - [Advanced WPF Localization](https://www.codeproject.com/Articles/249369/Advanced-WPF-Localization).


## Basic usage

*Please refer to the [Wiki](https://github.com/JechoJekov/WpfLocalization/wiki/) for complete feature list and examples. 
This section describes basic usage only.*

1. Install the WpfLocaliation package from [NuGet](https://www.nuget.org/packages/WpfLocalization)
2. Create a default resource file in your project
  * Go to Solution Explorer - Project -> Properties -> Resources and create a new file
  * OR [C#] Create `Resources.resx` file in the `Properties` project folder
  * OR [VB.NET] Create `Resources.resx` file in the `My Project` project folder
3. Use the `Loc` XAML extension in your application.

```XAML
<Window ...>
  ...
  <TextBlock Text="{Loc Text_HelloWorld}"/>
  ...
  <-- Localize bindings -->
  <TextBlock Text="{Loc Text_HelloUserName, Binding={Binding UserName}}"/>
  ...
  <!-- Localize multi-bindings -->
  <TextBlock>
    <TextBlock.Text>
      <Loc Key="Text_HelloPersonalName">
        <Binding Path="FirstName"/>
        <Binding Path="LastName"/>
      </Loc>
    </TextBlock.Text>
  </TextBlock>
  ...
  <!-- Localize date/time, number and currency formatting even if there is no localized resource -->
  <TextBlock Text="{Loc StringFormat='{}{0:d}', Binding={Binding BirthDate}}"/>
  ...
  <!-- Localize date/time, number and currency formatting inside localized text -->
  <TextBlock Text="{Loc Text_BirthDate, Binding={Binding BirthDate}}"/>
  ...
</Window>
```

4. Add localized values to the resource file.

Name | Value
---- | -----
... | ...
Text_HelloWorld | Welcome to WPF localization!
Text_HelloUserName | Hello {0}!
Text_HelloPersonalName | Hello {0} {1}!
Text_BirthDate | Your birth date is {0:d}.
... | ...

5. Add culture-specific resource files (e.g. `Resources.de.resx`, `Resources.fr-FR.resx`) and localize the values

*Resources.de.resx*

Name | Value
---- | -----
... | ...
Text_HelloWorld | Willkommen bei der WPF localization!
Text_HelloUserName | Hallo {0}!
Text_HelloPersonalName | Hallo {0} {1}!
Text_BirthDate | Dein Geburtsdatum ist {0:d}.
... | ...

*Resources.fr-FR.resx*

Name | Value
---- | -----
... | ...
Text_HelloWorld | Bienvenue dans la WPF localization!
Text_HelloUserName | Bonjour {0}!
Text_HelloPersonalName | Bonjour {0} {1}!
Text_BirthDate | Votre date de naissance est le {0:d}.
... | ...


## Overall list of features

*Please refer to the [Wiki](https://github.com/JechoJekov/WpfLocalization/wiki/) for a complete feature list and examples.*

* Both dependency and non-dependency properties
* Any data type for which there is a `TypeConverter` (including images, icons, fonts, colors, enumerations, margins, etc.)
* Bindings
* Templates
* Styles (including setters)
* User controls
* Custom controls (both in themes and in code-behind)
* Code-behind
* Multiple resource files located in any project (assembly)
* Mix multiple languages inside the same control, window or different windows
* Multiple UI threads
* High-performance (important for applications that utilize data grids or other demanding data controls)
* Supports WPF designer in Visual Studio 2013/2015/2017


## Documentation

[Wiki](https://github.com/JechoJekov/WpfLocalization/wiki/)  
[Code Project](https://www.codeproject.com/Articles/xxxxxx/Ultimate-WPF-Localization)


## Sample project

[C# - WpfLocalization.Demo](https://github.com/JechoJekov/WpfLocalization/tree/master/Project/WpfLocalization.Demo)  
[VB.NET - WpfLocalization.VBDemo](https://github.com/JechoJekov/WpfLocalization/tree/master/Project/WpfLocalization.VBDemo)

## License

Public Domain - [Unlicense](http://unlicense.org/)


## NuGet package

https://www.nuget.org/packages/WpfLocalization