# Ignite

New App
- Create New Project / iOS / App
- Organization: Aepryus Software
- Ignite Group changed to Source
- add Resources group next to it
- Delete: Main, SceneDelegate
- in Source add Groups: Global, Interface, Domain
- Global: AppDelegate
- Interface: ViewController
- Resources: Assets, LaunchScreen, Info
- Global: add Ignite file:

```swift
class Ignite {
    static let window: UIWindow = UIWindow()
  
    static func start() {
        print("[ Ignite ] ================================================================")
        window.rootViewController = ViewController()
        window.makeKeyAndVisible()
    }
}
```

change AppDelegate to:

```swift
@main
class AppDelegate: UIResponder, UIApplicationDelegate {
    // UIApplicationDelegate ===========================================================================
    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        Ignite.start()
        return true
    }
}
```


- add Acheron package
- change ViewController to:

```swift
class ViewController: UIViewController {
    // UIViewController ================================================================================
    override func viewDidLoad() {
        super.viewDidLoad()
        view.backgroundColor = .magenta.tone(0.5).tint(0.5)
    }
}
```

- Info.plist: delete “Application Scene Manifest”
- Target / Info: delete “Main storyboard file base name”
- Build settings: change Info.plist file to “Resources/Info.plist”
- Build settings: change Ignite.entitlements file to “Resources/Ignite.entitlements”
- Supported Destinations: delete Mac (designed for iPad); add Mac (Mac Catalyst)
- edit the schema and add: OS_ACTIVITY_MODE disable
