---
ms.openlocfilehash: b60f74947a537c602c7bd1a89587b76bd847c82a
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937261"
---
### <a name="target-framework-net-framework-support-dropped"></a><span data-ttu-id="9028c-101">Framework di destinazione: supporto .NET Framework eliminato</span><span class="sxs-lookup"><span data-stu-id="9028c-101">Target framework: .NET Framework support dropped</span></span>

<span data-ttu-id="9028c-102">A partire da ASP.NET Core 3,0, .NET Framework è un Framework di destinazione non supportato.</span><span class="sxs-lookup"><span data-stu-id="9028c-102">Starting with ASP.NET Core 3.0, .NET Framework is an unsupported target framework.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9028c-103">Descrizione delle modifiche</span><span class="sxs-lookup"><span data-stu-id="9028c-103">Change description</span></span>

<span data-ttu-id="9028c-104">.NET Framework 4,8 è l'ultima versione principale di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9028c-104">.NET Framework 4.8 is the last major version of .NET Framework.</span></span> <span data-ttu-id="9028c-105">Le nuove app ASP.NET Core devono essere compilate in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9028c-105">New ASP.NET Core apps should be built on .NET Core.</span></span> <span data-ttu-id="9028c-106">A partire dalla versione di .NET Core 3,0, è possibile pensare a ASP.NET Core 3,0 come parte di .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9028c-106">Starting with the .NET Core 3.0 release, you can think of ASP.NET Core 3.0 as being part of .NET Core.</span></span>

<span data-ttu-id="9028c-107">I clienti che usano ASP.NET Core con .NET Framework possono continuare in modo completamente supportato usando la [versione LTS 2,1](https://www.microsoft.com/net/download/dotnet-core/2.1).</span><span class="sxs-lookup"><span data-stu-id="9028c-107">Customers using ASP.NET Core with .NET Framework can continue in a fully supported fashion using the [2.1 LTS release](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span> <span data-ttu-id="9028c-108">Il supporto e la manutenzione per 2,1 continuano fino ad almeno il 21 agosto 2021.</span><span class="sxs-lookup"><span data-stu-id="9028c-108">Support and servicing for 2.1 continues until at least August 21, 2021.</span></span> <span data-ttu-id="9028c-109">Questa data è di tre anni dopo la dichiarazione della versione LTS per i [criteri di supporto .NET](https://www.microsoft.com/net/platform/support-policy).</span><span class="sxs-lookup"><span data-stu-id="9028c-109">This date is three years after declaration of the LTS release per the [.NET Support Policy](https://www.microsoft.com/net/platform/support-policy).</span></span> <span data-ttu-id="9028c-110">Il supporto per i pacchetti ASP.NET Core 2,1 **in .NET Framework** si estenderà a tempo indefinito, in modo analogo ai [criteri di manutenzione per altri framework ASP.NET basati su pacchetti](https://dotnet.microsoft.com/platform/support/policy/aspnet).</span><span class="sxs-lookup"><span data-stu-id="9028c-110">Support for ASP.NET Core 2.1 packages **on .NET Framework** will extend indefinitely, similar to the [servicing policy for other package-based ASP.NET frameworks](https://dotnet.microsoft.com/platform/support/policy/aspnet).</span></span>

<span data-ttu-id="9028c-111">Per altre informazioni sul porting da .NET Framework a .NET Core, vedere [porting to .NET Core](~/docs/core/porting/index.md).</span><span class="sxs-lookup"><span data-stu-id="9028c-111">For more information about porting from .NET Framework to .NET Core, see [Porting to .NET Core](~/docs/core/porting/index.md).</span></span>

<span data-ttu-id="9028c-112">i pacchetti `Microsoft.Extensions` (ad esempio registrazione, inserimento di dipendenze e configurazione) e Entity Framework Core non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="9028c-112">`Microsoft.Extensions` packages (such as logging, dependency injection, and configuration) and Entity Framework Core aren't affected.</span></span> <span data-ttu-id="9028c-113">Continueranno a supportare .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="9028c-113">They'll continue to support .NET Standard.</span></span>

<span data-ttu-id="9028c-114">Per ulteriori informazioni sulla motivazione di questa modifica, vedere [il post di Blog originale](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="9028c-114">For more information on the motivation for this change, see [the original blog post](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9028c-115">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="9028c-115">Version introduced</span></span>

<span data-ttu-id="9028c-116">3.0</span><span class="sxs-lookup"><span data-stu-id="9028c-116">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9028c-117">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="9028c-117">Old behavior</span></span>

<span data-ttu-id="9028c-118">ASP.NET Core app possono essere eseguite in .NET Core o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9028c-118">ASP.NET Core apps could run on either .NET Core or .NET Framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9028c-119">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="9028c-119">New behavior</span></span>

<span data-ttu-id="9028c-120">ASP.NET Core app possono essere eseguite solo in .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9028c-120">ASP.NET Core apps can only be run on .NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9028c-121">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="9028c-121">Recommended action</span></span>

<span data-ttu-id="9028c-122">Eseguire una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9028c-122">Take one of the following actions:</span></span>

- <span data-ttu-id="9028c-123">Mantieni l'app ASP.NET Core 2,1.</span><span class="sxs-lookup"><span data-stu-id="9028c-123">Keep your app on ASP.NET Core 2.1.</span></span>
- <span data-ttu-id="9028c-124">Eseguire la migrazione dell'app e delle dipendenze a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9028c-124">Migrate your app and dependencies to .NET Core.</span></span>

#### <a name="category"></a><span data-ttu-id="9028c-125">Categoria</span><span class="sxs-lookup"><span data-stu-id="9028c-125">Category</span></span>

<span data-ttu-id="9028c-126">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9028c-126">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9028c-127">API interessate</span><span class="sxs-lookup"><span data-stu-id="9028c-127">Affected APIs</span></span>

<span data-ttu-id="9028c-128">nessuna</span><span class="sxs-lookup"><span data-stu-id="9028c-128">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
