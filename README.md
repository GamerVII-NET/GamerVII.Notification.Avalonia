# GamerVII.Notification.Avalonia

---

![image](https://github.com/GamerVII-NET/GamerVII.Notification.Avalonia/assets/111225722/a99d814f-a8c8-46d9-93cd-99fd066695bc)
---

For use:

1. Add style in App.xaml

```xml
<Application.Styles>
        ...
    <StyleInclude Source="avares://GamerVII.Notification.Avalonia/Themes/Generic.xaml" />
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
    .HasMessage("Update will be installed on next application restart. This message will be dismissed after 5 seconds.")
    .Dismiss().WithDelay(TimeSpan.FromSeconds(5))
    .Queue();
```

or

```cs
this.Manager
     .CreateMessage(true, "#D03E3E", "Ошибка", "Укажите наименование клиента" )
     .Dismiss().WithDelay(TimeSpan.FromSeconds(2))
     .Queue();
```
