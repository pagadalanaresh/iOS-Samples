### LazyTableImages ###

===========================================================================
DESCRIPTION:

This sample demonstrates a multi-stage approach to loading and displaying a 
UITableView.  It displays the top paid iPhone apps on Apple's App Store.

It begins by loading the relevant text from the RSS feed so the table can load
as quickly as possible, then downloads the app images for each row asynchronously
so the UI is more responsive.

===========================================================================
BUILD REQUIREMENTS:

iPhone SDK 3.0 or later

===========================================================================
RUNTIME REQUIREMENTS:

iPhone OS 3.0 or later

===========================================================================
PACKAGING LIST:

LazyTableAppDelegate.{h/m} -
    The app delegate class that downloads in the background the
    "Top Paid iPhone Apps" RSS feed using NSURLConnection.

AppRecord.{h/m} -
    Wrapper object for each data entry, corresponding to a row in the table.

RootViewController.{h/m} -
    UITableViewController subclass that builds the table view in multiple stages,
    using feed data obtained from the LazyTableAppDelegate.

ParseOperation.{h/m}
    Helper NSOperation object used to parse the XML RSS feed loaded by LazyTableAppDelegate.

IconDownloader.{h/m}
    Helper object for managing the downloading of a particular app's icon.
    As a delegate "NSURLConnectionDelegate" is downloads the app icon in the background if it does not
    yet exist and works in conjunction with the RootViewController to manage which apps need their icon.

===========================================================================
CHANGES FROM PREVIOUS VERSIONS:

Version 1.0
- First version.

===========================================================================
Copyright (C) 2009 Apple Inc. All rights reserved.