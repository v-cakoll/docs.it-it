---
ms.openlocfilehash: 8d3a8712528d2d35c706cc26b8c388b65d6ad506
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449218"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a><span data-ttu-id="a1df0-101">Migliore convalida degli argomenti nel costruttore Pkcs8PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="a1df0-101">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>

<span data-ttu-id="a1df0-102">A partire da .NET Core 3.0 Preview 9, il `Pkcs8PrivateKeyInfo` costruttore convalida il `algorithmParameters` parametro come un singolo valore con codifica BER.</span><span class="sxs-lookup"><span data-stu-id="a1df0-102">Starting with .NET Core 3.0 Preview 9, the `Pkcs8PrivateKeyInfo` constructor validates the `algorithmParameters` parameter as a single BER-encoded value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a1df0-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="a1df0-103">Change description</span></span>

<span data-ttu-id="a1df0-104">Prima di .NET Core 3.0 Preview 9, il `algorithmParameters` [ `Pkcs8PrivateKeyInfo` costruttore](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) non convalidava l'argomento.</span><span class="sxs-lookup"><span data-stu-id="a1df0-104">Before .NET Core 3.0 Preview 9, the [`Pkcs8PrivateKeyInfo` constructor](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) did not validate the `algorithmParameters` argument.</span></span>  <span data-ttu-id="a1df0-105">Quando questo argomento rappresenta un valore non valido, il costruttore avrebbe <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> avuto esito <xref:System.ArgumentException> positivo, ma una chiamata`preEncodedValue`a uno qualsiasi dei <xref:System.Security.Cryptography.CryptographicException>metodi <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A>, o genera un per un argomento che non accettano ( ) o un oggetto .</span><span class="sxs-lookup"><span data-stu-id="a1df0-105">When this argument represented an invalid value, the constructor would succeed, but a call to any of the <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A>, or <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> methods would throw either an <xref:System.ArgumentException> for an argument they did not accept (`preEncodedValue`) or a <xref:System.Security.Cryptography.CryptographicException>.</span></span>

<span data-ttu-id="a1df0-106">Se viene eseguito con .NET Core 3.0 prima dell'anteprima <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> 9, il codice seguente genera un'eccezione solo quando viene chiamato il metodo:</span><span class="sxs-lookup"><span data-stu-id="a1df0-106">If run with .NET Core 3.0 before Preview 9, the following code throws an exception only when the <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> method is called:</span></span>

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

<span data-ttu-id="a1df0-107">A partire da .NET Core 3.0 Preview 9, l'argomento viene convalidato nel <xref:System.Security.Cryptography.CryptographicException>costruttore e un valore non valido genera un eccezione .</span><span class="sxs-lookup"><span data-stu-id="a1df0-107">Starting with .NET Core 3.0 Preview 9, the argument is validated in the constructor, and an invalid value results in the method throwing a <xref:System.Security.Cryptography.CryptographicException>.</span></span> <span data-ttu-id="a1df0-108">Questa modifica sposta l'eccezione più vicina all'origine dell'errore di dati.</span><span class="sxs-lookup"><span data-stu-id="a1df0-108">This change moves the exception closer to the source of the data error.</span></span> <span data-ttu-id="a1df0-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="a1df0-109">For example:</span></span>

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a><span data-ttu-id="a1df0-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="a1df0-110">Version introduced</span></span>

<span data-ttu-id="a1df0-111">3.0 Anteprima 9</span><span class="sxs-lookup"><span data-stu-id="a1df0-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a1df0-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="a1df0-112">Recommended action</span></span>

<span data-ttu-id="a1df0-113">Assicurarsi che `algorithmParameters` vengano forniti solo valori `Pkcs8PrivateKeyInfo` validi o <xref:System.ArgumentException> <xref:System.Security.Cryptography.CryptographicException> che vengano chiamate al test del costruttore per entrambi e se si desidera utilizzare la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="a1df0-113">Ensure that only valid `algorithmParameters` values are provided, or that calls to the `Pkcs8PrivateKeyInfo` constructor test for both <xref:System.ArgumentException> and <xref:System.Security.Cryptography.CryptographicException> if exception handling is desired.</span></span>

### <a name="category"></a><span data-ttu-id="a1df0-114">Category</span><span class="sxs-lookup"><span data-stu-id="a1df0-114">Category</span></span>

<span data-ttu-id="a1df0-115">Crittografia</span><span class="sxs-lookup"><span data-stu-id="a1df0-115">Cryptography</span></span>

### <a name="affected-apis"></a><span data-ttu-id="a1df0-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="a1df0-116">Affected APIs</span></span>

- <span data-ttu-id="a1df0-117">[Costruttore Pkcs8PrivateKeyInfo](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))</span><span class="sxs-lookup"><span data-stu-id="a1df0-117">[Pkcs8PrivateKeyInfo constructor](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))</span></span>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean)`

-->
