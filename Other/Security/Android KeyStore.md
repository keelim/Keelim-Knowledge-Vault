
```kotlin
object EncryptionUtils {  
	private const val ANDROID_KEYSTORE = "AndroidKeyStore"  
	private const val KEY_ALIAS = "alias" // As per your requirment  
  
	fun generateKey(): KeyPair?{  
		val keyStore: KeyStore = KeyStore.getInstance(ANDROID_KEYSTORE).apply {  
		load(null)  
	}  
	
	val aliases: Enumeration<String> = keyStore.aliases()  
	val keyPair: KeyPair?  
  
	if (aliases.toList().firstOrNull { it == KEY_ALIAS } == null){  
		val keyPairGenerator: KeyPairGenerator = KeyPairGenerator.getInstance(  
			KeyProperties.KEY_ALGORITHM_RSA,  
			ANDROID_KEYSTORE  
		)  
	
		val parameterSpec: KeyGenParameterSpec = KeyGenParameterSpec.Builder(  
			KEY_ALIAS,  
			KeyProperties.PURPOSE_ENCRYPT or KeyProperties.PURPOSE_DECRYPT 
		).setBlockModes(KeyProperties.BLOCK_MODE_ECB)  
		.setEncryptionPaddings(KeyProperties.ENCRYPTION_PADDING_RSA_PKCS1)  
		.build()  
  
		keyPairGenerator.initialize(parameterSpec)  
		keyPair = keyPairGenerator.genKeyPair()  
	} else {  
		val entry = keyStore.getEntry(KEY_ALIAS, null) as?KeyStore.PrivateKeyEntry  
		keyPair = KeyPair(entry?.certificate?.publicKey,entry?.privateKey)  
	}  
	return keyPair  
	}  
}
```