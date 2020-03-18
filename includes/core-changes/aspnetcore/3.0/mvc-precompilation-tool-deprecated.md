---
ms.openlocfilehash: 1e081c9f37fbd7ab754ce44ba89d7aa5cabfc219
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902017"
---
### <a name="mvc-precompilation-tool-deprecated"></a><span data-ttu-id="d62bf-101">MVC: strumento di precompilazione deprecato</span><span class="sxs-lookup"><span data-stu-id="d62bf-101">MVC: Precompilation tool deprecated</span></span>

<span data-ttu-id="d62bf-102">In ASP.NET Core 1.1, è stato introdotto il `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` pacchetto (strumento di precompilazione MVC) per aggiungere il supporto per la compilazione in fase di pubblicazione dei file Razor (file con estensione*cshtml).*</span><span class="sxs-lookup"><span data-stu-id="d62bf-102">In ASP.NET Core 1.1, the `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (MVC precompilation tool) package was introduced to add support for publish-time compilation of Razor files (*.cshtml* files).</span></span> <span data-ttu-id="d62bf-103">In ASP.NET Core 2.1, [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) è stato introdotto per espandere le funzionalità dello strumento di precompilazione.</span><span class="sxs-lookup"><span data-stu-id="d62bf-103">In ASP.NET Core 2.1, the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) was introduced to expand upon features of the precompilation tool.</span></span> <span data-ttu-id="d62bf-104">Razor SDK ha aggiunto il supporto per la compilazione in fase di compilazione e pubblicazione dei file Razor.</span><span class="sxs-lookup"><span data-stu-id="d62bf-104">The Razor SDK added support for build- and publish-time compilation of Razor files.</span></span> <span data-ttu-id="d62bf-105">L'SDK verifica la correttezza dei file *con estensione cshtml* in fase di compilazione migliorando al contempo il tempo di avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="d62bf-105">The SDK verifies the correctness of *.cshtml* files at build time while improving on app startup time.</span></span> <span data-ttu-id="d62bf-106">Razor SDK è attivato per impostazione predefinita e non è necessario alcun movimento per iniziare a usarlo.</span><span class="sxs-lookup"><span data-stu-id="d62bf-106">The Razor SDK is on by default, and no gesture is required to start using it.</span></span>

<span data-ttu-id="d62bf-107">In ASP.NET Core 3.0, lo strumento di precompilazione MVC di ASP.NET Core 1.1-era è stato rimosso.</span><span class="sxs-lookup"><span data-stu-id="d62bf-107">In ASP.NET Core 3.0, the ASP.NET Core 1.1-era MVC precompilation tool was removed.</span></span> <span data-ttu-id="d62bf-108">Le versioni precedenti del pacchetto continueranno a ricevere importanti correzioni di bug e di sicurezza nella versione della patch.</span><span class="sxs-lookup"><span data-stu-id="d62bf-108">Earlier package versions will continue receiving important bug and security fixes in the patch release.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d62bf-109">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="d62bf-109">Version introduced</span></span>

<span data-ttu-id="d62bf-110">3.0</span><span class="sxs-lookup"><span data-stu-id="d62bf-110">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="d62bf-111">Comportamento precedente</span><span class="sxs-lookup"><span data-stu-id="d62bf-111">Old behavior</span></span>

<span data-ttu-id="d62bf-112">Il `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` pacchetto è stato utilizzato per precompilare le visualizzazioni MVC Razor.</span><span class="sxs-lookup"><span data-stu-id="d62bf-112">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package was used to pre-compile MVC Razor views.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="d62bf-113">Nuovo comportamento</span><span class="sxs-lookup"><span data-stu-id="d62bf-113">New behavior</span></span>

<span data-ttu-id="d62bf-114">Razor SDK supporta in modo nativo questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="d62bf-114">The Razor SDK natively supports this functionality.</span></span> <span data-ttu-id="d62bf-115">Il `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` pacchetto non viene più aggiornato.</span><span class="sxs-lookup"><span data-stu-id="d62bf-115">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package is no longer updated.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="d62bf-116">Motivo della modifica</span><span class="sxs-lookup"><span data-stu-id="d62bf-116">Reason for change</span></span>

<span data-ttu-id="d62bf-117">Razor SDK fornisce ulteriori funzionalità e verifica la correttezza dei file *con estensione cshtml* in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="d62bf-117">The Razor SDK provides more functionality and verifies the correctness of *.cshtml* files at build time.</span></span> <span data-ttu-id="d62bf-118">L'SDK migliora anche il tempo di avvio dell'app.</span><span class="sxs-lookup"><span data-stu-id="d62bf-118">The SDK also improves app startup time.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d62bf-119">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="d62bf-119">Recommended action</span></span>

<span data-ttu-id="d62bf-120">Per gli utenti di ASP.NET Core 2.1 o versione successiva, eseguire l'aggiornamento per utilizzare il supporto nativo per la precompilazione [nell'SDK Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="d62bf-120">For users of ASP.NET Core 2.1 or later, update to use the native support for precompilation in the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span></span> <span data-ttu-id="d62bf-121">Se bug o funzionalità mancanti impediscono la migrazione a Razor SDK, aprire un problema in [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="d62bf-121">If bugs or missing features prevent migration to the Razor SDK, open an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="d62bf-122">Category</span><span class="sxs-lookup"><span data-stu-id="d62bf-122">Category</span></span>

<span data-ttu-id="d62bf-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d62bf-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d62bf-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="d62bf-124">Affected APIs</span></span>

<span data-ttu-id="d62bf-125">nessuno</span><span class="sxs-lookup"><span data-stu-id="d62bf-125">None</span></span>

<!-- 

### Affected APIs

Not detectable via API analysis

-->
