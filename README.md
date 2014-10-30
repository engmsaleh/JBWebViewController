JBWebViewController
===================

A drop-in Facebook inspired modal web browser.

## Installation

### CocoaPods
The recommended approach for installating JBWebViewController is through the package manager [CocoaPods](http://cocoapods.org/), which is widely used by iOS & Mac developers.

Simply add the following line to your Podfile:
```ruby
pod "JBWebViewController"
```

Does not work yet. Still on TODO list.

### Manual Install
Drag the JBWebViewController folder into your Xcode project, you may need to check the box "Copy items into destination group's folder (if needed)".

JBWebViewController needs the following third-party libraries:
* [ARChromeActivity](https://github.com/alextrob/ARChromeActivity)
* [ARSafariActivity](https://github.com/alexruperez/ARSafariActivity)
* [NJKWebViewProgress](https://github.com/ninjinkun/NJKWebViewProgress)

## How to use
JBWebViewController is ment to be shown modally, which is recommended to be down with it's built in show functionality. Whilst not being recommended, it is however possible to present JBWebViewController outside a modal view controller. JBWebViewController show always be connected to a UINavigationController.

#### Presenting JBWebViewController
```objectivec
JBWebViewController *controller = [[JBWebViewController alloc] initWithUrl:[NSURL URLWithString:@"http://www.apple.com/iphone/"]];

[controller show];
```

#### Presenting JBWebViewController with block
```objectivec
JBWebViewController *controller = [[JBWebViewController alloc] initWithUrl:[NSURL URLWithString:@"http://www.apple.com/iphone/"]];

[controller showControllerWithCompletion:^(JBWebViewController *controller) {
    NSLog(@"Controller has arrived.");
}];
```

#### Navigate to URL
```objectivec
[controller navigateToURL:[NSURL URLWithString:@"http://www.apple.com/ios/"]];
```

#### Load custom NSURLRequest
```objectivec
NSURLRequest *request = [NSURLRequest requestWithURL:[NSURL URLWithString:@"http://developer.apple.com/"]];
[controller loadRequest:request];
```


#### Reload current page
```objectivec
[controller reload];
```

#### Manually setting controller title
```objectivec
[controller setWebTitle:@"The quick brown fox"];
```

#### Getting controller title
```objectivec
NSString *controllerTitle = [controller getWebTitle];
```

#### Manually setting controller subtitle
```objectivec
[controller setWebSubtitle:@"foo bar"];
```

#### Getting controller subtitle
```objectivec
NSString *controllerSubtitle = [controller getWebSubtitle];
```

## Icons
Free icons by [Icon8s](http://icons8.com/) under Creative Commons Attribution-NoDerivs 3.0 Unported.

## Contact

Mention me on Twitter ([@JonasBoserup](https://twitter.com/JonasBoserup)) or email me ([Profile](https://github.com/boserup)).

## License

JBWebViewController is available under the MIT license. See the LICENSE file for more info.
