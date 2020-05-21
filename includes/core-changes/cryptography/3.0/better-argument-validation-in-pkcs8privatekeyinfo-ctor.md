---
ms.openlocfilehash: 32030698c12de87daef5e1d8851a0f55ec36d688
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721203"
---
### <a name="better-argument-validation-in-the-pkcs8privatekeyinfo-constructor"></a><span data-ttu-id="8b7d3-101">Migliore convalida degli argomenti nel costruttore Pkcs8PrivateKeyInfo</span><span class="sxs-lookup"><span data-stu-id="8b7d3-101">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>

<span data-ttu-id="8b7d3-102">A partire da .NET Core 3,0 Preview 9, il `Pkcs8PrivateKeyInfo` costruttore convalida il `algorithmParameters` parametro come singolo valore con codifica BER.</span><span class="sxs-lookup"><span data-stu-id="8b7d3-102">Starting with .NET Core 3.0 Preview 9, the `Pkcs8PrivateKeyInfo` constructor validates the `algorithmParameters` parameter as a single BER-encoded value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8b7d3-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="8b7d3-103">Change description</span></span>

<span data-ttu-id="8b7d3-104">Prima di .NET Core 3,0 Preview 9, il [ `Pkcs8PrivateKeyInfo` Costruttore](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) non convalidava l' `algorithmParameters` argomento.</span><span class="sxs-lookup"><span data-stu-id="8b7d3-104">Before .NET Core 3.0 Preview 9, the [`Pkcs8PrivateKeyInfo` constructor](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean)) did not validate the `algorithmParameters` argument.</span></span>  <span data-ttu-id="8b7d3-105">Quando questo argomento rappresenta un valore non valido, il costruttore ha esito positivo, ma una chiamata a uno dei <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A> metodi,, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A> o <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> genera un' <xref:System.ArgumentException> eccezione per un argomento che non accetta ( `preEncodedValue` ) o <xref:System.Security.Cryptography.CryptographicException> .</span><span class="sxs-lookup"><span data-stu-id="8b7d3-105">When this argument represented an invalid value, the constructor would succeed, but a call to any of the <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncode%2A>, <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encrypt%2A>, or <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.TryEncrypt%2A> methods would throw either an <xref:System.ArgumentException> for an argument they did not accept (`preEncodedValue`) or a <xref:System.Security.Cryptography.CryptographicException>.</span></span>

<span data-ttu-id="8b7d3-106">Se viene eseguito con .NET Core 3,0 prima dell'anteprima 9, il codice seguente genera un'eccezione solo quando <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> viene chiamato il metodo:</span><span class="sxs-lookup"><span data-stu-id="8b7d3-106">If run with .NET Core 3.0 before Preview 9, the following code throws an exception only when the <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.Encode> method is called:</span></span>

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
// This line throws an ArgumentException for `preEncodedValue`:
byte[] encoded = info.Encode();
```

<span data-ttu-id="8b7d3-107">A partire da .NET Core 3,0 Preview 9, l'argomento viene convalidato nel costruttore e un valore non valido restituisce il metodo che genera un oggetto <xref:System.Security.Cryptography.CryptographicException> .</span><span class="sxs-lookup"><span data-stu-id="8b7d3-107">Starting with .NET Core 3.0 Preview 9, the argument is validated in the constructor, and an invalid value results in the method throwing a <xref:System.Security.Cryptography.CryptographicException>.</span></span> <span data-ttu-id="8b7d3-108">Questa modifica sposta l'eccezione più vicino all'origine dell'errore dei dati.</span><span class="sxs-lookup"><span data-stu-id="8b7d3-108">This change moves the exception closer to the source of the data error.</span></span> <span data-ttu-id="8b7d3-109">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8b7d3-109">For example:</span></span>

```csharp
byte[] algorithmParameters = { 0x05, 0x00, 0x05, 0x00 };

// This line throws a CryptographicException
var info = new Pkcs8PrivateKeyInfo(algorithmId, algorithmParameters, privateKey);
```

#### <a name="version-introduced"></a><span data-ttu-id="8b7d3-110">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="8b7d3-110">Version introduced</span></span>

<span data-ttu-id="8b7d3-111">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="8b7d3-111">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8b7d3-112">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="8b7d3-112">Recommended action</span></span>

<span data-ttu-id="8b7d3-113">Verificare che `algorithmParameters` vengano forniti solo i valori validi o che le chiamate al `Pkcs8PrivateKeyInfo` Costruttore testano sia per sia per <xref:System.ArgumentException> <xref:System.Security.Cryptography.CryptographicException> se si desidera la gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="8b7d3-113">Ensure that only valid `algorithmParameters` values are provided, or that calls to the `Pkcs8PrivateKeyInfo` constructor test for both <xref:System.ArgumentException> and <xref:System.Security.Cryptography.CryptographicException> if exception handling is desired.</span></span>

#### <a name="category"></a><span data-ttu-id="8b7d3-114">Category</span><span class="sxs-lookup"><span data-stu-id="8b7d3-114">Category</span></span>

<span data-ttu-id="8b7d3-115">Crittografia</span><span class="sxs-lookup"><span data-stu-id="8b7d3-115">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8b7d3-116">API interessate</span><span class="sxs-lookup"><span data-stu-id="8b7d3-116">Affected APIs</span></span>

- <span data-ttu-id="8b7d3-117">[Costruttore Pkcs8PrivateKeyInfo](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))</span><span class="sxs-lookup"><span data-stu-id="8b7d3-117">[Pkcs8PrivateKeyInfo constructor](xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.%23ctor(System.Security.Cryptography.Oid,System.Nullable%7BSystem.ReadOnlyMemory%7BSystem.Byte%7D%7D,System.ReadOnlyMemory%7BSystem.Byte%7D,System.Boolean))</span></span>

<!--

#### Affected APIs

- `M:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo.#ctor(System.Security.Cryptography.Oid,System.Nullable{System.ReadOnlyMemory{System.Byte}},System.ReadOnlyMemory{System.Byte},System.Boolean)`

-->
