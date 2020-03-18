---
ms.openlocfilehash: b60f74947a537c602c7bd1a89587b76bd847c82a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937261"
---
### <a name="target-framework-net-framework-support-dropped"></a><span data-ttu-id="260a7-101">Framework di destinazione: il supporto di .NET Framework è stato eliminato</span><span class="sxs-lookup"><span data-stu-id="260a7-101">Target framework: .NET Framework support dropped</span></span>

<span data-ttu-id="260a7-102">A partire da ASP.NET Core 3.0, .NET Framework è un framework di destinazione non supportato.</span><span class="sxs-lookup"><span data-stu-id="260a7-102">Starting with ASP.NET Core 3.0, .NET Framework is an unsupported target framework.</span></span>

#### <a name="change-description"></a><span data-ttu-id="260a7-103">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="260a7-103">Change description</span></span>

<span data-ttu-id="260a7-104">.NET Framework 4.8 è l'ultima versione principale di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="260a7-104">.NET Framework 4.8 is the last major version of .NET Framework.</span></span> <span data-ttu-id="260a7-105">Le nuove app ASP.NET Core devono essere compilate in .NET Core.New ASP.NET Core apps should be built on .NET Core.</span><span class="sxs-lookup"><span data-stu-id="260a7-105">New ASP.NET Core apps should be built on .NET Core.</span></span> <span data-ttu-id="260a7-106">A partire dalla versione .NET Core 3.0, è possibile considerare ASP.NET Core 3.0 come parte di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="260a7-106">Starting with the .NET Core 3.0 release, you can think of ASP.NET Core 3.0 as being part of .NET Core.</span></span>

<span data-ttu-id="260a7-107">I clienti che utilizzano ASP.NET Core con .NET Framework possono continuare in modo completamente supportato utilizzando la [versione 2.1 LTS](https://www.microsoft.com/net/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="260a7-107">Customers using ASP.NET Core with .NET Framework can continue in a fully supported fashion using the [2.1 LTS release](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span> <span data-ttu-id="260a7-108">Il supporto e la manutenzione per 2.1 continuano almeno fino al 21 agosto 2021.</span><span class="sxs-lookup"><span data-stu-id="260a7-108">Support and servicing for 2.1 continues until at least August 21, 2021.</span></span> <span data-ttu-id="260a7-109">Questa data è di tre anni dopo la dichiarazione della versione LTS in base ai [criteri di supporto di .NET.](https://www.microsoft.com/net/platform/support-policy)</span><span class="sxs-lookup"><span data-stu-id="260a7-109">This date is three years after declaration of the LTS release per the [.NET Support Policy](https://www.microsoft.com/net/platform/support-policy).</span></span> <span data-ttu-id="260a7-110">Il supporto per i pacchetti di ASP.NET Core 2.1 **in .NET Framework** si estenderà all'infinito, in modo simile ai criteri di [manutenzione per altri framework di ASP.NET basati su pacchetti.](https://dotnet.microsoft.com/platform/support/policy/aspnet)</span><span class="sxs-lookup"><span data-stu-id="260a7-110">Support for ASP.NET Core 2.1 packages **on .NET Framework** will extend indefinitely, similar to the [servicing policy for other package-based ASP.NET frameworks](https://dotnet.microsoft.com/platform/support/policy/aspnet).</span></span>

<span data-ttu-id="260a7-111">Per ulteriori informazioni sul porting da .NET Framework a .NET Core, vedere [Porting to .NET Core](~/docs/core/porting/index.md).</span><span class="sxs-lookup"><span data-stu-id="260a7-111">For more information about porting from .NET Framework to .NET Core, see [Porting to .NET Core](~/docs/core/porting/index.md).</span></span>

<span data-ttu-id="260a7-112">`Microsoft.Extensions`pacchetti (ad esempio la registrazione, inserimento di dipendenze e configurazione) e Entity Framework Core non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="260a7-112">`Microsoft.Extensions` packages (such as logging, dependency injection, and configuration) and Entity Framework Core aren't affected.</span></span> <span data-ttu-id="260a7-113">Continueranno a supportare .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="260a7-113">They'll continue to support .NET Standard.</span></span>

<span data-ttu-id="260a7-114">Per ulteriori informazioni sulla motivazione di questa modifica, vedere [il post di blog originale](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="260a7-114">For more information on the motivation for this change, see [the original blog post](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="260a7-115">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="260a7-115">Version introduced</span></span>

<span data-ttu-id="260a7-116">3.0</span><span class="sxs-lookup"><span data-stu-id="260a7-116">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="260a7-117">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="260a7-117">Old behavior</span></span>

<span data-ttu-id="260a7-118">ASP.NET Core apps could run on either .NET Core or .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="260a7-118">ASP.NET Core apps could run on either .NET Core or .NET Framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="260a7-119">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="260a7-119">New behavior</span></span>

<span data-ttu-id="260a7-120">ASP.NET Core apps can only be run on .NET Core.</span><span class="sxs-lookup"><span data-stu-id="260a7-120">ASP.NET Core apps can only be run on .NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="260a7-121">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="260a7-121">Recommended action</span></span>

<span data-ttu-id="260a7-122">eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="260a7-122">Take one of the following actions:</span></span>

- <span data-ttu-id="260a7-123">Mantieni la tua app su ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="260a7-123">Keep your app on ASP.NET Core 2.1.</span></span>
- <span data-ttu-id="260a7-124">Eseguire la migrazione dell'app e delle dipendenze a .NET Core.Migrate your app and dependencies to .NET Core.</span><span class="sxs-lookup"><span data-stu-id="260a7-124">Migrate your app and dependencies to .NET Core.</span></span>

#### <a name="category"></a><span data-ttu-id="260a7-125">Category</span><span class="sxs-lookup"><span data-stu-id="260a7-125">Category</span></span>

<span data-ttu-id="260a7-126">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="260a7-126">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="260a7-127">API interessate</span><span class="sxs-lookup"><span data-stu-id="260a7-127">Affected APIs</span></span>

<span data-ttu-id="260a7-128">nessuno</span><span class="sxs-lookup"><span data-stu-id="260a7-128">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
