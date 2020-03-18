---
ms.openlocfilehash: 8d3a8712528d2d35c706cc26b8c388b65d6ad506
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449218"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a>Migliore convalida degli argomenti nel costruttore Pkcs8PrivateKeyInfo

A partire da .NET Core 3.0 Preview 9, il `Pkcs8PrivateKeyInfo` costruttore convalida il `algorithmParameters` parametro come un singolo valore con codifica BER.

#### <a name="change-description"></a>Descrizione modifica:

Prima di .NET Core 3.0 Preview 9, il `algorithmParameters` [ `Pkcs8PrivateKeyInfo` costruttore](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) non convalidava l'argomento.  Quando questo argomento rappresenta un valore non valido, il costruttore avrebbe <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> avuto esito <xref:System.ArgumentException> positivo, ma una chiamata`preEncodedValue`a uno qualsiasi dei <xref:System.Security.Cryptography.CryptographicException>metodi <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A>, o genera un per un argomento che non accettano ( ) o un oggetto .

Se viene eseguito con .NET Core 3.0 prima dell'anteprima <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> 9, il codice seguente genera un'eccezione solo quando viene chiamato il metodo:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

A partire da .NET Core 3.0 Preview 9, l'argomento viene convalidato nel <xref:System.Security.Cryptography.CryptographicException>costruttore e un valore non valido genera un eccezione . Questa modifica sposta l'eccezione più vicina all'origine dell'errore di dati. Ad esempio:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a>Versione introdotta

3.0 Anteprima 9

#### <a name="recommended-action"></a>Azione consigliata

Assicurarsi che `algorithmParameters` vengano forniti solo valori `Pkcs8PrivateKeyInfo` validi o <xref:System.ArgumentException> <xref:System.Security.Cryptography.CryptographicException> che vengano chiamate al test del costruttore per entrambi e se si desidera utilizzare la gestione delle eccezioni.

### <a name="category"></a>Category

Crittografia

### <a name="affected-apis"></a>API interessate

- [Costruttore Pkcs8PrivateKeyInfo](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean)`

-->
