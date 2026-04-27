# How-to-create-fully-customizable-tab-headers-in-.NET-MAUI-TabView

**Repository Description**  
This repository contains a .NET MAUI sample application that demonstrates how to create fully customizable tab headers using the Syncfusion MAUI TabView component.

This sample showcases how to customize header text, images, borders, alignment, fonts, colors, and entirely custom header layouts to achieve a polished and professional user interface.

## Project Overview
The purpose of this project is to help developers understand how to build highly customized tab headers in .NET MAUI applications using the Syncfusion TabView component. It demonstrates various customization techniques that enhance visual consistency and improve user experience across mobile and desktop platforms.

## Features
- Customizable tab header text, images, and layouts  
- Visual state customization using `VisualStateManager`  
- Dynamic header text color changes based on tab selection  
- Icon color binding using `FontImageSource`  
- Header border styling with configurable color, thickness, and corner radius  
- Indicator and layout customization (placement, background, and height)  

### Customization Demonstrated
This sample includes the following customization techniques:
1. **Visual state customization**  
   Uses `VisualStateManager` to dynamically change the header text color of each `SfTabItem` based on selection state.
2. **Icon color binding**  
   Applies `FontImageSource` to each `ImageSource` property in `SfTabItem`, binding its color to the tab’s text color for consistent styling.
3. **Border styling**  
   Customizes the tab header area’s border using `TabBarBorderColor`, `TabBarBorderThickness`, and `TabBarCornerRadius`.
4. **Indicator and layout settings**  
   Adjusts `IndicatorPlacement`, `IndicatorBackground`, and `TabBarHeight` to achieve a modern UI.

## Prerequisites
Ensure that the following requirements are met before running this project:
- Visual Studio 2026  
- .NET MAUI workload installed  

## Installation and Running the Application
1. Clone this repository to your local machine.
2. Open the solution file `TabViewHeaderCustomization.sln` in Visual Studio 2026.
3. Restore NuGet packages if prompted.
4. Build and run the project on an Android, iOS, Windows, or MacCatalyst target.

## Code Snippet

To achieve fully customizable tab headers, use the following XAML:

```xml
     <ContentPage.Resources>
    <Style TargetType="tabView:SfTabItem">
        <Setter Property="VisualStateManager.VisualStateGroups">
            <VisualStateGroupList>
                <VisualStateGroup>
                    <VisualState x:Name="NormalFilled" >
                        <VisualState.Setters>
                            <Setter Property="TextColor" Value="#111111" />
                        </VisualState.Setters>
                    </VisualState>
                    <VisualState x:Name="SelectedFilled">
                        <VisualState.Setters>
                            <Setter Property="TextColor" Value="#FFFFFF" />
                        </VisualState.Setters>
                    </VisualState>
                </VisualStateGroup>
            </VisualStateGroupList>
        </Setter>
    </Style>
</ContentPage.Resources>

<tabView:SfTabView x:Name="tabView" IndicatorBackground="SkyBlue" IndicatorPlacement="Fill" TabBarHeight="60" TabBarBackground="Transparent"  TabBarBorderColor="#6A11CB" TabBarBorderThickness="3" Margin="10" TabBarCornerRadius="15" >
    <tabView:SfTabView.Items>
        <tabView:SfTabItem Header="Call" x:Name="callItem"
                       ImagePosition="Left">
            <tabView:SfTabItem.ImageSource>
                <FontImageSource Glyph="ﺶ" x:Name="call"
                               Color="{Binding Source={x:Reference callItem},Path=TextColor}"
                           FontFamily="MaterialDesignIcons"/>
            </tabView:SfTabItem.ImageSource>
            <Grid Padding="16">
                <Label Text="Make and manage calls. View recent calls, dial new numbers, and quickly start a call from your contacts."
          FontSize="16" TextColor="#222" LineBreakMode="WordWrap"/>
            </Grid>
        </tabView:SfTabItem>

        <tabView:SfTabItem Header="Favourite" x:Name="favItem"
                       ImagePosition="Left">
            <tabView:SfTabItem.ImageSource>
                <FontImageSource Glyph="" x:Name="fav"
                           Color="{Binding Source={x:Reference favItem},Path=TextColor}"
                           FontFamily="MaterialDesignIcons"/>
            </tabView:SfTabItem.ImageSource>
            <Grid Padding="16">
                <Label Text="Your favorite contacts and shortcuts. Pin people you reach often for one‑tap calling or messaging."
          FontSize="16" TextColor="#222" LineBreakMode="WordWrap"/>
            </Grid>
        </tabView:SfTabItem>

        <tabView:SfTabItem Header="Contacts" x:Name="contactsItem"
                       ImagePosition="Left">
            <tabView:SfTabItem.ImageSource>
                <FontImageSource Glyph="" x:Name="contacts"
                           Color="{Binding Source={x:Reference contactsItem},Path=TextColor}"
                           FontFamily="MaterialDesignIcons"/>
            </tabView:SfTabItem.ImageSource>
            <Grid Padding="16">
                <Label Text="Browse and manage your contacts. Search, view details, and quickly add or edit entries in your address book."
          FontSize="16" TextColor="#222" LineBreakMode="WordWrap"/>
            </Grid>
        </tabView:SfTabItem>
    </tabView:SfTabView.Items>
</tabView:SfTabView>
```

## Usage
Run the application and interact with the TabView to observe:
- Dynamic styling changes when switching tabs  
- Custom icons and text alignment  
- Header border and indicator behavior  

You can modify the XAML definitions to experiment with layout and visual customization options.

## Documentation
- **General Syncfusion documentation:**  
  https://help.syncfusion.com/
- **.NET MAUI Introduction:**  
  https://help.syncfusion.com/maui/introduction/overview

## Additional Resources
- **TabBar Customization Guide:**  
  https://help.syncfusion.com/maui/tabview/tab-bar-customization

## Troubleshooting
- Ensure the .NET MAUI workload is properly installed.
- Clean and rebuild the solution if build errors occur.
- Verify the target platform is correctly configured.
- Check the Output and Device Log windows for runtime issues.

## Support
For detailed API references, advanced configuration options, and further guidance, refer to the Syncfusion .NET MAUI documentation and customization guides listed above.