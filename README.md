# q_notifsystem Documentation
A sleek, modern notification system for FiveM with smooth animations and customizable features.

## Preview:
![notifsystempreview](https://github.com/user-attachments/assets/c42e072a-0405-4100-b134-39fc856916ea)

## Table of Contents
- [Installation](#installation)
- [Usage](#usage)
- [API Reference](#api-reference)
- [Examples](#examples)
- [Customization](#customization)
- [Changelog](#changelog)
- [FAQ](#faq)
- [Support](#support)

## Installation

1. Download the resource
2. Place the `q_notifsystem` folder in your server's resources directory
3. Add to your server.cfg:
```cfg
ensure q_notifsystem
```

## Usage

### Basic Usage
```lua
-- Basic notification
exports['q_notifsystem']:Show({
    message = "Hello World"
})

-- Fully customized notification
exports['q_notifsystem']:Show({
    message = "Custom Notification",
    duration = 5000,
    color = "#1e40af",
    icon = "bell",
    opacity = 1.0
})
```

### Command Usage
The system includes a demo command:
```
/demo - Shows different notification styles
```

## API Reference

### Show Function
```lua
exports['q_notifsystem']:Show({
    message = string,  -- Required: Notification message
    duration = number, -- Optional: Duration in ms (default: 4000)
    color = string,   -- Optional: Background color (default: "#1f2937")
    icon = string,    -- Optional: Lucide icon name (default: "check")
    opacity = number  -- Optional: Opacity value 0.0-1.0 (default: 1.0)
})
```

### Parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| message | string | Required | The message to display |
| duration | number | 4000 | Time in milliseconds to show notification |
| color | string | "#1f2937" | Background color in hex format |
| icon | string | "check" | Icon name from lucide.dev |
| opacity | number | 1.0 | Opacity level (0.0 to 1.0) |

## Examples

### Different Types of Notifications
```lua
-- Success Notification
exports['q_notifsystem']:Show({
    message = "Action Completed",
    color = "#1f2937",
    icon = "check"
})

-- Warning Notification
exports['q_notifsystem']:Show({
    message = "Low Fuel Warning",
    color = "#854d0e",
    icon = "alert-triangle",
    duration = 5000
})

-- Error Notification
exports['q_notifsystem']:Show({
    message = "Connection Failed",
    color = "#991b1b",
    icon = "alert-octagon",
    duration = 6000
})
```

### Custom Durations
```lua
-- Quick notification (2 seconds)
exports['q_notifsystem']:Show({
    message = "Quick Info",
    duration = 2000
})

-- Extended notification (10 seconds)
exports['q_notifsystem']:Show({
    message = "Important Message",
    duration = 10000
})
```

### Opacity Examples
```lua
-- Semi-transparent notification
exports['q_notifsystem']:Show({
    message = "Subtle Message",
    opacity = 0.8
})

-- More transparent notification
exports['q_notifsystem']:Show({
    message = "Very Subtle Message",
    opacity = 0.5
})
```

## Customization

### Available Icons
All icons from [Lucide Icons](https://lucide.dev) are supported. Some commonly used icons:
- check
- alert-triangle
- alert-octagon
- info
- bell
- shield
- star

### Color Customization
Colors can be specified in any valid CSS color format:
- Hex: "#1f2937"
- RGB: "rgb(31, 41, 55)"
- Named colors: "red", "blue", etc.

## Changelog

### Version 1.0.0 (Current)
- Initial release
- Features:
  - Smooth slide animations
  - Progress bar with timer
  - Customizable colors and icons
  - Opacity control
  - Stacking notifications
  - Dynamic vertical repositioning
  - Lucide icon integration
  - Google Fonts integration (Nunito)

### Planned Features
- Sound effects
- Different animation styles
- Custom themes
- Mobile responsiveness
- Right-to-left (RTL) support
- Queue system for notifications
- Priority system

## FAQ

### Q: Can I modify the styling?
A: Yes, you can modify the HTML and CSS in the `html/index.html` file.

### Q: Which browsers are supported?
A: The system uses modern CSS features and should work in all recent browsers.

### Q: Can I add custom icons?
A: Yes, any icon from lucide.dev can be used by specifying its name in the icon parameter.

### Q: How many notifications can be shown at once?
A: There's no hard limit, but for best visual experience, consider limiting concurrent notifications.

## Support

For support, please:
1. Check the documentation
2. Review the examples
3. Create an issue on the GitHub repository
4. Join our Discord community

---

## Technical Details

### File Structure
```
q_notifsystem/
├── client/
│   └── notification.lua
├── html/
│   └── index.html
└── fxmanifest.lua
```

### Dependencies
- FiveM Client
- Lucide Icons

### Performance
The system is optimized for:
- Smooth animations
- Minimal resource usage
- Efficient DOM updates
- Clean memory management
