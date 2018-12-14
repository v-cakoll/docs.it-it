---
title: Comando dotnet new - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
author: mairaw
ms.author: mairaw
ms.date: 10/24/2018
ms.openlocfilehash: a8d486f569f31d68d5659ac6a80d615474ef2506
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131482"
---
# <a name="dotnet-new"></a><span data-ttu-id="e73ee-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e73ee-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e73ee-104">nome</span><span class="sxs-lookup"><span data-stu-id="e73ee-104">Name</span></span>

<span data-ttu-id="e73ee-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e73ee-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="e73ee-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e73ee-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e73ee-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e73ee-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e73ee-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e73ee-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e73ee-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="e73ee-110">Description</span><span class="sxs-lookup"><span data-stu-id="e73ee-110">Description</span></span>

<span data-ttu-id="e73ee-111">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="e73ee-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="e73ee-112">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="e73ee-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="e73ee-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e73ee-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="e73ee-114">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="e73ee-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="e73ee-115">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="e73ee-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="e73ee-116">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="e73ee-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e73ee-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e73ee-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="e73ee-118">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="e73ee-118">The command contains a default list of templates.</span></span> <span data-ttu-id="e73ee-119">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="e73ee-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e73ee-120">La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="e73ee-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="e73ee-121">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="e73ee-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e73ee-122">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="e73ee-122">Template description</span></span>                          | <span data-ttu-id="e73ee-123">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="e73ee-123">Template name</span></span>    | <span data-ttu-id="e73ee-124">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="e73ee-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="e73ee-125">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="e73ee-125">Console application</span></span>                          | `console`        | <span data-ttu-id="e73ee-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e73ee-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e73ee-127">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="e73ee-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="e73ee-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e73ee-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e73ee-129">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="e73ee-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="e73ee-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e73ee-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e73ee-131">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="e73ee-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="e73ee-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e73ee-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e73ee-133">Progetto di NUnit test</span><span class="sxs-lookup"><span data-stu-id="e73ee-133">NUnit test project</span></span>                           | `nunit`          | <span data-ttu-id="e73ee-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e73ee-134">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e73ee-135">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="e73ee-135">Razor page</span></span>                                   | `page`           | <span data-ttu-id="e73ee-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-136">[C#]</span></span>          |
| <span data-ttu-id="e73ee-137">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e73ee-137">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="e73ee-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-138">[C#]</span></span>          |
| <span data-ttu-id="e73ee-139">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e73ee-139">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="e73ee-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-140">[C#]</span></span>          |
| <span data-ttu-id="e73ee-141">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="e73ee-141">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="e73ee-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-142">[C#], F#</span></span>      |
| <span data-ttu-id="e73ee-143">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e73ee-143">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="e73ee-144">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-144">[C#], F#</span></span>      |
| <span data-ttu-id="e73ee-145">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e73ee-145">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="e73ee-146">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="e73ee-146">`razor`, `webapp`</span></span>| <span data-ttu-id="e73ee-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-147">[C#]</span></span>          |
| <span data-ttu-id="e73ee-148">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="e73ee-148">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="e73ee-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-149">[C#]</span></span>          |
| <span data-ttu-id="e73ee-150">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="e73ee-150">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="e73ee-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-151">[C#]</span></span>          |
| <span data-ttu-id="e73ee-152">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="e73ee-152">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="e73ee-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-153">[C#]</span></span>          |
| <span data-ttu-id="e73ee-154">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e73ee-154">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="e73ee-155">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-155">[C#], F#</span></span>      |
| <span data-ttu-id="e73ee-156">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="e73ee-156">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="e73ee-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-157">[C#]</span></span>          |
| <span data-ttu-id="e73ee-158">File global.json</span><span class="sxs-lookup"><span data-stu-id="e73ee-158">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="e73ee-159">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="e73ee-159">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="e73ee-160">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="e73ee-160">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="e73ee-161">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="e73ee-161">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e73ee-162">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e73ee-162">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="e73ee-163">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="e73ee-163">The command contains a default list of templates.</span></span> <span data-ttu-id="e73ee-164">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="e73ee-164">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e73ee-165">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="e73ee-165">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="e73ee-166">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="e73ee-166">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e73ee-167">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="e73ee-167">Template description</span></span>                          | <span data-ttu-id="e73ee-168">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="e73ee-168">Template name</span></span> | <span data-ttu-id="e73ee-169">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="e73ee-169">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="e73ee-170">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="e73ee-170">Console application</span></span>                          | `console`     | <span data-ttu-id="e73ee-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e73ee-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e73ee-172">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="e73ee-172">Class library</span></span>                                | `classlib`    | <span data-ttu-id="e73ee-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e73ee-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e73ee-174">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="e73ee-174">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="e73ee-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e73ee-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e73ee-176">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="e73ee-176">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="e73ee-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e73ee-177">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e73ee-178">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="e73ee-178">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="e73ee-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-179">[C#], F#</span></span>      |
| <span data-ttu-id="e73ee-180">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e73ee-180">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="e73ee-181">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-181">[C#], F#</span></span>      |
| <span data-ttu-id="e73ee-182">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e73ee-182">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="e73ee-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-183">[C#]</span></span>          |
| <span data-ttu-id="e73ee-184">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="e73ee-184">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="e73ee-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-185">[C#]</span></span>          |
| <span data-ttu-id="e73ee-186">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="e73ee-186">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="e73ee-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-187">[C#]</span></span>          |
| <span data-ttu-id="e73ee-188">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="e73ee-188">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="e73ee-189">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-189">[C#]</span></span>          |
| <span data-ttu-id="e73ee-190">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e73ee-190">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="e73ee-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-191">[C#], F#</span></span>      |
| <span data-ttu-id="e73ee-192">File global.json</span><span class="sxs-lookup"><span data-stu-id="e73ee-192">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="e73ee-193">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="e73ee-193">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="e73ee-194">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="e73ee-194">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="e73ee-195">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="e73ee-195">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="e73ee-196">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="e73ee-196">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="e73ee-197">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e73ee-197">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="e73ee-198">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e73ee-198">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e73ee-199">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e73ee-199">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e73ee-200">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="e73ee-200">The command contains a default list of templates.</span></span> <span data-ttu-id="e73ee-201">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="e73ee-201">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="e73ee-202">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.x.</span><span class="sxs-lookup"><span data-stu-id="e73ee-202">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="e73ee-203">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="e73ee-203">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e73ee-204">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="e73ee-204">Template description</span></span>  | <span data-ttu-id="e73ee-205">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="e73ee-205">Template name</span></span> | <span data-ttu-id="e73ee-206">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="e73ee-206">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="e73ee-207">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="e73ee-207">Console application</span></span>  | `console`     | <span data-ttu-id="e73ee-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-208">[C#], F#</span></span>  |
| <span data-ttu-id="e73ee-209">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="e73ee-209">Class library</span></span>        | `classlib`    | <span data-ttu-id="e73ee-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-210">[C#], F#</span></span>  |
| <span data-ttu-id="e73ee-211">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="e73ee-211">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="e73ee-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-212">[C#], F#</span></span>  |
| <span data-ttu-id="e73ee-213">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="e73ee-213">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="e73ee-214">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-214">[C#], F#</span></span>  |
| <span data-ttu-id="e73ee-215">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="e73ee-215">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="e73ee-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-216">[C#]</span></span>      |
| <span data-ttu-id="e73ee-217">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e73ee-217">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="e73ee-218">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e73ee-218">[C#], F#</span></span>  |
| <span data-ttu-id="e73ee-219">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e73ee-219">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="e73ee-220">[C#]</span><span class="sxs-lookup"><span data-stu-id="e73ee-220">[C#]</span></span>      |
| <span data-ttu-id="e73ee-221">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="e73ee-221">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="e73ee-222">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="e73ee-222">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="e73ee-223">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="e73ee-223">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="e73ee-224">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e73ee-224">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e73ee-225">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e73ee-225">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="e73ee-226">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="e73ee-226">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e73ee-227">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-227">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e73ee-228">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="e73ee-228">Prints out help for the command.</span></span> <span data-ttu-id="e73ee-229">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-229">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="e73ee-230">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="e73ee-230">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e73ee-231">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-231">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e73ee-232">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-232">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="e73ee-233">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="e73ee-233">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="e73ee-234">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e73ee-234">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="e73ee-235">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-235">Lists templates containing the specified name.</span></span> <span data-ttu-id="e73ee-236">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="e73ee-236">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e73ee-237">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-237">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="e73ee-238">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="e73ee-238">The language of the template to create.</span></span> <span data-ttu-id="e73ee-239">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="e73ee-239">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e73ee-240">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="e73ee-240">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e73ee-241">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="e73ee-241">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e73ee-242">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-242">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e73ee-243">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-243">The name for the created output.</span></span> <span data-ttu-id="e73ee-244">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e73ee-244">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="e73ee-245">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="e73ee-245">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e73ee-246">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-246">Location to place the generated output.</span></span> <span data-ttu-id="e73ee-247">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e73ee-247">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="e73ee-248">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="e73ee-248">Filters templates based on available types.</span></span> <span data-ttu-id="e73ee-249">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="e73ee-249">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="e73ee-250">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="e73ee-250">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="e73ee-251">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="e73ee-251">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e73ee-252">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="e73ee-252">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="e73ee-253">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="e73ee-253">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e73ee-254">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e73ee-254">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="e73ee-255">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="e73ee-255">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e73ee-256">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-256">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e73ee-257">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="e73ee-257">Prints out help for the command.</span></span> <span data-ttu-id="e73ee-258">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-258">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="e73ee-259">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="e73ee-259">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e73ee-260">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-260">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e73ee-261">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-261">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="e73ee-262">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="e73ee-262">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="e73ee-263">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e73ee-263">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="e73ee-264">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-264">Lists templates containing the specified name.</span></span> <span data-ttu-id="e73ee-265">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="e73ee-265">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e73ee-266">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-266">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="e73ee-267">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="e73ee-267">The language of the template to create.</span></span> <span data-ttu-id="e73ee-268">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="e73ee-268">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e73ee-269">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="e73ee-269">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e73ee-270">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="e73ee-270">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e73ee-271">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-271">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e73ee-272">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-272">The name for the created output.</span></span> <span data-ttu-id="e73ee-273">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e73ee-273">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e73ee-274">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-274">Location to place the generated output.</span></span> <span data-ttu-id="e73ee-275">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e73ee-275">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="e73ee-276">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="e73ee-276">Filters templates based on available types.</span></span> <span data-ttu-id="e73ee-277">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="e73ee-277">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="e73ee-278">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="e73ee-278">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="e73ee-279">Per disinstallare un modello con un valore `PATH` di origine, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="e73ee-279">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e73ee-280">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="e73ee-280">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="e73ee-281">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="e73ee-281">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="e73ee-282">Se non è possibile determinare l'argomento `PATH` o `NUGET_ID` necessario per disinstallare un modello, eseguendo `dotnet new --uninstall` senza un argomento, verranno elencati tutti i modelli installati e l'argomento necessario per disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="e73ee-282">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e73ee-283">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e73ee-283">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="e73ee-284">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-284">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="e73ee-285">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="e73ee-285">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="e73ee-286">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-286">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e73ee-287">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="e73ee-287">Prints out help for the command.</span></span> <span data-ttu-id="e73ee-288">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-288">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="e73ee-289">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-289">Lists templates containing the specified name.</span></span> <span data-ttu-id="e73ee-290">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="e73ee-290">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e73ee-291">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-291">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="e73ee-292">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="e73ee-292">The language of the template to create.</span></span> <span data-ttu-id="e73ee-293">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="e73ee-293">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e73ee-294">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="e73ee-294">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="e73ee-295">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="e73ee-295">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="e73ee-296">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-296">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e73ee-297">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-297">The name for the created output.</span></span> <span data-ttu-id="e73ee-298">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e73ee-298">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e73ee-299">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-299">Location to place the generated output.</span></span> <span data-ttu-id="e73ee-300">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e73ee-300">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="e73ee-301">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="e73ee-301">Template options</span></span>

<span data-ttu-id="e73ee-302">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e73ee-302">Each project template may have additional options available.</span></span> <span data-ttu-id="e73ee-303">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="e73ee-303">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e73ee-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e73ee-304">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="e73ee-305">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="e73ee-305">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="e73ee-306">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-306">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-307">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e73ee-307">**classlib**</span></span>

<span data-ttu-id="e73ee-308">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e73ee-308">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e73ee-309">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e73ee-309">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e73ee-310">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-310">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="e73ee-311">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-312">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="e73ee-312">**mstest, xunit**</span></span>

<span data-ttu-id="e73ee-313">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e73ee-313">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="e73ee-314">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-314">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-315">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="e73ee-315">**globaljson**</span></span>

<span data-ttu-id="e73ee-316">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e73ee-316">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="e73ee-317">**web**</span><span class="sxs-lookup"><span data-stu-id="e73ee-317">**web**</span></span>

<span data-ttu-id="e73ee-318">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-318">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="e73ee-319">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-319">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-320">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e73ee-320">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="e73ee-321">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="e73ee-321">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="e73ee-322">**webapi**</span><span class="sxs-lookup"><span data-stu-id="e73ee-322">**webapi**</span></span>

<span data-ttu-id="e73ee-323">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e73ee-323">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e73ee-324">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e73ee-324">The possible values are:</span></span>

- <span data-ttu-id="e73ee-325">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e73ee-325">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e73ee-326">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e73ee-326">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e73ee-327">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e73ee-327">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e73ee-328">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e73ee-328">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e73ee-329">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-329">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e73ee-330">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-330">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e73ee-331">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-331">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e73ee-332">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-332">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e73ee-333">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-333">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-334">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-334">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e73ee-335">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-335">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e73ee-336">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-336">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e73ee-337">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-337">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e73ee-338">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-338">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e73ee-339">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-339">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e73ee-340">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="e73ee-340">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e73ee-341">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-341">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e73ee-342">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-342">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e73ee-343">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-343">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e73ee-344">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-344">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e73ee-345">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-345">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e73ee-346">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="e73ee-346">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e73ee-347">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-347">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e73ee-348">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-348">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="e73ee-349">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="e73ee-349">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e73ee-350">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-350">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-351">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-351">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-352">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e73ee-352">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="e73ee-353">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-353">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e73ee-354">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="e73ee-354">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="e73ee-355">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="e73ee-355">**mvc, razor**</span></span>

<span data-ttu-id="e73ee-356">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e73ee-356">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e73ee-357">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e73ee-357">The possible values are:</span></span>

- <span data-ttu-id="e73ee-358">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e73ee-358">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e73ee-359">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="e73ee-359">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="e73ee-360">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e73ee-360">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e73ee-361">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e73ee-361">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e73ee-362">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="e73ee-362">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="e73ee-363">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e73ee-363">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e73ee-364">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-364">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e73ee-365">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-365">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e73ee-366">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-366">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e73ee-367">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-367">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e73ee-368">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-369">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-369">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="e73ee-370">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-371">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-371">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="e73ee-372">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-372">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-373">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-373">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e73ee-374">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-374">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e73ee-375">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-375">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e73ee-376">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-376">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e73ee-377">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-377">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e73ee-378">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-378">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e73ee-379">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="e73ee-379">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e73ee-380">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-380">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e73ee-381">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-381">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e73ee-382">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-382">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e73ee-383">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-383">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e73ee-384">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-384">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e73ee-385">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e73ee-385">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e73ee-386">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-386">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e73ee-387">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-387">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="e73ee-388">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="e73ee-388">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e73ee-389">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-389">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e73ee-390">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-390">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="e73ee-391">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-391">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="e73ee-392">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="e73ee-392">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e73ee-393">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-393">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-394">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-395">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e73ee-395">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="e73ee-396">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-396">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="e73ee-397">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="e73ee-397">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="e73ee-398">**page**</span><span class="sxs-lookup"><span data-stu-id="e73ee-398">**page**</span></span>

<span data-ttu-id="e73ee-399">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e73ee-400">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-400">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e73ee-401">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="e73ee-401">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="e73ee-402">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="e73ee-402">**viewimports**</span></span>

<span data-ttu-id="e73ee-403">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-403">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e73ee-404">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-404">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e73ee-405">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e73ee-405">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="e73ee-406">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="e73ee-406">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="e73ee-407">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-407">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-408">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e73ee-408">**classlib**</span></span>

<span data-ttu-id="e73ee-409">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e73ee-409">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e73ee-410">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e73ee-410">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e73ee-411">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-411">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="e73ee-412">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-413">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="e73ee-413">**mstest, xunit**</span></span>

<span data-ttu-id="e73ee-414">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e73ee-414">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="e73ee-415">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-415">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-416">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="e73ee-416">**globaljson**</span></span>

<span data-ttu-id="e73ee-417">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e73ee-417">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="e73ee-418">**web**</span><span class="sxs-lookup"><span data-stu-id="e73ee-418">**web**</span></span>

<span data-ttu-id="e73ee-419">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-419">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e73ee-420">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-420">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-421">**webapi**</span><span class="sxs-lookup"><span data-stu-id="e73ee-421">**webapi**</span></span>

<span data-ttu-id="e73ee-422">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e73ee-422">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e73ee-423">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e73ee-423">The possible values are:</span></span>

- <span data-ttu-id="e73ee-424">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e73ee-424">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e73ee-425">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e73ee-425">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e73ee-426">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e73ee-426">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e73ee-427">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e73ee-427">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e73ee-428">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-428">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e73ee-429">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-429">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e73ee-430">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-430">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e73ee-431">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-431">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e73ee-432">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-432">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-433">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-433">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e73ee-434">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-434">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e73ee-435">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-435">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e73ee-436">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-436">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e73ee-437">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-437">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e73ee-438">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-438">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e73ee-439">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="e73ee-439">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e73ee-440">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-440">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e73ee-441">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-441">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e73ee-442">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-442">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e73ee-443">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-443">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e73ee-444">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-444">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e73ee-445">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="e73ee-445">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e73ee-446">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-446">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e73ee-447">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-447">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e73ee-448">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="e73ee-448">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e73ee-449">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-449">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-450">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-450">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-451">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="e73ee-451">**mvc, razor**</span></span>

<span data-ttu-id="e73ee-452">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e73ee-452">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e73ee-453">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e73ee-453">The possible values are:</span></span>

- <span data-ttu-id="e73ee-454">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e73ee-454">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e73ee-455">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="e73ee-455">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="e73ee-456">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e73ee-456">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e73ee-457">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e73ee-457">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e73ee-458">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="e73ee-458">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="e73ee-459">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e73ee-459">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e73ee-460">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-460">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e73ee-461">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-461">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e73ee-462">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-462">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e73ee-463">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-463">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e73ee-464">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-465">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-465">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="e73ee-466">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-467">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-467">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="e73ee-468">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-468">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-469">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-469">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e73ee-470">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-470">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e73ee-471">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-471">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e73ee-472">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-472">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e73ee-473">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-473">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e73ee-474">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-474">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e73ee-475">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="e73ee-475">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e73ee-476">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-476">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e73ee-477">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-477">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e73ee-478">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e73ee-478">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e73ee-479">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-479">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e73ee-480">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-480">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e73ee-481">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e73ee-481">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e73ee-482">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-482">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e73ee-483">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-483">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="e73ee-484">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="e73ee-484">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e73ee-485">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-485">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e73ee-486">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-486">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e73ee-487">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-487">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="e73ee-488">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="e73ee-488">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e73ee-489">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-489">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e73ee-490">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e73ee-490">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e73ee-491">**page**</span><span class="sxs-lookup"><span data-stu-id="e73ee-491">**page**</span></span>

<span data-ttu-id="e73ee-492">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e73ee-493">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-493">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e73ee-494">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="e73ee-494">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="e73ee-495">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="e73ee-495">**viewimports**</span></span>

<span data-ttu-id="e73ee-496">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="e73ee-496">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e73ee-497">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-497">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e73ee-498">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e73ee-498">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e73ee-499">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="e73ee-499">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="e73ee-500">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e73ee-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e73ee-501">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-501">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="e73ee-502">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-502">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="e73ee-503">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e73ee-503">**classlib**</span></span>

<span data-ttu-id="e73ee-504">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e73ee-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e73ee-505">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-505">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="e73ee-506">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-506">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="e73ee-507">**mvc**</span><span class="sxs-lookup"><span data-stu-id="e73ee-507">**mvc**</span></span>

<span data-ttu-id="e73ee-508">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e73ee-508">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e73ee-509">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-509">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="e73ee-510">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-510">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="e73ee-511">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e73ee-511">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="e73ee-512">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-512">Values: `None` or `Individual`.</span></span> <span data-ttu-id="e73ee-513">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-513">The default value is `None`.</span></span>

<span data-ttu-id="e73ee-514">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="e73ee-514">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="e73ee-515">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-515">Values: `true` or `false`.</span></span> <span data-ttu-id="e73ee-516">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="e73ee-516">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="e73ee-517">Esempi</span><span class="sxs-lookup"><span data-stu-id="e73ee-517">Examples</span></span>

<span data-ttu-id="e73ee-518">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="e73ee-518">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="e73ee-519">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="e73ee-519">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="e73ee-520">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="e73ee-520">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="e73ee-521">Creare una nuova applicazione xUnit:</span><span class="sxs-lookup"><span data-stu-id="e73ee-521">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="e73ee-522">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="e73ee-522">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="e73ee-523">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="e73ee-523">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="e73ee-524">Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):</span><span class="sxs-lookup"><span data-stu-id="e73ee-524">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="e73ee-525">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e73ee-525">See also</span></span>

* [<span data-ttu-id="e73ee-526">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e73ee-526">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="e73ee-527">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e73ee-527">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="e73ee-528">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="e73ee-528">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="e73ee-529">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e73ee-529">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
