---
ms.openlocfilehash: 877f9d99b660c4af843e4d8d525219c1df6c99a9
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721424"
---
### <a name="net-core-30-prefers-openssl-11x-to-openssl-10x"></a><span data-ttu-id="461c6-101">.NET Core 3,0 preferisce OpenSSL 1.1. x a OpenSSL 1.0. x</span><span class="sxs-lookup"><span data-stu-id="461c6-101">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>

<span data-ttu-id="461c6-102">.NET Core per Linux, che funziona in più distribuzioni Linux, può supportare sia OpenSSL 1.0. x che OpenSSL 1.1. x.</span><span class="sxs-lookup"><span data-stu-id="461c6-102">.NET Core for Linux, which works across multiple Linux distributions, can support both OpenSSL 1.0.x and OpenSSL 1.1.x.</span></span>  <span data-ttu-id="461c6-103">.NET Core 2,1 e .NET Core 2,2 cercare prima 1.0. x, quindi eseguire il fallback alla versione 1.1. x; .NET Core 3,0 cerca innanzitutto 1.1. x.</span><span class="sxs-lookup"><span data-stu-id="461c6-103">.NET Core 2.1 and .NET Core 2.2 look for 1.0.x first, then fall back to 1.1.x; .NET Core 3.0 looks for 1.1.x first.</span></span> <span data-ttu-id="461c6-104">Questa modifica è stata apportata per aggiungere il supporto per nuovi standard crittografici.</span><span class="sxs-lookup"><span data-stu-id="461c6-104">This change was made to add support for new cryptographic standards.</span></span>

<span data-ttu-id="461c6-105">Questa modifica può influisca sulle librerie o sulle applicazioni che eseguono l'interoperabilità della piattaforma con i tipi di interoperabilità specifici di OpenSSL in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="461c6-105">This change may impact libraries or applications that do platform interop with the OpenSSL-specific interop types in .NET Core.</span></span>

#### <a name="change-description"></a><span data-ttu-id="461c6-106">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="461c6-106">Change description</span></span>

<span data-ttu-id="461c6-107">In .NET Core 2,2 e versioni precedenti, il runtime preferisce il caricamento di OpenSSL 1.0. x su 1.1. x.</span><span class="sxs-lookup"><span data-stu-id="461c6-107">In .NET Core 2.2 and earlier versions, the runtime prefers loading OpenSSL 1.0.x over 1.1.x.</span></span> <span data-ttu-id="461c6-108">Ciò significa che i <xref:System.IntPtr> <xref:System.Runtime.InteropServices.SafeHandle> tipi e per l'interoperabilità con OpenSSL vengono utilizzati con libcrypto. so. 1.0.0/libcrypto. so. 1.0/libcrypto. so. 10 per preferenza.</span><span class="sxs-lookup"><span data-stu-id="461c6-108">This means that the <xref:System.IntPtr> and <xref:System.Runtime.InteropServices.SafeHandle> types for interop with OpenSSL are used with libcrypto.so.1.0.0 / libcrypto.so.1.0 / libcrypto.so.10 by preference.</span></span>

<span data-ttu-id="461c6-109">A partire da .NET Core 3,0, il runtime preferisce il caricamento di OpenSSL 1.1. x su OpenSSL 1.0. x, quindi i <xref:System.IntPtr> <xref:System.Runtime.InteropServices.SafeHandle> tipi e per l'interoperabilità con OpenSSL vengono usati con libcrypto. so. 1.1/libcrypto. so. 11/libcrypto. so. 1.1.0/libcrypto. so. 1.1.1 per preferenza.</span><span class="sxs-lookup"><span data-stu-id="461c6-109">Starting with .NET Core 3.0, the runtime prefers loading OpenSSL 1.1.x over OpenSSL 1.0.x, so the <xref:System.IntPtr> and <xref:System.Runtime.InteropServices.SafeHandle> types for interop with OpenSSL are used with libcrypto.so.1.1 / libcrypto.so.11 / libcrypto.so.1.1.0 / libcrypto.so.1.1.1 by preference.</span></span> <span data-ttu-id="461c6-110">Di conseguenza, le librerie e le applicazioni che interagiscono direttamente con OpenSSL possono avere puntatori incompatibili con i valori esposti a .NET Core durante l'aggiornamento da .NET Core 2,1 o .NET Core 2,2.</span><span class="sxs-lookup"><span data-stu-id="461c6-110">As a result, libraries and applications that interoperate with OpenSSL directly may have incompatible pointers with the .NET Core-exposed values when upgrading from .NET Core 2.1 or .NET Core 2.2.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="461c6-111">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="461c6-111">Version introduced</span></span>

<span data-ttu-id="461c6-112">3.0</span><span class="sxs-lookup"><span data-stu-id="461c6-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="461c6-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="461c6-113">Recommended action</span></span>

<span data-ttu-id="461c6-114">Le librerie e le applicazioni che eseguono operazioni dirette con OpenSSL devono prestare attenzione per assicurarsi che stiano usando la stessa versione di OpenSSL del runtime di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="461c6-114">Libraries and applications that do direct operations with OpenSSL need to be careful to ensure they are using the same version of OpenSSL as the .NET Core runtime.</span></span>

<span data-ttu-id="461c6-115">Tutte le librerie o le applicazioni che usano i <xref:System.IntPtr> <xref:System.Runtime.InteropServices.SafeHandle> valori o dai tipi crittografici di .NET Core direttamente con OpenSSL devono confrontare la versione della libreria usata con la nuova <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> proprietà per assicurarsi che i puntatori siano compatibili.</span><span class="sxs-lookup"><span data-stu-id="461c6-115">All libraries or applications that use <xref:System.IntPtr> or <xref:System.Runtime.InteropServices.SafeHandle> values from the .NET Core cryptographic types directly with OpenSSL should compare the version of the library they use with the new <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property to ensure the pointers are compatible.</span></span>

#### <a name="category"></a><span data-ttu-id="461c6-116">Category</span><span class="sxs-lookup"><span data-stu-id="461c6-116">Category</span></span>

<span data-ttu-id="461c6-117">Crittografia</span><span class="sxs-lookup"><span data-stu-id="461c6-117">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="461c6-118">API interessate</span><span class="sxs-lookup"><span data-stu-id="461c6-118">Affected APIs</span></span>

- <xref:System.Security.Cryptography.SafeEvpPKeyHandle.%23ctor%2A>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.RSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.DSAOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.IntPtr)>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.%23ctor(System.Security.Cryptography.SafeEvpPKeyHandle)>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Handle?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Security.Cryptography.SafeEvpPKeyHandle.#ctor`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.RSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.RSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.DSAOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.DSAOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.#ctor(System.Security.CryptographySafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDsaOpenSsl.DuplicateKeyHandle`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.IntPtr)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.#ctor(System.Security.Cryptography.SafeEvpPKeyHandle)`
- `M:System.Security.Cryptography.ECDiffieHellmanOpenSsl.DuplicateKeyHandle`
- `P:System.Security.Cryptography.X509Certificates.X509Certificate.Handle`

-->
