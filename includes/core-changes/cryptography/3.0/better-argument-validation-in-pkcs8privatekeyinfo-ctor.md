---
ms.openlocfilehash: 32030698c12de87daef5e1d8851a0f55ec36d688
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721203"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a>Migliore convalida degli argomenti nel costruttore Pkcs8PrivateKeyInfo

A partire da .NET Core 3,0 Preview 9, il `Pkcs8PrivateKeyInfo` costruttore convalida il `algorithmParameters` parametro come singolo valore con codifica BER.

#### <a name="change-description"></a>Descrizione modifica:

Prima di .NET Core 3,0 Preview 9, il [ `Pkcs8PrivateKeyInfo` Costruttore](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) non convalidava l' `algorithmParameters` argomento.  Quando questo argomento rappresenta un valore non valido, il costruttore ha esito positivo, ma una chiamata a uno dei <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A> metodi,, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A> o <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> genera un' <xref:System.ArgumentException> eccezione per un argomento che non accetta ( `preEncodedValue` ) o <xref:System.Security.Cryptography.CryptographicException> .

Se viene eseguito con .NET Core 3,0 prima dell'anteprima 9, il codice seguente genera un'eccezione solo quando <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> viene chiamato il metodo:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

A partire da .NET Core 3,0 Preview 9, l'argomento viene convalidato nel costruttore e un valore non valido restituisce il metodo che genera un oggetto <xref:System.Security.Cryptography.CryptographicException> . Questa modifica sposta l'eccezione più vicino all'origine dell'errore dei dati. Ad esempio:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Verificare che `algorithmParameters` vengano forniti solo i valori validi o che le chiamate al `Pkcs8PrivateKeyInfo` Costruttore testano sia per sia per <xref:System.ArgumentException> <xref:System.Security.Cryptography.CryptographicException> se si desidera la gestione delle eccezioni.

#### <a name="category"></a>Category

Crittografia

#### <a name="affected-apis"></a>API interessate

- [Costruttore Pkcs8PrivateKeyInfo](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))

<!--

#### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean)`

-->
