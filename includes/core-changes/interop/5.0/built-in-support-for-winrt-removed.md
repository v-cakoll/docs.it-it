---
ms.openlocfilehash: d21b2e092d460fdfc367d0f490228ed44ad5c6cc
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365649"
---
### <a name="built-in-support-for-winrt-is-removed-from-net"></a><span data-ttu-id="35d4a-101">Il supporto predefinito per WinRT è stato rimosso da .NET</span><span class="sxs-lookup"><span data-stu-id="35d4a-101">Built-in support for WinRT is removed from .NET</span></span>

<span data-ttu-id="35d4a-102">Il supporto incorporato per l'utilizzo delle API di [Windows Runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) in .NET è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="35d4a-102">Built-in support for consumption of [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) APIs in .NET is removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="35d4a-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="35d4a-103">Version introduced</span></span>

<span data-ttu-id="35d4a-104">5,0 Preview 6</span><span class="sxs-lookup"><span data-stu-id="35d4a-104">5.0 Preview 6</span></span>

#### <a name="change-description"></a><span data-ttu-id="35d4a-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="35d4a-105">Change description</span></span>

<span data-ttu-id="35d4a-106">In precedenza, CoreCLR poteva usare [i file di metadati Windows (WinMD)](/uwp/winrt-cref/winmd-files) in Active e utilizzare i tipi WinRT.</span><span class="sxs-lookup"><span data-stu-id="35d4a-106">Previously, CoreCLR could consume [Windows metadata (WinMD) files](/uwp/winrt-cref/winmd-files) to active and consume WinRT types.</span></span> <span data-ttu-id="35d4a-107">A partire da .NET 5,0, CoreCLR non può più utilizzare direttamente i file WinMD.</span><span class="sxs-lookup"><span data-stu-id="35d4a-107">Starting in .NET 5.0, CoreCLR can no longer consume WinMD files directly.</span></span>

<span data-ttu-id="35d4a-108">Se si tenta di fare riferimento a un assembly non supportato, si otterrà <xref:System.IO.FileNotFoundException> .</span><span class="sxs-lookup"><span data-stu-id="35d4a-108">If you attempt to reference an unsupported assembly, you'll get a <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="35d4a-109">Se si attiva una classe WinRT, si otterrà <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="35d4a-109">If you activate a WinRT class, you'll get a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="35d4a-110">Questa modifica di rilievo è stata apportata per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="35d4a-110">This breaking change was made for the following reasons:</span></span>

- <span data-ttu-id="35d4a-111">WinRT può quindi essere sviluppato e migliorato separatamente dal runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="35d4a-111">So WinRT can be developed and improved separately from the .NET runtime.</span></span>
- <span data-ttu-id="35d4a-112">Per la simmetria con i sistemi di interoperabilità forniti per altri sistemi operativi, ad esempio iOS e Android.</span><span class="sxs-lookup"><span data-stu-id="35d4a-112">For symmetry with interop systems provided for other operating systems, such as iOS and Android.</span></span>
- <span data-ttu-id="35d4a-113">Per sfruttare le altre funzionalità di .NET, ad esempio le funzionalità di C#, IL collegamento Intermediate Language (IL) e la compilazione AOT (Ahead of Time).</span><span class="sxs-lookup"><span data-stu-id="35d4a-113">To take advantage of other .NET features, such as C# features, intermediate language (IL) linking, and ahead-of-time (AOT) compilation.</span></span>
- <span data-ttu-id="35d4a-114">Per semplificare la codebase del runtime .NET.</span><span class="sxs-lookup"><span data-stu-id="35d4a-114">To simplify the .NET runtime codebase.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="35d4a-115">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="35d4a-115">Recommended action</span></span>

- <span data-ttu-id="35d4a-116">Rimuovere i riferimenti al [pacchetto Microsoft. Windows. Sdk. Contracts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts) e sostituirli con i riferimenti al [pacchetto Microsoft.Windows.Sdk.NET](https://www.nuget.org/packages/microsoft.windows.sdk.net).</span><span class="sxs-lookup"><span data-stu-id="35d4a-116">Remove references to the [Microsoft.Windows.SDK.Contracts package](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts) and replace them with references to the [Microsoft.Windows.SDK.NET package](https://www.nuget.org/packages/microsoft.windows.sdk.net).</span></span>

- <span data-ttu-id="35d4a-117">Usare la catena di strumenti [C#/WinRT](/windows/uwp/csharp-winrt/) per generare o personalizzare i tipi e le API WinRT in .NET 5,0 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="35d4a-117">Use the [C#/WinRT](/windows/uwp/csharp-winrt/) tool chain to generate or customize WinRT APIs and types in .NET 5.0 and later versions.</span></span>

#### <a name="category"></a><span data-ttu-id="35d4a-118">Category</span><span class="sxs-lookup"><span data-stu-id="35d4a-118">Category</span></span>

<span data-ttu-id="35d4a-119">Interoperabilità</span><span class="sxs-lookup"><span data-stu-id="35d4a-119">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="35d4a-120">API interessate</span><span class="sxs-lookup"><span data-stu-id="35d4a-120">Affected APIs</span></span>

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

-->
