## Intent [[Intent]] 관련
아래와 같은 방법으로 deprecated 된 코드를 방어할 수 있다.

cc [[inline, noinline, crossline]]
```kotlin
inline fun <reified T> Intent.parcelable(key: String, clazz: Class<T>): T? = when {
  SDK_INT >= 33 -> getParcelableExtra(key, clazz)
  else -> @Suppress("DEPRECATION") getParcelableExtra(key) as? T
}

inline fun <reified T> Bundle.parcelable(key: String, clazz: Class<T>): T? = when {
  SDK_INT >= 33 -> getParcelable(key, clazz)
  else -> @Suppress("DEPRECATION") getParcelable(key) as? T
}
```

## Privacy SandBox 

---
- Personalization
  ![[Pasted image 20221103003038.png]]
- Photo picker API
- notification permission request
- Android SDK Upgrade Assistant
- AppCompat libraries
- SDK Extensions
