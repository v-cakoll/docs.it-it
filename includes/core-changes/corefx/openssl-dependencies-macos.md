---
ms.openlocfilehash: 6a5cd260a2820e2a81142f6d55e32e91173ca503
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147451"
---
### <a name="openssl-versions-on-macos"></a><span data-ttu-id="af5aa-101">Versioni OpenSSL su macOS</span><span class="sxs-lookup"><span data-stu-id="af5aa-101">OpenSSL versions on macOS</span></span>

<span data-ttu-id="af5aa-102">I runtime di .NET Core 3.0 e versioni successive in macOS ora preferiscono le versioni OpenSSL <xref:System.Security.Cryptography.AesGcm> <xref:System.Security.Cryptography.DSAOpenSsl>1.1.x alle versioni OpenSSL 1.0.x per i <xref:System.Security.Cryptography.AesCcm>tipi , , , <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, , <xref:System.Security.Cryptography.RSAOpenSsl>e <xref:System.Security.Cryptography.SafeEvpPKeyHandle> .</span><span class="sxs-lookup"><span data-stu-id="af5aa-102">The .NET Core 3.0 and later runtimes on macOS now prefer OpenSSL 1.1.x versions to OpenSSL 1.0.x versions for the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, and <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

<span data-ttu-id="af5aa-103">Il runtime di .NET Core 2.1 ora supporta le versioni OpenSSL 1.1.x, ma preferisce comunque le versioni OpenSSL 1.0.x.</span><span class="sxs-lookup"><span data-stu-id="af5aa-103">The .NET Core 2.1 runtime now supports OpenSSL 1.1.x versions, but still prefers OpenSSL 1.0.x versions.</span></span>

#### <a name="change-description"></a><span data-ttu-id="af5aa-104">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="af5aa-104">Change description</span></span>

<span data-ttu-id="af5aa-105">In precedenza, il runtime di .NET Core utilizzava le versioni OpenSSL 1.0.x in macOS per i tipi che interagiscono con OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="af5aa-105">Previously, the .NET Core runtime used OpenSSL 1.0.x versions on macOS for types that interact with OpenSSL.</span></span> <span data-ttu-id="af5aa-106">La versione OpenSSL 1.0.x più recente, OpenSSL 1.0.2, è ora fuori supporto.</span><span class="sxs-lookup"><span data-stu-id="af5aa-106">The most recent OpenSSL 1.0.x version, OpenSSL 1.0.2, is now out of support.</span></span> <span data-ttu-id="af5aa-107">Per mantenere i tipi che usano OpenSSL nelle versioni supportate di OpenSSL, i runtime di .NET Core 3.0 e versioni successive ora usano le versioni più recenti di OpenSSL su macOS.</span><span class="sxs-lookup"><span data-stu-id="af5aa-107">To keep types that use OpenSSL on supported versions of OpenSSL, the .NET Core 3.0 and later runtimes now use newer versions of OpenSSL on macOS.</span></span>

<span data-ttu-id="af5aa-108">Con questa modifica, il comportamento per i runtime di .NET Core in macOS è il seguente:With this change, the behavior for the .NET Core runtimes on macOS is as follows:</span><span class="sxs-lookup"><span data-stu-id="af5aa-108">With this change, the behavior for the .NET Core runtimes on macOS is as follows:</span></span>

- <span data-ttu-id="af5aa-109">I runtime di .NET Core 3.0 e versioni successive utilizzano OpenSSL 1.1.x, se disponibile, ed esegue il rollback a OpenSSL 1.0.x solo se non è disponibile alcuna versione 1.1.x.</span><span class="sxs-lookup"><span data-stu-id="af5aa-109">The .NET Core 3.0 and later version runtimes use OpenSSL 1.1.x, if available, and fall back to OpenSSL 1.0.x only if there's no 1.1.x version available.</span></span>

  <span data-ttu-id="af5aa-110">Per i chiamanti che utilizzano i tipi di interoperabilità OpenSSL con P/Invoke personalizzati, seguire le indicazioni contenute nelle <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> osservazioni.</span><span class="sxs-lookup"><span data-stu-id="af5aa-110">For callers that use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span> <span data-ttu-id="af5aa-111">L'app potrebbe bloccarsi se <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> non si controlla il valore.</span><span class="sxs-lookup"><span data-stu-id="af5aa-111">Your app may crash if you don't check the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> value.</span></span>

- <span data-ttu-id="af5aa-112">Il runtime di .NET Core 2.1 utilizza OpenSSL 1.0.x, se disponibile, ed esegue il fallback a OpenSSL 1.1.x se non è disponibile alcuna versione 1.0.x.</span><span class="sxs-lookup"><span data-stu-id="af5aa-112">The .NET Core 2.1 runtime uses OpenSSL 1.0.x, if available, and falls back to OpenSSL 1.1.x if there's no 1.0.x version available.</span></span>

  <span data-ttu-id="af5aa-113">Il runtime 2.1 preferisce la versione <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> precedente di OpenSSL perché la proprietà non esiste in .NET Core 2.1, pertanto la versione OpenSSL non può essere determinata in modo affidabile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="af5aa-113">The 2.1 runtime prefers the earlier version of OpenSSL because the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property does not exist in .NET Core 2.1, so the OpenSSL version cannot be reliably determined at run time.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="af5aa-114">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="af5aa-114">Version introduced</span></span>

- <span data-ttu-id="af5aa-115">.NET Core 2.1.16</span><span class="sxs-lookup"><span data-stu-id="af5aa-115">.NET Core 2.1.16</span></span>
- <span data-ttu-id="af5aa-116">.NET Core 3.0.3</span><span class="sxs-lookup"><span data-stu-id="af5aa-116">.NET Core 3.0.3</span></span>
- <span data-ttu-id="af5aa-117">.NET Core 3.1.2</span><span class="sxs-lookup"><span data-stu-id="af5aa-117">.NET Core 3.1.2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="af5aa-118">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="af5aa-118">Recommended action</span></span>

- <span data-ttu-id="af5aa-119">Disinstallare OpenSSL versione 1.0.2 se non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="af5aa-119">Uninstall OpenSSL version 1.0.2 if it's no longer needed.</span></span>

- <span data-ttu-id="af5aa-120">Installare OpenSSL 1.1.x se <xref:System.Security.Cryptography.AesCcm> <xref:System.Security.Cryptography.AesGcm>si <xref:System.Security.Cryptography.DSAOpenSsl> <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>utilizzano <xref:System.Security.Cryptography.RSAOpenSsl>i <xref:System.Security.Cryptography.SafeEvpPKeyHandle> tipi , , , , <xref:System.Security.Cryptography.ECDsaOpenSsl>, o .</span><span class="sxs-lookup"><span data-stu-id="af5aa-120">Install OpenSSL 1.1.x if you use the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, or <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

- <span data-ttu-id="af5aa-121">Se si utilizzano i tipi di interoperabilità OpenSSL con <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> P/Invoke personalizzati, seguire le indicazioni contenute nelle osservazioni.</span><span class="sxs-lookup"><span data-stu-id="af5aa-121">If you use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span>

#### <a name="category"></a><span data-ttu-id="af5aa-122">Category</span><span class="sxs-lookup"><span data-stu-id="af5aa-122">Category</span></span>

<span data-ttu-id="af5aa-123">CoreFx</span><span class="sxs-lookup"><span data-stu-id="af5aa-123">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="af5aa-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="af5aa-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->
