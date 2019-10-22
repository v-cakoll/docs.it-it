---
ms.openlocfilehash: 641233df165a1c2208a2185f2b6e99077f9a59d3
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394089"
---
### <a name="mvc-precompilation-tool-deprecated"></a><span data-ttu-id="627b8-101">MVC: strumento di precompilazione deprecato</span><span class="sxs-lookup"><span data-stu-id="627b8-101">MVC: Precompilation tool deprecated</span></span>

<span data-ttu-id="627b8-102">In ASP.NET Core 1,1, il pacchetto `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (strumento di precompilazione MVC) è stato introdotto per aggiungere il supporto per la compilazione in fase di pubblicazione dei file Razor (file con*estensione cshtml* ).</span><span class="sxs-lookup"><span data-stu-id="627b8-102">In ASP.NET Core 1.1, the `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (MVC precompilation tool) package was introduced to add support for publish-time compilation of Razor files (*.cshtml* files).</span></span> <span data-ttu-id="627b8-103">In ASP.NET Core 2,1, [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) è stato introdotto per espandersi sulle funzionalità dello strumento di precompilazione.</span><span class="sxs-lookup"><span data-stu-id="627b8-103">In ASP.NET Core 2.1, the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) was introduced to expand upon features of the precompilation tool.</span></span> <span data-ttu-id="627b8-104">Razor SDK ha aggiunto il supporto per la compilazione in fase di compilazione e di pubblicazione dei file Razor.</span><span class="sxs-lookup"><span data-stu-id="627b8-104">The Razor SDK added support for build- and publish-time compilation of Razor files.</span></span> <span data-ttu-id="627b8-105">L'SDK verifica la correttezza dei file con *estensione cshtml* in fase di compilazione, migliorando al tempo stesso l'avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="627b8-105">The SDK verifies the correctness of *.cshtml* files at build time while improving on app startup time.</span></span> <span data-ttu-id="627b8-106">Razor SDK è attiva per impostazione predefinita e non è necessario alcun movimento per iniziare a usarlo.</span><span class="sxs-lookup"><span data-stu-id="627b8-106">The Razor SDK is on by default, and no gesture is required to start using it.</span></span>

<span data-ttu-id="627b8-107">In ASP.NET Core 3,0 è stato rimosso lo strumento di precompilazione MVC ASP.NET Core 1,1-era.</span><span class="sxs-lookup"><span data-stu-id="627b8-107">In ASP.NET Core 3.0, the ASP.NET Core 1.1-era MVC precompilation tool was removed.</span></span> <span data-ttu-id="627b8-108">Le versioni precedenti del pacchetto continueranno a ricevere importanti correzioni di bug e sicurezza nella versione patch.</span><span class="sxs-lookup"><span data-stu-id="627b8-108">Earlier package versions will continue receiving important bug and security fixes in the patch release.</span></span> 

#### <a name="version-introduced"></a><span data-ttu-id="627b8-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="627b8-109">Version introduced</span></span>

<span data-ttu-id="627b8-110">3.0</span><span class="sxs-lookup"><span data-stu-id="627b8-110">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="627b8-111">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="627b8-111">Old behavior</span></span>

<span data-ttu-id="627b8-112">Il pacchetto `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` è stato usato per pre-compilare le visualizzazioni Razor MVC.</span><span class="sxs-lookup"><span data-stu-id="627b8-112">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package was used to pre-compile MVC Razor views.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="627b8-113">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="627b8-113">New behavior</span></span>

<span data-ttu-id="627b8-114">Razor SDK supporta questa funzionalità in modo nativo.</span><span class="sxs-lookup"><span data-stu-id="627b8-114">The Razor SDK natively supports this functionality.</span></span> <span data-ttu-id="627b8-115">Il pacchetto `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` non viene più aggiornato.</span><span class="sxs-lookup"><span data-stu-id="627b8-115">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package is no longer updated.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="627b8-116">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="627b8-116">Reason for change</span></span>

<span data-ttu-id="627b8-117">Razor SDK offre più funzionalità e verifica la correttezza dei file con *estensione cshtml* in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="627b8-117">The Razor SDK provides more functionality and verifies the correctness of *.cshtml* files at build time.</span></span> <span data-ttu-id="627b8-118">L'SDK migliora anche il tempo di avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="627b8-118">The SDK also improves app startup time.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="627b8-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="627b8-119">Recommended action</span></span>

<span data-ttu-id="627b8-120">Per gli utenti di ASP.NET Core 2,1 o versioni successive, eseguire l'aggiornamento per usare il supporto nativo per la precompilazione in [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="627b8-120">For users of ASP.NET Core 2.1 or later, update to use the native support for precompilation in the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span></span> <span data-ttu-id="627b8-121">Se i bug o le funzionalità mancanti impediscono la migrazione a Razor SDK, aprire un problema in [ASPNET/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span><span class="sxs-lookup"><span data-stu-id="627b8-121">If bugs or missing features prevent migration to the Razor SDK, open an issue at [aspnet/AspNetCore](https://github.com/aspnet/AspNetCore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="627b8-122">Category</span><span class="sxs-lookup"><span data-stu-id="627b8-122">Category</span></span>

<span data-ttu-id="627b8-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="627b8-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="627b8-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="627b8-124">Affected APIs</span></span>

<span data-ttu-id="627b8-125">Nessuno</span><span class="sxs-lookup"><span data-stu-id="627b8-125">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->