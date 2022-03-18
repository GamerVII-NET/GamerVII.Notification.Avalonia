# Avalonia.Notification

Fork of ![this](https://github.com/Enterwell/Wpf.Notifications) repo

---

---

![](https://github.com/AvaloniaCommunity/Avalonia.Notification/blob/master/Images/Avalonia.Notification.gif)

---

For use:

1. Add style in App.xaml

```xml
<Application.Styles>
        ...
        <StyleInclude Source="avares://Avalonia.Notification/Themes/Generic.xaml" />
</Application.Styles>

```

2. Add notification panel in your window

```xml
 <Border Grid.Column="1">
       <controls:NotificationMessageContainer Manager="{Binding Manager}" />
 </Border>
```

3. Bind manager from vm

```cs
 public INotificationMessageManager Manager { get; } = new NotificationMessageManager();
```

4. Run notification

```cs
            this.Manager
                .CreateMessage()
                .Accent("#1751C3")
                .Animates(true)
                .Background("#333")
                .HasBadge("Info")
                .HasMessage(
                    "Update will be installed on next application restart. This message will be dismissed after 5 seconds.")
                .Dismiss().WithButton("Update now", button => { })
                .Dismiss().WithButton("Release notes", button => { })
                .Dismiss().WithDelay(TimeSpan.FromSeconds(5))
                .Queue();
```