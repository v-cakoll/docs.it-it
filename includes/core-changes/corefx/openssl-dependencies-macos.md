---
ms.openlocfilehash: a4476fbff572c004632153e5a98812c241efca57
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721272"
---
### <a name="openssl-versions-on-macos"></a><span data-ttu-id="967ed-101">Versioni OpenSSL in macOS</span><span class="sxs-lookup"><span data-stu-id="967ed-101">OpenSSL versions on macOS</span></span>

<span data-ttu-id="967ed-102">I Runtime .NET Core 3,0 e versioni successive in MacOS preferiscono ora le versioni OpenSSL 1.1. x alle versioni OpenSSL 1.0. x per i <xref:System.Security.Cryptography.AesCcm> <xref:System.Security.Cryptography.AesGcm> tipi,, <xref:System.Security.Cryptography.DSAOpenSsl> , <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> , <xref:System.Security.Cryptography.ECDsaOpenSsl> , <xref:System.Security.Cryptography.RSAOpenSsl> e <xref:System.Security.Cryptography.SafeEvpPKeyHandle> .</span><span class="sxs-lookup"><span data-stu-id="967ed-102">The .NET Core 3.0 and later runtimes on macOS now prefer OpenSSL 1.1.x versions to OpenSSL 1.0.x versions for the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, and <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

<span data-ttu-id="967ed-103">Il runtime di .NET Core 2,1 supporta ora le versioni OpenSSL 1.1. x, ma preferisce comunque le versioni OpenSSL 1.0. x.</span><span class="sxs-lookup"><span data-stu-id="967ed-103">The .NET Core 2.1 runtime now supports OpenSSL 1.1.x versions, but still prefers OpenSSL 1.0.x versions.</span></span>

#### <a name="change-description"></a><span data-ttu-id="967ed-104">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="967ed-104">Change description</span></span>

<span data-ttu-id="967ed-105">In precedenza, il runtime di .NET Core usava le versioni OpenSSL 1.0. x in macOS per i tipi che interagiscono con OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="967ed-105">Previously, the .NET Core runtime used OpenSSL 1.0.x versions on macOS for types that interact with OpenSSL.</span></span> <span data-ttu-id="967ed-106">La versione più recente di OpenSSL 1.0. x, OpenSSL 1.0.2, ora non è più supportata.</span><span class="sxs-lookup"><span data-stu-id="967ed-106">The most recent OpenSSL 1.0.x version, OpenSSL 1.0.2, is now out of support.</span></span> <span data-ttu-id="967ed-107">Per gestire i tipi che usano OpenSSL sulle versioni supportate di OpenSSL, i runtime di .NET Core 3,0 e versioni successive usano ora le versioni più recenti di OpenSSL in macOS.</span><span class="sxs-lookup"><span data-stu-id="967ed-107">To keep types that use OpenSSL on supported versions of OpenSSL, the .NET Core 3.0 and later runtimes now use newer versions of OpenSSL on macOS.</span></span>

<span data-ttu-id="967ed-108">Con questa modifica, il comportamento per i runtime di .NET Core in macOS è il seguente:</span><span class="sxs-lookup"><span data-stu-id="967ed-108">With this change, the behavior for the .NET Core runtimes on macOS is as follows:</span></span>

- <span data-ttu-id="967ed-109">Nei runtime di .NET Core 3,0 e versioni successive viene usato OpenSSL 1.1. x, se disponibile, e si esegue il fallback a OpenSSL 1.0. x solo se non è disponibile una versione 1.1. x.</span><span class="sxs-lookup"><span data-stu-id="967ed-109">The .NET Core 3.0 and later version runtimes use OpenSSL 1.1.x, if available, and fall back to OpenSSL 1.0.x only if there's no 1.1.x version available.</span></span>

  <span data-ttu-id="967ed-110">Per i chiamanti che usano i tipi di interoperabilità OpenSSL con P/Invoke personalizzati, seguire le istruzioni riportate nelle <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> note.</span><span class="sxs-lookup"><span data-stu-id="967ed-110">For callers that use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span> <span data-ttu-id="967ed-111">L'app potrebbe arrestarsi in modo anomalo se non si controlla il <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> valore.</span><span class="sxs-lookup"><span data-stu-id="967ed-111">Your app may crash if you don't check the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> value.</span></span>

- <span data-ttu-id="967ed-112">Il runtime di .NET Core 2,1 USA OpenSSL 1.0. x, se disponibile, e esegue il fallback a OpenSSL 1.1. x se non è disponibile la versione 1.0. x.</span><span class="sxs-lookup"><span data-stu-id="967ed-112">The .NET Core 2.1 runtime uses OpenSSL 1.0.x, if available, and falls back to OpenSSL 1.1.x if there's no 1.0.x version available.</span></span>

  <span data-ttu-id="967ed-113">Il runtime di 2,1 preferisce la versione precedente di OpenSSL perché la <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> proprietà non esiste in .NET Core 2,1, quindi la versione OpenSSL non può essere determinata in modo affidabile in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="967ed-113">The 2.1 runtime prefers the earlier version of OpenSSL because the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property does not exist in .NET Core 2.1, so the OpenSSL version cannot be reliably determined at run time.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="967ed-114">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="967ed-114">Version introduced</span></span>

- <span data-ttu-id="967ed-115">2.1.16 di .NET Core</span><span class="sxs-lookup"><span data-stu-id="967ed-115">.NET Core 2.1.16</span></span>
- <span data-ttu-id="967ed-116">3.0.3 di .NET Core</span><span class="sxs-lookup"><span data-stu-id="967ed-116">.NET Core 3.0.3</span></span>
- <span data-ttu-id="967ed-117">.NET Core 3.1.2</span><span class="sxs-lookup"><span data-stu-id="967ed-117">.NET Core 3.1.2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="967ed-118">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="967ed-118">Recommended action</span></span>

- <span data-ttu-id="967ed-119">Disinstallare OpenSSL versione 1.0.2 se non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="967ed-119">Uninstall OpenSSL version 1.0.2 if it's no longer needed.</span></span>

- <span data-ttu-id="967ed-120">Installare OpenSSL 1.1. x se si usano i <xref:System.Security.Cryptography.AesCcm> <xref:System.Security.Cryptography.AesGcm> tipi,, <xref:System.Security.Cryptography.DSAOpenSsl> , <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl> , <xref:System.Security.Cryptography.ECDsaOpenSsl> , <xref:System.Security.Cryptography.RSAOpenSsl> o <xref:System.Security.Cryptography.SafeEvpPKeyHandle> .</span><span class="sxs-lookup"><span data-stu-id="967ed-120">Install OpenSSL 1.1.x if you use the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, or <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

- <span data-ttu-id="967ed-121">Se si usano i tipi di interoperabilità OpenSSL con P/Invoke personalizzati, seguire le istruzioni riportate nelle <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> note.</span><span class="sxs-lookup"><span data-stu-id="967ed-121">If you use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span>

#### <a name="category"></a><span data-ttu-id="967ed-122">Category</span><span class="sxs-lookup"><span data-stu-id="967ed-122">Category</span></span>

<span data-ttu-id="967ed-123">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="967ed-123">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="967ed-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="967ed-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->
