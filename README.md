PushSharpHttpTwo - PushSharp updated version!
==============

PushSharp is a GREAT server-side library for sending Push Notifications to iOS/OSX (APNS), Android/Chrome (GCM/FCM), Windows/Windows Phone, Amazon (ADM) and Blackberry devices -> https://github.com/Redth/PushSharp

And PushSharpHttpTwo is updated version of PushSharp to send push notifications over Http/2 to solve iOS13 & Xcode11 problem. To see more about problem -> https://onesignal.com/blog/ios-13-introduces-4-breaking-changes-to-notifications/

This library is making push service calls over Http/2 and adding some headers for iOS13 & Xcode11 want us to do.

### What is different?

in ApnsHttp2Connection.cs:

```csharp
if ((string.IsNullOrEmpty(notification.PushType)))
{
    notification.PushType = "background";
}
headers.Add("apns-push-type", notification.PushType); 
headers.Add ("apns-priority", notification.Priority == ApnsPriority.Low ? "5" : "10"); // 5 or 10
