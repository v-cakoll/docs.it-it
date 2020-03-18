---
ms.openlocfilehash: be1fad236dd3eed047b010e93285aec8bc607b61
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394179"
---
### <a name="hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced"></a><span data-ttu-id="96a77-101">Hosting: tipi IHostingEnvironment e IApplicationLifetime contrassegnati come obsoleti e sostituiti</span><span class="sxs-lookup"><span data-stu-id="96a77-101">Hosting: IHostingEnvironment and IApplicationLifetime types marked obsolete and replaced</span></span>

<span data-ttu-id="96a77-102">Sono stati introdotti nuovi `IHostingEnvironment` `IApplicationLifetime` tipi per sostituire i tipi esistenti.</span><span class="sxs-lookup"><span data-stu-id="96a77-102">New types have been introduced to replace existing `IHostingEnvironment` and `IApplicationLifetime` types.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="96a77-103">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="96a77-103">Version introduced</span></span>

<span data-ttu-id="96a77-104">3.0</span><span class="sxs-lookup"><span data-stu-id="96a77-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="96a77-105">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="96a77-105">Old behavior</span></span>

<span data-ttu-id="96a77-106">C'erano `IHostingEnvironment` due `IApplicationLifetime` diversi `Microsoft.Extensions.Hosting` `Microsoft.AspNetCore.Hosting`e tipi da e .</span><span class="sxs-lookup"><span data-stu-id="96a77-106">There were two different `IHostingEnvironment` and `IApplicationLifetime` types from `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="96a77-107">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="96a77-107">New behavior</span></span>

<span data-ttu-id="96a77-108">I vecchi tipi sono stati contrassegnati come obsoleti e sostituiti con nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="96a77-108">The old types have been marked as obsolete and replaced with new types.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="96a77-109">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="96a77-109">Reason for change</span></span>

<span data-ttu-id="96a77-110">Quando `Microsoft.Extensions.Hosting` è stato introdotto in ASP.NET `IHostingEnvironment` Core `IApplicationLifetime` 2.1, alcuni tipi come e sono stati copiati da `Microsoft.AspNetCore.Hosting`.</span><span class="sxs-lookup"><span data-stu-id="96a77-110">When `Microsoft.Extensions.Hosting` was introduced in ASP.NET Core 2.1, some types like `IHostingEnvironment` and `IApplicationLifetime` were copied from `Microsoft.AspNetCore.Hosting`.</span></span> <span data-ttu-id="96a77-111">Alcune modifiche di ASP.NET Core 3.0 `Microsoft.Extensions.Hosting` `Microsoft.AspNetCore.Hosting` fanno sì che le app includano sia gli spazi dei nomi che quelli.</span><span class="sxs-lookup"><span data-stu-id="96a77-111">Some ASP.NET Core 3.0 changes cause apps to include both the `Microsoft.Extensions.Hosting` and `Microsoft.AspNetCore.Hosting` namespaces.</span></span> <span data-ttu-id="96a77-112">Qualsiasi utilizzo di tali tipi duplicati causa un errore del compilatore "riferimento ambiguo" quando viene fatto riferimento a entrambi gli spazi dei nomi.</span><span class="sxs-lookup"><span data-stu-id="96a77-112">Any use of those duplicate types causes an "ambiguous reference" compiler error when both namespaces are referenced.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="96a77-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="96a77-113">Recommended action</span></span>

<span data-ttu-id="96a77-114">Sostituiti tutti gli usi dei vecchi tipi con i tipi appena introdotti come di seguito:</span><span class="sxs-lookup"><span data-stu-id="96a77-114">Replaced any usages of the old types with the newly introduced types as below:</span></span>

<span data-ttu-id="96a77-115">**Tipi obsoleti (avviso):**</span><span class="sxs-lookup"><span data-stu-id="96a77-115">**Obsolete types (warning):**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>

<span data-ttu-id="96a77-116">**Nuovi tipi:**</span><span class="sxs-lookup"><span data-stu-id="96a77-116">**New types:**</span></span>

- <xref:Microsoft.Extensions.Hosting.IHostEnvironment?displayProperty=nameWithType>
- `Microsoft.AspNetCore.Hosting.IWebHostEnvironment : IHostEnvironment`
- <xref:Microsoft.Extensions.Hosting.IHostApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.Environments?displayProperty=nameWithType>

<span data-ttu-id="96a77-117">I `IHostEnvironment` `IsDevelopment` metodi `IsProduction` new e `Microsoft.Extensions.Hosting` extension si trovano nello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="96a77-117">The new `IHostEnvironment` `IsDevelopment` and `IsProduction` extension methods are in the `Microsoft.Extensions.Hosting` namespace.</span></span> <span data-ttu-id="96a77-118">Potrebbe essere necessario aggiungere tale spazio dei nomi al progetto.</span><span class="sxs-lookup"><span data-stu-id="96a77-118">That namespace may need to be added to your project.</span></span>

#### <a name="category"></a><span data-ttu-id="96a77-119">Category</span><span class="sxs-lookup"><span data-stu-id="96a77-119">Category</span></span>

<span data-ttu-id="96a77-120">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="96a77-120">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="96a77-121">API interessate</span><span class="sxs-lookup"><span data-stu-id="96a77-121">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Hosting.IHostingEnvironment?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.EnvironmentName?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IApplicationLifetime?displayProperty=nameWithType>
- <xref:Microsoft.Extensions.Hosting.IHostingEnvironment?displayProperty=nameWithType>

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.EnvironmentName`
- `T:Microsoft.AspNetCore.Hosting.IApplicationLifetime`
- `T:Microsoft.AspNetCore.Hosting.IHostingEnvironment`
- `T:Microsoft.Extensions.Hosting.EnvironmentName`
- `T:Microsoft.Extensions.Hosting.IApplicationLifetime`
- `T:Microsoft.Extensions.Hosting.IHostingEnvironment`

-->
