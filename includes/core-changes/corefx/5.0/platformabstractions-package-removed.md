---
ms.openlocfilehash: d85fb8df7afdc5f4c3faecebcd24d11677798bc9
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365615"
---
### <a name="microsoftdotnetplatformabstractions-package-removed"></a><span data-ttu-id="72cf7-101">Pacchetto Microsoft. DotNet. PlatformAbstractions rimosso</span><span class="sxs-lookup"><span data-stu-id="72cf7-101">Microsoft.DotNet.PlatformAbstractions package removed</span></span>

<span data-ttu-id="72cf7-102">Non verranno generate nuove versioni del [pacchetto NuGet Microsoft. dotnet. PlatformAbstractions](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) .</span><span class="sxs-lookup"><span data-stu-id="72cf7-102">No new versions of the [Microsoft.DotNet.PlatformAbstractions NuGet package](https://www.nuget.org/packages/Microsoft.DotNet.PlatformAbstractions/) will be produced.</span></span>

#### <a name="change-description"></a><span data-ttu-id="72cf7-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="72cf7-103">Change description</span></span>

<span data-ttu-id="72cf7-104">In precedenza, le nuove versioni della <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> libreria venivano prodotte insieme alle nuove versioni di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="72cf7-104">Previously, new versions of the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library were produced alongside new versions of .NET Core.</span></span> <span data-ttu-id="72cf7-105">In futuro, non verrà aggiunta alcuna nuova funzionalità alla libreria e non verranno rilasciate nuove versioni principali.</span><span class="sxs-lookup"><span data-stu-id="72cf7-105">Going forward, no new functionality will be added to the library, and no new major versions will be released.</span></span> <span data-ttu-id="72cf7-106">Tuttavia, le versioni esistenti della libreria continueranno a funzionare e verranno gestite.</span><span class="sxs-lookup"><span data-stu-id="72cf7-106">However, existing versions of the library will continue to work and be serviced.</span></span>

<span data-ttu-id="72cf7-107">La <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> libreria si sovrappone alle API già stabilite in System. \* namespaces.</span><span class="sxs-lookup"><span data-stu-id="72cf7-107">The <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library overlaps with APIs that are already established in the System.\* namespaces.</span></span> <span data-ttu-id="72cf7-108">Alcune API, inoltre, non sono state <xref:Microsoft.DotNet.PlatformAbstractions> progettate con lo stesso livello di controllo e supporto a lungo termine come il resto del sistema. \* API.</span><span class="sxs-lookup"><span data-stu-id="72cf7-108">Also, some <xref:Microsoft.DotNet.PlatformAbstractions> APIs weren't designed with the same level of scrutiny and long-term supportability as the rest of the System.\* APIs.</span></span> <span data-ttu-id="72cf7-109">Ad esempio, <xref:Microsoft.DotNet.PlatformAbstractions> Usa l' `Platform` enumerazione per descrivere la piattaforma del sistema operativo corrente.</span><span class="sxs-lookup"><span data-stu-id="72cf7-109">For example, <xref:Microsoft.DotNet.PlatformAbstractions> uses the `Platform` enumeration to describe the current operating system platform.</span></span> <span data-ttu-id="72cf7-110">Questo progetto di enumerazione è stato rifiutato in modo esplicito al momento della progettazione dell' <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API, per consentire nuove piattaforme e flessibilità futura.</span><span class="sxs-lookup"><span data-stu-id="72cf7-110">This enumeration design was explicitly rejected when the <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> API was designed, to allow for new platforms and future flexibility.</span></span>

<span data-ttu-id="72cf7-111">Gli scenari abilitati dalla <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> libreria sono ora possibili senza di essa.</span><span class="sxs-lookup"><span data-stu-id="72cf7-111">The scenarios enabled by the <xref:Microsoft.DotNet.PlatformAbstractions?displayProperty=fullName> library are now possible without it.</span></span> <span data-ttu-id="72cf7-112">Le versioni esistenti continueranno a funzionare anche in .NET 5,0 e versioni successive e verranno gestite insieme alle versioni precedenti di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="72cf7-112">Existing versions will continue to work, even in .NET 5.0 and later, and will be serviced along with previous versions of .NET Core.</span></span> <span data-ttu-id="72cf7-113">Tuttavia, le nuove funzionalità non verranno aggiunte alla libreria.</span><span class="sxs-lookup"><span data-stu-id="72cf7-113">However, new functionality won't be added to the library.</span></span> <span data-ttu-id="72cf7-114">Verranno invece aggiunte nuove funzionalità ad altre librerie e API.</span><span class="sxs-lookup"><span data-stu-id="72cf7-114">Instead, new functionality will be added to other libraries and APIs.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="72cf7-115">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="72cf7-115">Version introduced</span></span>

<span data-ttu-id="72cf7-116">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="72cf7-116">5.0 Preview 6</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="72cf7-117">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="72cf7-117">Recommended action</span></span>

- <span data-ttu-id="72cf7-118">È possibile continuare a usare le versioni precedenti della libreria se soddisfano i requisiti.</span><span class="sxs-lookup"><span data-stu-id="72cf7-118">You can continue to use older versions of the library if they meet your requirements.</span></span>

- <span data-ttu-id="72cf7-119">Se le versioni precedenti non soddisfano i requisiti, sostituire gli utilizzi delle `PlatformAbstractions` API con le sostituzioni consigliate.</span><span class="sxs-lookup"><span data-stu-id="72cf7-119">If the older versions don't meet your requirements, replace usages of the `PlatformAbstractions` APIs with the recommended replacements.</span></span>

  | <span data-ttu-id="72cf7-120">`PlatformAbstractions`API</span><span class="sxs-lookup"><span data-stu-id="72cf7-120">`PlatformAbstractions` API</span></span> | <span data-ttu-id="72cf7-121">Sostituzione consigliata</span><span class="sxs-lookup"><span data-stu-id="72cf7-121">Recommended replacement</span></span> |
  |-|-|
  | `ApplicationEnvironment.ApplicationBasePath` | <xref:System.AppContext.BaseDirectory?displayProperty=nameWithType> |
  | <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner> | <xref:System.HashCode?displayProperty=nameWithType> |
  | `RuntimeEnvironment.GetRuntimeIdentifier()` | <xref:System.Runtime.InteropServices.RuntimeInformation.RuntimeIdentifier?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemPlatform` | <xref:System.Runtime.InteropServices.RuntimeInformation.IsOSPlatform(System.Runtime.InteropServices.OSPlatform)?displayProperty=nameWithType> |
  | `RuntimeEnvironment.RuntimeArchitecture` | <xref:System.Runtime.InteropServices.RuntimeInformation.ProcessArchitecture?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystem` | <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> |
  | `RuntimeEnvironment.OperatingSystemVersion` | <span data-ttu-id="72cf7-122"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> e <xref:System.Environment.OSVersion?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="72cf7-122"><xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> and <xref:System.Environment.OSVersion?displayProperty=nameWithType></span></span> |

  > [!NOTE]
  > <span data-ttu-id="72cf7-123">La maggior parte dei casi d'uso per `RuntimeEnvironment.OperatingSystem` e `RuntimeEnvironment.OperatingSystemVersion` è a scopo di visualizzazione, ad esempio, la visualizzazione di un utente, la registrazione e la telemetria.</span><span class="sxs-lookup"><span data-stu-id="72cf7-123">Most use cases for `RuntimeEnvironment.OperatingSystem` and `RuntimeEnvironment.OperatingSystemVersion` are for display purposes, for example, displaying to a user, logging, and telemetry.</span></span> <span data-ttu-id="72cf7-124">Non è consigliabile prendere decisioni in fase di esecuzione in base a una versione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="72cf7-124">It's not recommended to make run-time decisions based on an operating system (OS) version.</span></span> <span data-ttu-id="72cf7-125"><xref:System.Environment.OSVersion?displayProperty=nameWithType>restituisce ora la versione corretta per i sistemi operativi Windows e macOS.</span><span class="sxs-lookup"><span data-stu-id="72cf7-125"><xref:System.Environment.OSVersion?displayProperty=nameWithType> now returns the correct version for Windows and macOS operating systems.</span></span> <span data-ttu-id="72cf7-126">Tuttavia, per la maggior parte delle distribuzioni UNIX, ciò che è considerato la "versione del sistema operativo" non è altrettanto semplice.</span><span class="sxs-lookup"><span data-stu-id="72cf7-126">However, for most Unix distributions, what is considered to be the "OS version" is not as straightforward.</span></span> <span data-ttu-id="72cf7-127">Ad esempio, potrebbe essere la versione del kernel Linux o la versione della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="72cf7-127">For example, it could be the Linux kernel version, or it could be the distro version.</span></span> <span data-ttu-id="72cf7-128">Per la maggior parte delle piattaforme UNIX, <xref:System.Environment.OSVersion?displayProperty=nameWithType> e <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> restituiscono la versione restituita da `uname` .</span><span class="sxs-lookup"><span data-stu-id="72cf7-128">For most Unix platforms, <xref:System.Environment.OSVersion?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.RuntimeInformation.OSDescription?displayProperty=nameWithType> return the version that's returned by `uname`.</span></span> <span data-ttu-id="72cf7-129">Per ottenere il nome della distro Linux e le informazioni sulla versione, l'approccio consigliato consiste nel leggere il file */etc/OS-release* .</span><span class="sxs-lookup"><span data-stu-id="72cf7-129">To get the Linux distro name and version information, the recommended approach is to read the */etc/os-release* file.</span></span>

#### <a name="category"></a><span data-ttu-id="72cf7-130">Category</span><span class="sxs-lookup"><span data-stu-id="72cf7-130">Category</span></span>

<span data-ttu-id="72cf7-131">Principali librerie .NET</span><span class="sxs-lookup"><span data-stu-id="72cf7-131">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="72cf7-132">API interessate</span><span class="sxs-lookup"><span data-stu-id="72cf7-132">Affected APIs</span></span>

- `Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- <xref:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner?displayProperty=fullName>
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier()`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

<!--

#### Affected APIs

- `P:Microsoft.DotNet.PlatformAbstractions.ApplicationEnvironment.ApplicationBasePath`
- `T:Microsoft.DotNet.PlatformAbstractions.HashCodeCombiner`
- `M:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.GetRuntimeIdentifier`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystem`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemPlatform`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.OperatingSystemVersion`
- `P:Microsoft.DotNet.PlatformAbstractions.RuntimeEnvironment.RuntimeArchitecture`

-->
