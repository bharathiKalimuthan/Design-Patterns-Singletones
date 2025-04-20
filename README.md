### Singletones
The Singleton is a creational design pattern that ensures a class has only one instance and provides a global point of access to it. some of the singletones we use in swift are:

```swift
let defaults = UserDefaults.standard
let sharedURLSession = URLSession.shared
```
A singletone created with static keyword.The static keyword means:
It belongs to the type itself, not to an instance.
It's initialized only once during the app's lifetime (lazy and thread-safe).
It’s globally accessible via the type — MySingleton.shared.
  ```swift
class Singleton {
    static let sharedInstance = Singleton()
}

```
and we create it with private constructor
class NetworkManager {

    static let shared = NetworkManager(baseURL: API.baseURL)

    let baseURL: URL

    private init(baseURL: URL) {
        self.baseURL = baseURL
    }

}

private init make sure that instance created only once 
static let shared is stored at the type level kinda global for that class level
static let is bestway to create a single tone that make sure
 **Thread safety** - No race conditions occur on multithreaded environment
** lazily initilized **- created when first time usage
