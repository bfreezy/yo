# yo


## Custom User Notifications with Swift

### Overview
```yo``` is a simple app for sending custom notifications to the Notification Center in OS X Yosemite. It allows customizing the various text fields and button labels, as well as the application to open when the (optional) action button has been clicked.

It differs from [terminal-notifier](https://github.com/alloy/terminal-notifier) in that it creates persistent (alert, rather than banner) notifications that remain in place until clicked. Also, as an alert, it gives you the option of customizing the clickable buttons.

### Build & Installation
1. Clone the project.
2. Open the project in XCode and set the App Icon to your desired icon. See the Icon section below for more info on this.
3. Build.
4. Copy the built app (Contextual-click on the Products->yo.app->Show in Finder) wherever you see fit, although ```/Applications/Utilities``` seems like a suitable place.

### Usage
You must call the app from commandline, from the actual binary inside. Feel free to alias or ln to this file to avoid the long filename in the future.

```
Usage: /Applications/Utilities/yo.app/Contents/MacOS/yo [options]
  -t, --title:
      Title for notification
  -s, --subtitle:
      Subtitle for notification
  -i, --itext:
      Informative text.
  -b, --btext:
      Action button text.
  -o, --obtext:  
      Alternate label for cancel button text.
  -a, --action:  
      Application to open if user selects the action button. Provide the full path as the argument.
```

Notes:
- Title is mandatory. All other arguments are optional.
- The action argument needs a path or ULR. yo just calls ```open```, so anything that would work there, should work here.

### Example
```
# /Applications/Utilities/yo.app/Contents/MacOS/yo -t "Taco Time" -b "Yum" -a "http://en.wikipedia.org/wiki/Taco"
```