---
title: Comando dotnet new - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ae24c4145cc67ca863c07e4d22af8a1c2c2dd732
ms.sourcegitcommit: 3540f614fc94f77ca4ab58df66db2d0f4d52dfee
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2018
ms.locfileid: "34570463"
---
# <a name="dotnet-new"></a><span data-ttu-id="e20ad-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="e20ad-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="e20ad-104">nome</span><span class="sxs-lookup"><span data-stu-id="e20ad-104">Name</span></span>

<span data-ttu-id="e20ad-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e20ad-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="e20ad-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e20ad-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e20ad-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e20ad-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e20ad-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e20ad-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e20ad-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="e20ad-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e20ad-110">Description</span></span>

<span data-ttu-id="e20ad-111">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="e20ad-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="e20ad-112">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="e20ad-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="e20ad-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e20ad-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="e20ad-114">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="e20ad-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="e20ad-115">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="e20ad-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="e20ad-116">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="e20ad-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e20ad-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e20ad-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="e20ad-118">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="e20ad-118">The command contains a default list of templates.</span></span> <span data-ttu-id="e20ad-119">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="e20ad-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e20ad-120">La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="e20ad-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="e20ad-121">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="e20ad-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e20ad-122">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="e20ad-122">Template description</span></span>                          | <span data-ttu-id="e20ad-123">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="e20ad-123">Template name</span></span>   | <span data-ttu-id="e20ad-124">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="e20ad-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="e20ad-125">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="e20ad-125">Console application</span></span>                          | `console`       | <span data-ttu-id="e20ad-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e20ad-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e20ad-127">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="e20ad-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="e20ad-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e20ad-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e20ad-129">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="e20ad-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="e20ad-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e20ad-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e20ad-131">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="e20ad-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="e20ad-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e20ad-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e20ad-133">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="e20ad-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="e20ad-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-134">[C#]</span></span>          |
| <span data-ttu-id="e20ad-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e20ad-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="e20ad-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-136">[C#]</span></span>          |
| <span data-ttu-id="e20ad-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e20ad-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="e20ad-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-138">[C#]</span></span>          |
| <span data-ttu-id="e20ad-139">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="e20ad-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="e20ad-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-140">[C#], F#</span></span>      |
| <span data-ttu-id="e20ad-141">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e20ad-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="e20ad-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-142">[C#], F#</span></span>      |
| <span data-ttu-id="e20ad-143">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e20ad-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="e20ad-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-144">[C#]</span></span>          |
| <span data-ttu-id="e20ad-145">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="e20ad-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="e20ad-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-146">[C#]</span></span>          |
| <span data-ttu-id="e20ad-147">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="e20ad-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="e20ad-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-148">[C#]</span></span>          |
| <span data-ttu-id="e20ad-149">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="e20ad-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="e20ad-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-150">[C#]</span></span>          |
| <span data-ttu-id="e20ad-151">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e20ad-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="e20ad-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-152">[C#], F#</span></span>      |
| <span data-ttu-id="e20ad-153">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="e20ad-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="e20ad-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-154">[C#]</span></span>          |
| <span data-ttu-id="e20ad-155">File global.json</span><span class="sxs-lookup"><span data-stu-id="e20ad-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="e20ad-156">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="e20ad-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="e20ad-157">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="e20ad-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="e20ad-158">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="e20ad-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e20ad-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e20ad-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="e20ad-160">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="e20ad-160">The command contains a default list of templates.</span></span> <span data-ttu-id="e20ad-161">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="e20ad-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="e20ad-162">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="e20ad-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="e20ad-163">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="e20ad-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e20ad-164">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="e20ad-164">Template description</span></span>                          | <span data-ttu-id="e20ad-165">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="e20ad-165">Template name</span></span> | <span data-ttu-id="e20ad-166">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="e20ad-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="e20ad-167">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="e20ad-167">Console application</span></span>                          | `console`     | <span data-ttu-id="e20ad-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e20ad-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e20ad-169">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="e20ad-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="e20ad-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e20ad-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e20ad-171">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="e20ad-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="e20ad-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e20ad-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e20ad-173">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="e20ad-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="e20ad-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="e20ad-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="e20ad-175">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="e20ad-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="e20ad-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-176">[C#], F#</span></span>      |
| <span data-ttu-id="e20ad-177">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="e20ad-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="e20ad-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-178">[C#], F#</span></span>      |
| <span data-ttu-id="e20ad-179">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e20ad-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="e20ad-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-180">[C#]</span></span>          |
| <span data-ttu-id="e20ad-181">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="e20ad-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="e20ad-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-182">[C#]</span></span>          |
| <span data-ttu-id="e20ad-183">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="e20ad-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="e20ad-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-184">[C#]</span></span>          |
| <span data-ttu-id="e20ad-185">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="e20ad-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="e20ad-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-186">[C#]</span></span>          |
| <span data-ttu-id="e20ad-187">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e20ad-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="e20ad-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-188">[C#], F#</span></span>      |
| <span data-ttu-id="e20ad-189">File global.json</span><span class="sxs-lookup"><span data-stu-id="e20ad-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="e20ad-190">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="e20ad-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="e20ad-191">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="e20ad-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="e20ad-192">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="e20ad-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="e20ad-193">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="e20ad-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="e20ad-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="e20ad-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="e20ad-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="e20ad-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e20ad-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e20ad-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e20ad-197">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="e20ad-197">The command contains a default list of templates.</span></span> <span data-ttu-id="e20ad-198">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="e20ad-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="e20ad-199">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.x.</span><span class="sxs-lookup"><span data-stu-id="e20ad-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="e20ad-200">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="e20ad-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="e20ad-201">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="e20ad-201">Template description</span></span>  | <span data-ttu-id="e20ad-202">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="e20ad-202">Template name</span></span> | <span data-ttu-id="e20ad-203">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="e20ad-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="e20ad-204">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="e20ad-204">Console application</span></span>  | `console`     | <span data-ttu-id="e20ad-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-205">[C#], F#</span></span>  |
| <span data-ttu-id="e20ad-206">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="e20ad-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="e20ad-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-207">[C#], F#</span></span>  |
| <span data-ttu-id="e20ad-208">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="e20ad-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="e20ad-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-209">[C#], F#</span></span>  |
| <span data-ttu-id="e20ad-210">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="e20ad-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="e20ad-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-211">[C#], F#</span></span>  |
| <span data-ttu-id="e20ad-212">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="e20ad-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="e20ad-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-213">[C#]</span></span>      |
| <span data-ttu-id="e20ad-214">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e20ad-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="e20ad-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="e20ad-215">[C#], F#</span></span>  |
| <span data-ttu-id="e20ad-216">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="e20ad-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="e20ad-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="e20ad-217">[C#]</span></span>      |
| <span data-ttu-id="e20ad-218">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="e20ad-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="e20ad-219">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="e20ad-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="e20ad-220">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="e20ad-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="e20ad-221">Opzioni</span><span class="sxs-lookup"><span data-stu-id="e20ad-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e20ad-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e20ad-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="e20ad-223">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="e20ad-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e20ad-224">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e20ad-225">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="e20ad-225">Prints out help for the command.</span></span> <span data-ttu-id="e20ad-226">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="e20ad-227">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="e20ad-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e20ad-228">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e20ad-229">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="e20ad-230">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="e20ad-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="e20ad-231">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e20ad-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="e20ad-232">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="e20ad-233">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="e20ad-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e20ad-234">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="e20ad-235">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="e20ad-235">The language of the template to create.</span></span> <span data-ttu-id="e20ad-236">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="e20ad-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e20ad-237">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="e20ad-237">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e20ad-238">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-238">The name for the created output.</span></span> <span data-ttu-id="e20ad-239">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e20ad-239">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="e20ad-240">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="e20ad-240">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e20ad-241">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-241">Location to place the generated output.</span></span> <span data-ttu-id="e20ad-242">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e20ad-242">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="e20ad-243">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="e20ad-243">Filters templates based on available types.</span></span> <span data-ttu-id="e20ad-244">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="e20ad-244">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="e20ad-245">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="e20ad-245">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="e20ad-246">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="e20ad-246">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e20ad-247">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="e20ad-247">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="e20ad-248">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="e20ad-248">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e20ad-249">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e20ad-249">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="e20ad-250">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="e20ad-250">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="e20ad-251">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-251">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e20ad-252">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="e20ad-252">Prints out help for the command.</span></span> <span data-ttu-id="e20ad-253">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-253">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="e20ad-254">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="e20ad-254">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="e20ad-255">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-255">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="e20ad-256">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-256">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="e20ad-257">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="e20ad-257">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="e20ad-258">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e20ad-258">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="e20ad-259">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-259">Lists templates containing the specified name.</span></span> <span data-ttu-id="e20ad-260">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="e20ad-260">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e20ad-261">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-261">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="e20ad-262">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="e20ad-262">The language of the template to create.</span></span> <span data-ttu-id="e20ad-263">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="e20ad-263">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e20ad-264">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="e20ad-264">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e20ad-265">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-265">The name for the created output.</span></span> <span data-ttu-id="e20ad-266">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e20ad-266">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e20ad-267">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-267">Location to place the generated output.</span></span> <span data-ttu-id="e20ad-268">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e20ad-268">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="e20ad-269">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="e20ad-269">Filters templates based on available types.</span></span> <span data-ttu-id="e20ad-270">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="e20ad-270">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="e20ad-271">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="e20ad-271">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="e20ad-272">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="e20ad-272">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="e20ad-273">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="e20ad-273">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="e20ad-274">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="e20ad-274">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e20ad-275">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e20ad-275">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="e20ad-276">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-276">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="e20ad-277">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="e20ad-277">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="e20ad-278">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-278">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="e20ad-279">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="e20ad-279">Prints out help for the command.</span></span> <span data-ttu-id="e20ad-280">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-280">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="e20ad-281">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-281">Lists templates containing the specified name.</span></span> <span data-ttu-id="e20ad-282">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="e20ad-282">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="e20ad-283">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-283">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="e20ad-284">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="e20ad-284">The language of the template to create.</span></span> <span data-ttu-id="e20ad-285">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="e20ad-285">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="e20ad-286">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="e20ad-286">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="e20ad-287">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-287">The name for the created output.</span></span> <span data-ttu-id="e20ad-288">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e20ad-288">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="e20ad-289">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-289">Location to place the generated output.</span></span> <span data-ttu-id="e20ad-290">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="e20ad-290">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="e20ad-291">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="e20ad-291">Template options</span></span>

<span data-ttu-id="e20ad-292">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="e20ad-292">Each project template may have additional options available.</span></span> <span data-ttu-id="e20ad-293">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="e20ad-293">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="e20ad-294">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="e20ad-294">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="e20ad-295">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="e20ad-295">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="e20ad-296">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-296">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-297">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e20ad-297">**classlib**</span></span>

<span data-ttu-id="e20ad-298">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e20ad-298">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e20ad-299">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e20ad-299">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e20ad-300">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-300">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="e20ad-301">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-301">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-302">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="e20ad-302">**mstest, xunit**</span></span>

<span data-ttu-id="e20ad-303">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e20ad-303">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="e20ad-304">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-305">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="e20ad-305">**globaljson**</span></span>

<span data-ttu-id="e20ad-306">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e20ad-306">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="e20ad-307">**web**</span><span class="sxs-lookup"><span data-stu-id="e20ad-307">**web**</span></span>

<span data-ttu-id="e20ad-308">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-308">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e20ad-309">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-310">**webapi**</span><span class="sxs-lookup"><span data-stu-id="e20ad-310">**webapi**</span></span>

<span data-ttu-id="e20ad-311">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e20ad-311">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e20ad-312">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e20ad-312">The possible values are:</span></span>

- <span data-ttu-id="e20ad-313">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e20ad-313">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e20ad-314">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e20ad-314">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e20ad-315">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e20ad-315">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e20ad-316">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e20ad-316">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e20ad-317">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-317">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e20ad-318">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-318">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e20ad-319">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-319">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e20ad-320">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-320">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e20ad-321">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-321">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-322">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-322">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e20ad-323">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-323">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e20ad-324">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-324">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e20ad-325">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-325">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e20ad-326">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-326">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e20ad-327">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-327">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e20ad-328">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="e20ad-328">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e20ad-329">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-329">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e20ad-330">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-330">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e20ad-331">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-331">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e20ad-332">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-332">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e20ad-333">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-333">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e20ad-334">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="e20ad-334">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e20ad-335">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-335">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e20ad-336">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-336">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e20ad-337">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="e20ad-337">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e20ad-338">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-338">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-339">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-339">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-340">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="e20ad-340">**mvc, razor**</span></span>

<span data-ttu-id="e20ad-341">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e20ad-341">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e20ad-342">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e20ad-342">The possible values are:</span></span>

- <span data-ttu-id="e20ad-343">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e20ad-343">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e20ad-344">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="e20ad-344">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="e20ad-345">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e20ad-345">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e20ad-346">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e20ad-346">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e20ad-347">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="e20ad-347">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="e20ad-348">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e20ad-348">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e20ad-349">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-349">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e20ad-350">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-350">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e20ad-351">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-351">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e20ad-352">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-352">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e20ad-353">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-353">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-354">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-354">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="e20ad-355">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-355">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-356">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-356">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="e20ad-357">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-357">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-358">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-358">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e20ad-359">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-359">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e20ad-360">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-360">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e20ad-361">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-361">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e20ad-362">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-362">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e20ad-363">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-363">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e20ad-364">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="e20ad-364">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e20ad-365">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-365">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e20ad-366">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-366">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e20ad-367">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-367">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e20ad-368">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-368">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e20ad-369">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-369">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e20ad-370">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e20ad-370">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e20ad-371">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-371">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e20ad-372">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-372">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="e20ad-373">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="e20ad-373">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e20ad-374">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-374">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e20ad-375">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-375">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e20ad-376">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-376">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="e20ad-377">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="e20ad-377">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e20ad-378">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-378">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-379">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-379">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-380">**page**</span><span class="sxs-lookup"><span data-stu-id="e20ad-380">**page**</span></span>

<span data-ttu-id="e20ad-381">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-381">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e20ad-382">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-382">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e20ad-383">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="e20ad-383">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="e20ad-384">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="e20ad-384">**viewimports**</span></span>

<span data-ttu-id="e20ad-385">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-385">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e20ad-386">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-386">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="e20ad-387">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="e20ad-387">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="e20ad-388">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="e20ad-388">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="e20ad-389">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-389">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-390">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e20ad-390">**classlib**</span></span>

<span data-ttu-id="e20ad-391">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e20ad-391">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e20ad-392">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e20ad-392">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="e20ad-393">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-393">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="e20ad-394">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-395">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="e20ad-395">**mstest, xunit**</span></span>

<span data-ttu-id="e20ad-396">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="e20ad-396">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="e20ad-397">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-397">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-398">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="e20ad-398">**globaljson**</span></span>

<span data-ttu-id="e20ad-399">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="e20ad-399">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="e20ad-400">**web**</span><span class="sxs-lookup"><span data-stu-id="e20ad-400">**web**</span></span>

<span data-ttu-id="e20ad-401">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-401">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e20ad-402">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-402">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-403">**webapi**</span><span class="sxs-lookup"><span data-stu-id="e20ad-403">**webapi**</span></span>

<span data-ttu-id="e20ad-404">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e20ad-404">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e20ad-405">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e20ad-405">The possible values are:</span></span>

- <span data-ttu-id="e20ad-406">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e20ad-406">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e20ad-407">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e20ad-407">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e20ad-408">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e20ad-408">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e20ad-409">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e20ad-409">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e20ad-410">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-410">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e20ad-411">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-411">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e20ad-412">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-412">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e20ad-413">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-413">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e20ad-414">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-414">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-415">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-415">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e20ad-416">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-416">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e20ad-417">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-417">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e20ad-418">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-418">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e20ad-419">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-419">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="e20ad-420">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-420">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e20ad-421">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="e20ad-421">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e20ad-422">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-422">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e20ad-423">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-423">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e20ad-424">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-424">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e20ad-425">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-425">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e20ad-426">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-426">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e20ad-427">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="e20ad-427">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e20ad-428">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-428">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e20ad-429">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-429">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e20ad-430">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="e20ad-430">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e20ad-431">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-431">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-432">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-432">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-433">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="e20ad-433">**mvc, razor**</span></span>

<span data-ttu-id="e20ad-434">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e20ad-434">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="e20ad-435">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="e20ad-435">The possible values are:</span></span>

- <span data-ttu-id="e20ad-436">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="e20ad-436">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="e20ad-437">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="e20ad-437">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="e20ad-438">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="e20ad-438">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="e20ad-439">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="e20ad-439">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="e20ad-440">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="e20ad-440">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="e20ad-441">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="e20ad-441">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="e20ad-442">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-442">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="e20ad-443">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-443">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="e20ad-444">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-444">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="e20ad-445">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-445">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="e20ad-446">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-446">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-447">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-447">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="e20ad-448">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-448">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-449">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-449">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="e20ad-450">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-450">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-451">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-451">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="e20ad-452">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-452">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="e20ad-453">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-453">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="e20ad-454">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-454">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="e20ad-455">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-455">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="e20ad-456">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-456">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="e20ad-457">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="e20ad-457">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="e20ad-458">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-458">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e20ad-459">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-459">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="e20ad-460">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="e20ad-460">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="e20ad-461">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-461">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="e20ad-462">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-462">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="e20ad-463">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="e20ad-463">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="e20ad-464">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-464">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="e20ad-465">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-465">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="e20ad-466">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="e20ad-466">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="e20ad-467">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-467">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="e20ad-468">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-468">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="e20ad-469">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-469">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="e20ad-470">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="e20ad-470">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="e20ad-471">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-471">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="e20ad-472">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="e20ad-472">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="e20ad-473">**page**</span><span class="sxs-lookup"><span data-stu-id="e20ad-473">**page**</span></span>

<span data-ttu-id="e20ad-474">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-474">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e20ad-475">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-475">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="e20ad-476">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="e20ad-476">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="e20ad-477">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="e20ad-477">**viewimports**</span></span>

<span data-ttu-id="e20ad-478">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="e20ad-478">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="e20ad-479">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-479">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e20ad-480">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e20ad-480">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e20ad-481">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="e20ad-481">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="e20ad-482">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e20ad-482">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e20ad-483">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-483">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="e20ad-484">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-484">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="e20ad-485">**classlib**</span><span class="sxs-lookup"><span data-stu-id="e20ad-485">**classlib**</span></span>

<span data-ttu-id="e20ad-486">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e20ad-486">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e20ad-487">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-487">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="e20ad-488">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-488">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="e20ad-489">**mvc**</span><span class="sxs-lookup"><span data-stu-id="e20ad-489">**mvc**</span></span>

<span data-ttu-id="e20ad-490">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="e20ad-490">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="e20ad-491">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-491">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="e20ad-492">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-492">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="e20ad-493">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="e20ad-493">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="e20ad-494">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-494">Values: `None` or `Individual`.</span></span> <span data-ttu-id="e20ad-495">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-495">The default value is `None`.</span></span>

<span data-ttu-id="e20ad-496">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="e20ad-496">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="e20ad-497">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-497">Values: `true` or `false`.</span></span> <span data-ttu-id="e20ad-498">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="e20ad-498">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="e20ad-499">Esempi</span><span class="sxs-lookup"><span data-stu-id="e20ad-499">Examples</span></span>

<span data-ttu-id="e20ad-500">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="e20ad-500">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="e20ad-501">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="e20ad-501">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="e20ad-502">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione con destinazione a .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="e20ad-502">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="e20ad-503">Creare una nuova applicazione xUnit con destinazione .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="e20ad-503">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="e20ad-504">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="e20ad-504">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="e20ad-505">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="e20ad-505">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="e20ad-506">Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):</span><span class="sxs-lookup"><span data-stu-id="e20ad-506">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="e20ad-507">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e20ad-507">See also</span></span>

[<span data-ttu-id="e20ad-508">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e20ad-508">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="e20ad-509">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e20ad-509">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="e20ad-510">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="e20ad-510">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="e20ad-511">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e20ad-511">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)