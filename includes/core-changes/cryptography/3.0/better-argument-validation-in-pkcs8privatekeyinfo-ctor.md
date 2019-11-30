---
ms.openlocfilehash: a9b6af31b68c25ab58c52757f48ed23cca3f5a35
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567973"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a>Migliore convalida degli argomenti nel costruttore Pkcs8PrivateKeyInfo

A partire da .NET Core 3,0 Preview 9, il costruttore `Pkcs8PrivateKeyInfo` convalida il parametro `algorithmParameters` come singolo valore con codifica BER.

#### <a name="change-description"></a>Descrizione della modifica

Prima di .NET Core 3,0 Preview 9, il [costruttore`Pkcs8PrivateKeyInfo`](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) non convalidava l'argomento `algorithmParameters`.  Quando questo argomento rappresenta un valore non valido, il costruttore ha esito positivo, ma una chiamata a uno dei metodi <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A>o <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> genera un <xref:System.ArgumentException> per un argomento che non accetta (`preEncodedValue`) o un <xref:System.Security.Cryptography.CryptographicException>.

Se viene eseguito con .NET Core 3,0 prima dell'anteprima 9, il codice seguente genera un'eccezione solo quando viene chiamato il metodo <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

A partire da .NET Core 3,0 Preview 9, l'argomento viene convalidato nel costruttore e un valore non valido determina la generazione di un <xref:System.Security.Cryptography.CryptographicException>da parte del metodo. Questa modifica sposta l'eccezione più vicino all'origine dell'errore dei dati. Ad esempio:

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a>Versione introdotta

3,0 Preview 9

#### <a name="recommended-action"></a>Azione consigliata

Verificare che siano specificati solo valori `algorithmParameters` validi oppure che le chiamate al costruttore di `Pkcs8PrivateKeyInfo` verificano sia per <xref:System.ArgumentException> che per <xref:System.Security.Cryptography.CryptographicException> se si desidera la gestione delle eccezioni.

### <a name="category"></a>Category

Crittografia

### <a name="affected-apis"></a>API interessate

- [Costruttore Pkcs8PrivateKeyInfo](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean))

-->
