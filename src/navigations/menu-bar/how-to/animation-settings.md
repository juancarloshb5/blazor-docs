---
title: "Animation Settings"
component: "Menu Bar"
description: "This section helps to learn how to change the animations of menu bar."
---

# Change animation settings

To change the animation of the Menu Bar, [`AnimationSettings`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.SfMenu.html#Syncfusion_Blazor_Navigations_SfMenu_AnimationSettings) property is used. The supported effects for Menu Bar are,

| Effect | Functionality |
| ------------ | ----------------------- |
| None | Specifies the sub menu transform with no animation effect. |
| SlideDown | Specifies the sub menu transform with slide down effect. |
| ZoomIn | Specifies the sub menu transform with zoom in effect. |
| FadeIn | Specifies the sub menu transform with fade in effect. |

The following sample illustrates how to open Menu with `FadeIn` [`effect`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.MenuAnimationSettingsModel.html#Syncfusion_Blazor_Navigations_MenuAnimationSettingsModel_Effect) with the [`Duration`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.MenuAnimationSettingsModel.html#Syncfusion_Blazor_Navigations_MenuAnimationSettingsModel_Duration) of `400ms`. Also we can set [`Easing`](https://help.syncfusion.com/cr/blazor/Syncfusion.Blazor.Navigations.MenuAnimationSettingsModel.html#Syncfusion_Blazor_Navigations_MenuAnimationSettingsModel_Easing) for menu items.

```csharp
@using Syncfusion.Blazor.Navigations

<SfMenu Items="@MenuItems">
    <MenuAnimationSettings Effect = "MenuEffect.FadeIn" Duration = "400"></MenuAnimationSettings>
</SfMenu>

@code {
    public List<MenuItem> MenuItems = new List<MenuItem>{
        new MenuItem { Text = "File", Items = new List<MenuItem>{
            new MenuItem{ Text = "Open" },
            new MenuItem{ Text = "Save" },
            new MenuItem{ Text = "Exit" } } },
        new MenuItem { Text = "Edit", Items = new List<MenuItem>{
            new MenuItem{ Text = "Cut" },
            new MenuItem{ Text = "Copy" },
            new MenuItem{ Text = "Paste" } } },
        new MenuItem { Text = "View", Items = new List<MenuItem>{
            new MenuItem{ Text = "Toolbar" },
            new MenuItem{ Text = "Sidebar" },
            new MenuItem{ Text = "Fullscreen" } } },
        new MenuItem { Text = "Tools", Items = new List<MenuItem>{
            new MenuItem{ Text = "Spelling & Grammer" },
            new MenuItem{ Text = "Customize" },
            new MenuItem{ Text = "Options" } } },
    };
}
```

Output be like

![Menu Sample](./../images/menu-animation.png)
