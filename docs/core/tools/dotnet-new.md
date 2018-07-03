---
title: Comando dotnet new - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
author: mairaw
ms.author: mairaw
ms.date: 06/12/2018
ms.openlocfilehash: f0ef91361dfbc2c2ba5532fbd607786289e98c69
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207782"
---
# <a name="dotnet-new"></a><span data-ttu-id="8acae-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="8acae-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="8acae-104">nome</span><span class="sxs-lookup"><span data-stu-id="8acae-104">Name</span></span>

<span data-ttu-id="8acae-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="8acae-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8acae-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="8acae-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8acae-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8acae-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8acae-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8acae-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8acae-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8acae-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="8acae-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8acae-110">Description</span></span>

<span data-ttu-id="8acae-111">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="8acae-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="8acae-112">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="8acae-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="8acae-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="8acae-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="8acae-114">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="8acae-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="8acae-115">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="8acae-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="8acae-116">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="8acae-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8acae-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8acae-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="8acae-118">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="8acae-118">The command contains a default list of templates.</span></span> <span data-ttu-id="8acae-119">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="8acae-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="8acae-120">La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="8acae-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="8acae-121">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="8acae-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="8acae-122">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="8acae-122">Template description</span></span>                          | <span data-ttu-id="8acae-123">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="8acae-123">Template name</span></span>   | <span data-ttu-id="8acae-124">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="8acae-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="8acae-125">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="8acae-125">Console application</span></span>                          | `console`       | <span data-ttu-id="8acae-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8acae-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="8acae-127">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="8acae-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="8acae-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8acae-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="8acae-129">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="8acae-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="8acae-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8acae-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="8acae-131">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="8acae-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="8acae-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8acae-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="8acae-133">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="8acae-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="8acae-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-134">[C#]</span></span>          |
| <span data-ttu-id="8acae-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="8acae-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="8acae-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-136">[C#]</span></span>          |
| <span data-ttu-id="8acae-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="8acae-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="8acae-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-138">[C#]</span></span>          |
| <span data-ttu-id="8acae-139">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="8acae-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="8acae-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-140">[C#], F#</span></span>      |
| <span data-ttu-id="8acae-141">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="8acae-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="8acae-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-142">[C#], F#</span></span>      |
| <span data-ttu-id="8acae-143">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8acae-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="8acae-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-144">[C#]</span></span>          |
| <span data-ttu-id="8acae-145">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="8acae-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="8acae-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-146">[C#]</span></span>          |
| <span data-ttu-id="8acae-147">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="8acae-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="8acae-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-148">[C#]</span></span>          |
| <span data-ttu-id="8acae-149">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="8acae-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="8acae-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-150">[C#]</span></span>          |
| <span data-ttu-id="8acae-151">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8acae-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="8acae-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-152">[C#], F#</span></span>      |
| <span data-ttu-id="8acae-153">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="8acae-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="8acae-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-154">[C#]</span></span>          |
| <span data-ttu-id="8acae-155">File global.json</span><span class="sxs-lookup"><span data-stu-id="8acae-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="8acae-156">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="8acae-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="8acae-157">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="8acae-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="8acae-158">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="8acae-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8acae-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8acae-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="8acae-160">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="8acae-160">The command contains a default list of templates.</span></span> <span data-ttu-id="8acae-161">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="8acae-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="8acae-162">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="8acae-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="8acae-163">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="8acae-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="8acae-164">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="8acae-164">Template description</span></span>                          | <span data-ttu-id="8acae-165">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="8acae-165">Template name</span></span> | <span data-ttu-id="8acae-166">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="8acae-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="8acae-167">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="8acae-167">Console application</span></span>                          | `console`     | <span data-ttu-id="8acae-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8acae-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="8acae-169">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="8acae-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="8acae-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8acae-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="8acae-171">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="8acae-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="8acae-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8acae-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="8acae-173">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="8acae-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="8acae-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="8acae-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="8acae-175">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="8acae-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="8acae-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-176">[C#], F#</span></span>      |
| <span data-ttu-id="8acae-177">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="8acae-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="8acae-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-178">[C#], F#</span></span>      |
| <span data-ttu-id="8acae-179">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8acae-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="8acae-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-180">[C#]</span></span>          |
| <span data-ttu-id="8acae-181">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="8acae-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="8acae-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-182">[C#]</span></span>          |
| <span data-ttu-id="8acae-183">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="8acae-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="8acae-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-184">[C#]</span></span>          |
| <span data-ttu-id="8acae-185">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="8acae-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="8acae-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-186">[C#]</span></span>          |
| <span data-ttu-id="8acae-187">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8acae-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="8acae-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-188">[C#], F#</span></span>      |
| <span data-ttu-id="8acae-189">File global.json</span><span class="sxs-lookup"><span data-stu-id="8acae-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="8acae-190">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="8acae-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="8acae-191">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="8acae-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="8acae-192">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="8acae-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="8acae-193">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="8acae-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="8acae-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="8acae-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="8acae-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="8acae-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8acae-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8acae-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="8acae-197">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="8acae-197">The command contains a default list of templates.</span></span> <span data-ttu-id="8acae-198">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="8acae-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="8acae-199">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.x.</span><span class="sxs-lookup"><span data-stu-id="8acae-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="8acae-200">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="8acae-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="8acae-201">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="8acae-201">Template description</span></span>  | <span data-ttu-id="8acae-202">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="8acae-202">Template name</span></span> | <span data-ttu-id="8acae-203">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="8acae-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="8acae-204">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="8acae-204">Console application</span></span>  | `console`     | <span data-ttu-id="8acae-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-205">[C#], F#</span></span>  |
| <span data-ttu-id="8acae-206">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="8acae-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="8acae-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-207">[C#], F#</span></span>  |
| <span data-ttu-id="8acae-208">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="8acae-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="8acae-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-209">[C#], F#</span></span>  |
| <span data-ttu-id="8acae-210">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="8acae-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="8acae-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-211">[C#], F#</span></span>  |
| <span data-ttu-id="8acae-212">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="8acae-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="8acae-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-213">[C#]</span></span>      |
| <span data-ttu-id="8acae-214">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8acae-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="8acae-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="8acae-215">[C#], F#</span></span>  |
| <span data-ttu-id="8acae-216">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8acae-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="8acae-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="8acae-217">[C#]</span></span>      |
| <span data-ttu-id="8acae-218">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="8acae-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="8acae-219">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="8acae-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="8acae-220">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="8acae-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="8acae-221">Opzioni</span><span class="sxs-lookup"><span data-stu-id="8acae-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8acae-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8acae-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="8acae-223">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="8acae-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="8acae-224">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="8acae-225">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="8acae-225">Prints out help for the command.</span></span> <span data-ttu-id="8acae-226">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="8acae-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="8acae-227">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="8acae-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8acae-228">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="8acae-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="8acae-229">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="8acae-230">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="8acae-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="8acae-231">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="8acae-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="8acae-232">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="8acae-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="8acae-233">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="8acae-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="8acae-234">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="8acae-235">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="8acae-235">The language of the template to create.</span></span> <span data-ttu-id="8acae-236">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="8acae-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8acae-237">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="8acae-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="8acae-238">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="8acae-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="8acae-239">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="8acae-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="8acae-240">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="8acae-240">The name for the created output.</span></span> <span data-ttu-id="8acae-241">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8acae-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="8acae-242">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="8acae-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="8acae-243">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-243">Location to place the generated output.</span></span> <span data-ttu-id="8acae-244">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8acae-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="8acae-245">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="8acae-245">Filters templates based on available types.</span></span> <span data-ttu-id="8acae-246">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="8acae-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="8acae-247">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="8acae-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="8acae-248">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="8acae-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="8acae-249">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="8acae-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="8acae-250">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="8acae-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8acae-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8acae-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="8acae-252">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="8acae-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="8acae-253">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="8acae-254">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="8acae-254">Prints out help for the command.</span></span> <span data-ttu-id="8acae-255">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="8acae-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="8acae-256">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="8acae-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="8acae-257">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="8acae-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="8acae-258">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="8acae-259">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="8acae-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="8acae-260">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="8acae-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="8acae-261">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="8acae-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="8acae-262">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="8acae-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="8acae-263">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="8acae-264">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="8acae-264">The language of the template to create.</span></span> <span data-ttu-id="8acae-265">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="8acae-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8acae-266">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="8acae-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="8acae-267">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="8acae-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="8acae-268">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="8acae-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="8acae-269">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="8acae-269">The name for the created output.</span></span> <span data-ttu-id="8acae-270">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8acae-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="8acae-271">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-271">Location to place the generated output.</span></span> <span data-ttu-id="8acae-272">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8acae-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="8acae-273">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="8acae-273">Filters templates based on available types.</span></span> <span data-ttu-id="8acae-274">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="8acae-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="8acae-275">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="8acae-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="8acae-276">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="8acae-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="8acae-277">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="8acae-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="8acae-278">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="8acae-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8acae-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8acae-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="8acae-280">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="8acae-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="8acae-281">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="8acae-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="8acae-282">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="8acae-283">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="8acae-283">Prints out help for the command.</span></span> <span data-ttu-id="8acae-284">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="8acae-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="8acae-285">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="8acae-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="8acae-286">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="8acae-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="8acae-287">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="8acae-288">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="8acae-288">The language of the template to create.</span></span> <span data-ttu-id="8acae-289">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="8acae-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="8acae-290">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="8acae-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="8acae-291">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="8acae-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="8acae-292">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="8acae-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="8acae-293">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="8acae-293">The name for the created output.</span></span> <span data-ttu-id="8acae-294">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8acae-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="8acae-295">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-295">Location to place the generated output.</span></span> <span data-ttu-id="8acae-296">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="8acae-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="8acae-297">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="8acae-297">Template options</span></span>

<span data-ttu-id="8acae-298">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="8acae-298">Each project template may have additional options available.</span></span> <span data-ttu-id="8acae-299">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="8acae-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="8acae-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="8acae-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="8acae-301">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="8acae-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="8acae-302">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="8acae-303">**classlib**</span></span>

<span data-ttu-id="8acae-304">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8acae-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8acae-305">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="8acae-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="8acae-306">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="8acae-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="8acae-307">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-308">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="8acae-308">**mstest, xunit**</span></span>

<span data-ttu-id="8acae-309">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="8acae-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="8acae-310">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="8acae-311">**globaljson**</span></span>

<span data-ttu-id="8acae-312">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="8acae-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="8acae-313">**web**</span><span class="sxs-lookup"><span data-stu-id="8acae-313">**web**</span></span>

<span data-ttu-id="8acae-314">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-314">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="8acae-315">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-316">**webapi**</span><span class="sxs-lookup"><span data-stu-id="8acae-316">**webapi**</span></span>

<span data-ttu-id="8acae-317">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="8acae-317">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8acae-318">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="8acae-318">The possible values are:</span></span>

- <span data-ttu-id="8acae-319">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="8acae-319">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="8acae-320">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="8acae-320">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="8acae-321">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="8acae-321">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="8acae-322">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="8acae-322">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="8acae-323">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-323">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8acae-324">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-324">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8acae-325">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="8acae-325">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="8acae-326">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-326">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8acae-327">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-327">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-328">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-328">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8acae-329">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-329">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8acae-330">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="8acae-330">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="8acae-331">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-331">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="8acae-332">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-332">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8acae-333">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="8acae-333">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="8acae-334">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="8acae-334">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="8acae-335">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-335">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8acae-336">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="8acae-336">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="8acae-337">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-337">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8acae-338">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-338">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8acae-339">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="8acae-339">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="8acae-340">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="8acae-340">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="8acae-341">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-341">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="8acae-342">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-342">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="8acae-343">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="8acae-343">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8acae-344">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-344">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-345">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-345">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-346">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="8acae-346">**mvc, razor**</span></span>

<span data-ttu-id="8acae-347">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="8acae-347">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8acae-348">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="8acae-348">The possible values are:</span></span>

- <span data-ttu-id="8acae-349">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="8acae-349">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="8acae-350">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="8acae-350">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="8acae-351">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="8acae-351">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="8acae-352">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="8acae-352">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="8acae-353">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="8acae-353">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="8acae-354">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="8acae-354">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="8acae-355">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-355">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8acae-356">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-356">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8acae-357">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="8acae-357">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="8acae-358">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-358">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8acae-359">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-359">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-360">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-360">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="8acae-361">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-361">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-362">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-362">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="8acae-363">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-363">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-364">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-364">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8acae-365">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-365">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8acae-366">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="8acae-366">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="8acae-367">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-367">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="8acae-368">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-368">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8acae-369">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="8acae-369">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="8acae-370">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="8acae-370">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="8acae-371">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8acae-372">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="8acae-372">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="8acae-373">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-373">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8acae-374">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-374">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8acae-375">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="8acae-375">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="8acae-376">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="8acae-376">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8acae-377">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-377">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8acae-378">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="8acae-378">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="8acae-379">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="8acae-379">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="8acae-380">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-380">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="8acae-381">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-381">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="8acae-382">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-382">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="8acae-383">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="8acae-383">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8acae-384">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-384">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-385">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-385">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-386">**page**</span><span class="sxs-lookup"><span data-stu-id="8acae-386">**page**</span></span>

<span data-ttu-id="8acae-387">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-387">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="8acae-388">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="8acae-388">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="8acae-389">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="8acae-389">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="8acae-390">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="8acae-390">**viewimports**</span></span>

<span data-ttu-id="8acae-391">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-391">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="8acae-392">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="8acae-392">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="8acae-393">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="8acae-393">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="8acae-394">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="8acae-394">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="8acae-395">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-395">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-396">**classlib**</span><span class="sxs-lookup"><span data-stu-id="8acae-396">**classlib**</span></span>

<span data-ttu-id="8acae-397">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8acae-397">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8acae-398">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="8acae-398">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="8acae-399">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="8acae-399">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="8acae-400">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-400">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-401">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="8acae-401">**mstest, xunit**</span></span>

<span data-ttu-id="8acae-402">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="8acae-402">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="8acae-403">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-404">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="8acae-404">**globaljson**</span></span>

<span data-ttu-id="8acae-405">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="8acae-405">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="8acae-406">**web**</span><span class="sxs-lookup"><span data-stu-id="8acae-406">**web**</span></span>

<span data-ttu-id="8acae-407">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-407">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="8acae-408">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-409">**webapi**</span><span class="sxs-lookup"><span data-stu-id="8acae-409">**webapi**</span></span>

<span data-ttu-id="8acae-410">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="8acae-410">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8acae-411">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="8acae-411">The possible values are:</span></span>

- <span data-ttu-id="8acae-412">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="8acae-412">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="8acae-413">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="8acae-413">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="8acae-414">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="8acae-414">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="8acae-415">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="8acae-415">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="8acae-416">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-416">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8acae-417">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-417">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8acae-418">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="8acae-418">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="8acae-419">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-419">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8acae-420">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-420">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-421">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-421">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8acae-422">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-422">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8acae-423">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="8acae-423">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="8acae-424">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-424">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="8acae-425">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-425">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="8acae-426">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="8acae-426">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="8acae-427">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="8acae-427">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="8acae-428">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-428">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8acae-429">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="8acae-429">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="8acae-430">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-430">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8acae-431">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-431">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8acae-432">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="8acae-432">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="8acae-433">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="8acae-433">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="8acae-434">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-434">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="8acae-435">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-435">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="8acae-436">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="8acae-436">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8acae-437">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-437">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-438">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-438">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-439">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="8acae-439">**mvc, razor**</span></span>

<span data-ttu-id="8acae-440">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="8acae-440">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="8acae-441">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="8acae-441">The possible values are:</span></span>

- <span data-ttu-id="8acae-442">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="8acae-442">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="8acae-443">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="8acae-443">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="8acae-444">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="8acae-444">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="8acae-445">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="8acae-445">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="8acae-446">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="8acae-446">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="8acae-447">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="8acae-447">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="8acae-448">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-448">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="8acae-449">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-449">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="8acae-450">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="8acae-450">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="8acae-451">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-451">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="8acae-452">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-452">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-453">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-453">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="8acae-454">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-454">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-455">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-455">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="8acae-456">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-456">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-457">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-457">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="8acae-458">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-458">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="8acae-459">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="8acae-459">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="8acae-460">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-460">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="8acae-461">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-461">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="8acae-462">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="8acae-462">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="8acae-463">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="8acae-463">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="8acae-464">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8acae-465">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="8acae-465">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="8acae-466">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="8acae-466">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="8acae-467">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-467">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="8acae-468">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="8acae-468">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="8acae-469">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="8acae-469">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="8acae-470">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-470">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="8acae-471">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="8acae-471">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="8acae-472">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="8acae-472">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="8acae-473">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="8acae-473">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="8acae-474">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-474">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="8acae-475">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-475">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="8acae-476">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="8acae-476">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="8acae-477">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="8acae-477">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="8acae-478">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="8acae-478">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="8acae-479">**page**</span><span class="sxs-lookup"><span data-stu-id="8acae-479">**page**</span></span>

<span data-ttu-id="8acae-480">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-480">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="8acae-481">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="8acae-481">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="8acae-482">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="8acae-482">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="8acae-483">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="8acae-483">**viewimports**</span></span>

<span data-ttu-id="8acae-484">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="8acae-484">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="8acae-485">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="8acae-485">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8acae-486">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8acae-486">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="8acae-487">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="8acae-487">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="8acae-488">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8acae-488">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8acae-489">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="8acae-489">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="8acae-490">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="8acae-490">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="8acae-491">**classlib**</span><span class="sxs-lookup"><span data-stu-id="8acae-491">**classlib**</span></span>

<span data-ttu-id="8acae-492">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8acae-492">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8acae-493">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="8acae-493">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="8acae-494">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="8acae-494">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="8acae-495">**mvc**</span><span class="sxs-lookup"><span data-stu-id="8acae-495">**mvc**</span></span>

<span data-ttu-id="8acae-496">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8acae-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="8acae-497">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="8acae-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="8acae-498">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="8acae-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="8acae-499">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="8acae-499">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="8acae-500">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="8acae-500">Values: `None` or `Individual`.</span></span> <span data-ttu-id="8acae-501">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="8acae-501">The default value is `None`.</span></span>

<span data-ttu-id="8acae-502">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="8acae-502">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="8acae-503">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="8acae-503">Values: `true` or `false`.</span></span> <span data-ttu-id="8acae-504">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="8acae-504">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="8acae-505">Esempi</span><span class="sxs-lookup"><span data-stu-id="8acae-505">Examples</span></span>

<span data-ttu-id="8acae-506">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="8acae-506">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="8acae-507">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="8acae-507">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="8acae-508">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="8acae-508">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="8acae-509">Creare una nuova applicazione xUnit:</span><span class="sxs-lookup"><span data-stu-id="8acae-509">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="8acae-510">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="8acae-510">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="8acae-511">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="8acae-511">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="8acae-512">Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):</span><span class="sxs-lookup"><span data-stu-id="8acae-512">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="8acae-513">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8acae-513">See also</span></span>

[<span data-ttu-id="8acae-514">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="8acae-514">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="8acae-515">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="8acae-515">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="8acae-516">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="8acae-516">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="8acae-517">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="8acae-517">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
