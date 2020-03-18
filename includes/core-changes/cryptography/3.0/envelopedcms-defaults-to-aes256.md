---
ms.openlocfilehash: f9000b19997201c2d3de0643669f9029ff1ca31c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "74567983"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a><span data-ttu-id="20db5-101">Il valore predefinito di EnvelopedCms è la crittografia AES-256EnvelopedCms defaults to AES-256 encryption</span><span class="sxs-lookup"><span data-stu-id="20db5-101">EnvelopedCms defaults to AES-256 encryption</span></span>

<span data-ttu-id="20db5-102">L'algoritmo di `EnvelopedCms` crittografia simmetrica predefinito utilizzato da è stato modificato da TripleDES a AES-256.</span><span class="sxs-lookup"><span data-stu-id="20db5-102">The default symmetric encryption algorithm used by `EnvelopedCms` has changed from TripleDES to AES-256.</span></span>

#### <a name="change-description"></a><span data-ttu-id="20db5-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="20db5-103">Change description</span></span>

<span data-ttu-id="20db5-104">In .NET Core Preview 7 <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> e versioni precedenti, quando viene utilizzato per crittografare i dati senza specificare un algoritmo di crittografia simmetrica tramite un overload del costruttore, i dati sono stati crittografati con l'algoritmo TripleDES/3DES/3DEA/DES3-EDE.</span><span class="sxs-lookup"><span data-stu-id="20db5-104">In .NET Core Preview 7 and earlier versions, when <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> is used to encrypt data without specifying a symmetric encryption algorithm via a constructor overload, the data was encrypted with the TripleDES/3DES/3DEA/DES3-EDE algorithm.</span></span>

<span data-ttu-id="20db5-105">A partire da .NET Core 3.0 Preview 8 (tramite la versione 4.6.0 del pacchetto [System.Security.Cryptography.Pkcs.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) NuGet), l'algoritmo predefinito è stato modificato in AES-256 per la modernizzazione dell'algoritmo e per migliorare la sicurezza delle opzioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="20db5-105">Starting with .NET Core 3.0 Preview 8 (via version 4.6.0 of the [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) NuGet package), the default algorithm has been changed to AES-256 for algorithm modernization and to improve the security of default options.</span></span> <span data-ttu-id="20db5-106">Se il certificato di un destinatario del messaggio ha una chiave pubblica Diffie-Hellman (non CE), l'operazione di crittografia potrebbe non riuscire a <xref:System.Security.Cryptography.CryptographicException> causa di limitazioni nella piattaforma sottostante.</span><span class="sxs-lookup"><span data-stu-id="20db5-106">If a message recipient certificate has a (non-EC) Diffie-Hellman public key, the encryption operation may fail with a <xref:System.Security.Cryptography.CryptographicException> due to limitations in the underlying platform.</span></span>

<span data-ttu-id="20db5-107">Nel codice di esempio seguente, i dati vengono crittografati con TripleDES se in esecuzione su .NET Core 3.0 Preview 7 o versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="20db5-107">In the following sample code, the data is encrypted with TripleDES if running on .NET Core 3.0 Preview 7 or earlier.</span></span> <span data-ttu-id="20db5-108">Se in esecuzione su .NET Core 3.0 Preview 8 o versione successiva, viene crittografato con AES-256.</span><span class="sxs-lookup"><span data-stu-id="20db5-108">If running on .NET Core 3.0 Preview 8 or later, it is encrypted with AES-256.</span></span>

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a><span data-ttu-id="20db5-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="20db5-109">Version introduced</span></span>

<span data-ttu-id="20db5-110">3.0 Anteprima 8</span><span class="sxs-lookup"><span data-stu-id="20db5-110">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="20db5-111">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="20db5-111">Recommended action</span></span>

<span data-ttu-id="20db5-112">Se si è influenzati negativamente dalla modifica, è possibile ripristinare la crittografia <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> TripleDES specificando in <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>modo esplicito l'identificatore dell'algoritmo di crittografia in un costruttore che include un parametro di tipo , ad esempio:</span><span class="sxs-lookup"><span data-stu-id="20db5-112">If you are negatively impacted by the change, you can restore TripleDES encryption by explicitly specifying the encryption algorithm identifier in an <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> constructor that includes a parameter of type <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, such as:</span></span>

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a><span data-ttu-id="20db5-113">Category</span><span class="sxs-lookup"><span data-stu-id="20db5-113">Category</span></span>

<span data-ttu-id="20db5-114">Crittografia</span><span class="sxs-lookup"><span data-stu-id="20db5-114">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="20db5-115">API interessate</span><span class="sxs-lookup"><span data-stu-id="20db5-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->
