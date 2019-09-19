---
ms.openlocfilehash: f72a9f60d0adcace2df6f1761940f8d8cd33d3af
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119289"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a>Migliore convalida degli argomenti nel costruttore Pkcs8PrivateKeyInfo

A partire da .NET Core 3,0 Preview 9, `Pkcs8PrivateKeyInfo` il costruttore convalida il `algorithmParameters` parametro come singolo valore con codifica BER. 

#### <a name="change-description"></a>Descrizione della modifica

Prima di .NET Core 3,0 Preview 9, il [ `Pkcs8PrivateKeyInfo` Costruttore](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) non convalidava l' `algorithmParameters` argomento.  Quando questo argomento rappresenta un valore non valido, il costruttore ha esito positivo, ma una chiamata a <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>uno <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>dei <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A>metodi, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> , o genera un' <xref:System.ArgumentException> eccezione per un argomento non accettato (`preEncodedValue`) <xref:System.Security.Cryptography.CryptographicException>o.

Se viene eseguito con .NET Core 3,0 prima dell'anteprima 9, il codice seguente genera un'eccezione solo <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> quando viene chiamato il metodo:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

A partire da .NET Core 3,0 Preview 9, l'argomento viene convalidato nel costruttore e un valore non valido restituisce il metodo che genera <xref:System.Security.Cryptography.CryptographicException>un oggetto. Questa modifica sposta l'eccezione più vicino all'origine dell'errore dei dati. Ad esempio:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Verificare che vengano forniti `algorithmParameters` solo i valori validi o che le chiamate al `Pkcs8PrivateKeyInfo` <xref:System.Security.Cryptography.CryptographicException> Costruttore testano sia <xref:System.ArgumentException> per sia per se si desidera la gestione delle eccezioni.

### <a name="category"></a>Category

Crittografia

### <a name="affected-apis"></a>API interessate

- [Costruttore Pkcs8PrivateKeyInfo](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean))

-->