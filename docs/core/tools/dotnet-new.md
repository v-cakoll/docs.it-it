---
title: Comando dotnet new - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
author: mairaw
ms.author: mairaw
ms.date: 07/31/2018
ms.openlocfilehash: 2c82dda2d93225edb360316637e22964135cd5e4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512555"
---
# <a name="dotnet-new"></a><span data-ttu-id="4acd3-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="4acd3-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4acd3-104">nome</span><span class="sxs-lookup"><span data-stu-id="4acd3-104">Name</span></span>

<span data-ttu-id="4acd3-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4acd3-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="4acd3-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4acd3-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4acd3-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4acd3-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4acd3-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4acd3-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4acd3-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="4acd3-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4acd3-110">Description</span></span>

<span data-ttu-id="4acd3-111">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="4acd3-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="4acd3-112">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="4acd3-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="4acd3-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="4acd3-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="4acd3-114">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="4acd3-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="4acd3-115">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="4acd3-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="4acd3-116">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="4acd3-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4acd3-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4acd3-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="4acd3-118">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="4acd3-118">The command contains a default list of templates.</span></span> <span data-ttu-id="4acd3-119">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="4acd3-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="4acd3-120">La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="4acd3-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="4acd3-121">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="4acd3-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4acd3-122">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="4acd3-122">Template description</span></span>                          | <span data-ttu-id="4acd3-123">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="4acd3-123">Template name</span></span>   | <span data-ttu-id="4acd3-124">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="4acd3-124">Languages</span></span>     |
|----------------------------------------------|-----------------|---------------|
| <span data-ttu-id="4acd3-125">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="4acd3-125">Console application</span></span>                          | `console`       | <span data-ttu-id="4acd3-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4acd3-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4acd3-127">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="4acd3-127">Class library</span></span>                                | `classlib`      | <span data-ttu-id="4acd3-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4acd3-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4acd3-129">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="4acd3-129">Unit test project</span></span>                            | `mstest`        | <span data-ttu-id="4acd3-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4acd3-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4acd3-131">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="4acd3-131">xUnit test project</span></span>                           | `xunit`         | <span data-ttu-id="4acd3-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4acd3-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4acd3-133">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="4acd3-133">Razor page</span></span>                                   | `page`          | <span data-ttu-id="4acd3-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-134">[C#]</span></span>          |
| <span data-ttu-id="4acd3-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="4acd3-135">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="4acd3-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-136">[C#]</span></span>          |
| <span data-ttu-id="4acd3-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="4acd3-137">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="4acd3-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-138">[C#]</span></span>          |
| <span data-ttu-id="4acd3-139">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="4acd3-139">ASP.NET Core empty</span></span>                           | `web`           | <span data-ttu-id="4acd3-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-140">[C#], F#</span></span>      |
| <span data-ttu-id="4acd3-141">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="4acd3-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="4acd3-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-142">[C#], F#</span></span>      |
| <span data-ttu-id="4acd3-143">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4acd3-143">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="4acd3-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-144">[C#]</span></span>          |
| <span data-ttu-id="4acd3-145">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="4acd3-145">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="4acd3-146">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-146">[C#]</span></span>          |
| <span data-ttu-id="4acd3-147">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="4acd3-147">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="4acd3-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-148">[C#]</span></span>          |
| <span data-ttu-id="4acd3-149">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="4acd3-149">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="4acd3-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-150">[C#]</span></span>          |
| <span data-ttu-id="4acd3-151">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4acd3-151">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="4acd3-152">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-152">[C#], F#</span></span>      |
| <span data-ttu-id="4acd3-153">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="4acd3-153">Razor class library</span></span>                          | `razorclasslib` | <span data-ttu-id="4acd3-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-154">[C#]</span></span>          |
| <span data-ttu-id="4acd3-155">File global.json</span><span class="sxs-lookup"><span data-stu-id="4acd3-155">global.json file</span></span>                             | `globaljson`    |               |
| <span data-ttu-id="4acd3-156">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="4acd3-156">NuGet config</span></span>                                 | `nugetconfig`   |               |
| <span data-ttu-id="4acd3-157">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="4acd3-157">Web config</span></span>                                   | `webconfig`     |               |
| <span data-ttu-id="4acd3-158">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="4acd3-158">Solution file</span></span>                                | `sln`           |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4acd3-159">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4acd3-159">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="4acd3-160">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="4acd3-160">The command contains a default list of templates.</span></span> <span data-ttu-id="4acd3-161">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="4acd3-161">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="4acd3-162">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="4acd3-162">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="4acd3-163">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="4acd3-163">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4acd3-164">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="4acd3-164">Template description</span></span>                          | <span data-ttu-id="4acd3-165">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="4acd3-165">Template name</span></span> | <span data-ttu-id="4acd3-166">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="4acd3-166">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="4acd3-167">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="4acd3-167">Console application</span></span>                          | `console`     | <span data-ttu-id="4acd3-168">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4acd3-168">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4acd3-169">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="4acd3-169">Class library</span></span>                                | `classlib`    | <span data-ttu-id="4acd3-170">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4acd3-170">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4acd3-171">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="4acd3-171">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="4acd3-172">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4acd3-172">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4acd3-173">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="4acd3-173">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="4acd3-174">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="4acd3-174">[C#], F#, VB</span></span>  |
| <span data-ttu-id="4acd3-175">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="4acd3-175">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="4acd3-176">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-176">[C#], F#</span></span>      |
| <span data-ttu-id="4acd3-177">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="4acd3-177">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="4acd3-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-178">[C#], F#</span></span>      |
| <span data-ttu-id="4acd3-179">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4acd3-179">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="4acd3-180">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-180">[C#]</span></span>          |
| <span data-ttu-id="4acd3-181">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="4acd3-181">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="4acd3-182">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-182">[C#]</span></span>          |
| <span data-ttu-id="4acd3-183">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="4acd3-183">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="4acd3-184">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-184">[C#]</span></span>          |
| <span data-ttu-id="4acd3-185">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="4acd3-185">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="4acd3-186">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-186">[C#]</span></span>          |
| <span data-ttu-id="4acd3-187">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4acd3-187">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="4acd3-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-188">[C#], F#</span></span>      |
| <span data-ttu-id="4acd3-189">File global.json</span><span class="sxs-lookup"><span data-stu-id="4acd3-189">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="4acd3-190">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="4acd3-190">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="4acd3-191">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="4acd3-191">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="4acd3-192">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="4acd3-192">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="4acd3-193">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="4acd3-193">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="4acd3-194">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="4acd3-194">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="4acd3-195">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="4acd3-195">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4acd3-196">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4acd3-196">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4acd3-197">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="4acd3-197">The command contains a default list of templates.</span></span> <span data-ttu-id="4acd3-198">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="4acd3-198">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="4acd3-199">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.x.</span><span class="sxs-lookup"><span data-stu-id="4acd3-199">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="4acd3-200">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="4acd3-200">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="4acd3-201">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="4acd3-201">Template description</span></span>  | <span data-ttu-id="4acd3-202">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="4acd3-202">Template name</span></span> | <span data-ttu-id="4acd3-203">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="4acd3-203">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="4acd3-204">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="4acd3-204">Console application</span></span>  | `console`     | <span data-ttu-id="4acd3-205">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-205">[C#], F#</span></span>  |
| <span data-ttu-id="4acd3-206">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="4acd3-206">Class library</span></span>        | `classlib`    | <span data-ttu-id="4acd3-207">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-207">[C#], F#</span></span>  |
| <span data-ttu-id="4acd3-208">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="4acd3-208">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="4acd3-209">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-209">[C#], F#</span></span>  |
| <span data-ttu-id="4acd3-210">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="4acd3-210">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="4acd3-211">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-211">[C#], F#</span></span>  |
| <span data-ttu-id="4acd3-212">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="4acd3-212">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="4acd3-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-213">[C#]</span></span>      |
| <span data-ttu-id="4acd3-214">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4acd3-214">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="4acd3-215">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="4acd3-215">[C#], F#</span></span>  |
| <span data-ttu-id="4acd3-216">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4acd3-216">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="4acd3-217">[C#]</span><span class="sxs-lookup"><span data-stu-id="4acd3-217">[C#]</span></span>      |
| <span data-ttu-id="4acd3-218">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="4acd3-218">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="4acd3-219">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="4acd3-219">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="4acd3-220">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="4acd3-220">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="4acd3-221">Opzioni</span><span class="sxs-lookup"><span data-stu-id="4acd3-221">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4acd3-222">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4acd3-222">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="4acd3-223">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="4acd3-223">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="4acd3-224">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-224">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4acd3-225">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4acd3-225">Prints out help for the command.</span></span> <span data-ttu-id="4acd3-226">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-226">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="4acd3-227">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="4acd3-227">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="4acd3-228">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-228">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="4acd3-229">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-229">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="4acd3-230">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="4acd3-230">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="4acd3-231">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4acd3-231">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="4acd3-232">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-232">Lists templates containing the specified name.</span></span> <span data-ttu-id="4acd3-233">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="4acd3-233">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4acd3-234">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-234">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="4acd3-235">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="4acd3-235">The language of the template to create.</span></span> <span data-ttu-id="4acd3-236">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="4acd3-236">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4acd3-237">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="4acd3-237">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4acd3-238">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="4acd3-238">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4acd3-239">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-239">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4acd3-240">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-240">The name for the created output.</span></span> <span data-ttu-id="4acd3-241">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4acd3-241">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="4acd3-242">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="4acd3-242">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4acd3-243">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-243">Location to place the generated output.</span></span> <span data-ttu-id="4acd3-244">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4acd3-244">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="4acd3-245">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="4acd3-245">Filters templates based on available types.</span></span> <span data-ttu-id="4acd3-246">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="4acd3-246">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="4acd3-247">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="4acd3-247">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="4acd3-248">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="4acd3-248">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="4acd3-249">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="4acd3-249">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="4acd3-250">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="4acd3-250">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4acd3-251">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4acd3-251">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="4acd3-252">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="4acd3-252">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="4acd3-253">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-253">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4acd3-254">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4acd3-254">Prints out help for the command.</span></span> <span data-ttu-id="4acd3-255">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-255">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="4acd3-256">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="4acd3-256">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="4acd3-257">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-257">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="4acd3-258">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-258">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="4acd3-259">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="4acd3-259">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="4acd3-260">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="4acd3-260">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="4acd3-261">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-261">Lists templates containing the specified name.</span></span> <span data-ttu-id="4acd3-262">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="4acd3-262">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4acd3-263">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-263">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="4acd3-264">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="4acd3-264">The language of the template to create.</span></span> <span data-ttu-id="4acd3-265">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="4acd3-265">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4acd3-266">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="4acd3-266">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4acd3-267">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="4acd3-267">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4acd3-268">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-268">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4acd3-269">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-269">The name for the created output.</span></span> <span data-ttu-id="4acd3-270">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4acd3-270">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4acd3-271">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-271">Location to place the generated output.</span></span> <span data-ttu-id="4acd3-272">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4acd3-272">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="4acd3-273">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="4acd3-273">Filters templates based on available types.</span></span> <span data-ttu-id="4acd3-274">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="4acd3-274">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="4acd3-275">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="4acd3-275">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="4acd3-276">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="4acd3-276">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="4acd3-277">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="4acd3-277">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="4acd3-278">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="4acd3-278">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4acd3-279">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4acd3-279">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="4acd3-280">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-280">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="4acd3-281">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="4acd3-281">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="4acd3-282">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-282">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="4acd3-283">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="4acd3-283">Prints out help for the command.</span></span> <span data-ttu-id="4acd3-284">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-284">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="4acd3-285">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-285">Lists templates containing the specified name.</span></span> <span data-ttu-id="4acd3-286">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="4acd3-286">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="4acd3-287">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-287">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="4acd3-288">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="4acd3-288">The language of the template to create.</span></span> <span data-ttu-id="4acd3-289">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="4acd3-289">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="4acd3-290">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="4acd3-290">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="4acd3-291">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="4acd3-291">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="4acd3-292">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-292">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="4acd3-293">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-293">The name for the created output.</span></span> <span data-ttu-id="4acd3-294">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4acd3-294">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="4acd3-295">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-295">Location to place the generated output.</span></span> <span data-ttu-id="4acd3-296">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="4acd3-296">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="4acd3-297">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="4acd3-297">Template options</span></span>

<span data-ttu-id="4acd3-298">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="4acd3-298">Each project template may have additional options available.</span></span> <span data-ttu-id="4acd3-299">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="4acd3-299">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="4acd3-300">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="4acd3-300">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="4acd3-301">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="4acd3-301">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="4acd3-302">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-302">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-303">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4acd3-303">**classlib**</span></span>

<span data-ttu-id="4acd3-304">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4acd3-304">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4acd3-305">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4acd3-305">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="4acd3-306">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-306">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="4acd3-307">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-307">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-308">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="4acd3-308">**mstest, xunit**</span></span>

<span data-ttu-id="4acd3-309">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4acd3-309">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="4acd3-310">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-310">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-311">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="4acd3-311">**globaljson**</span></span>

<span data-ttu-id="4acd3-312">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="4acd3-312">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="4acd3-313">**web**</span><span class="sxs-lookup"><span data-stu-id="4acd3-313">**web**</span></span>

<span data-ttu-id="4acd3-314">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-314">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4acd3-315">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-315">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-316">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4acd3-316">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4acd3-317">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="4acd3-317">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="4acd3-318">**webapi**</span><span class="sxs-lookup"><span data-stu-id="4acd3-318">**webapi**</span></span>

<span data-ttu-id="4acd3-319">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="4acd3-319">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4acd3-320">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="4acd3-320">The possible values are:</span></span>

- <span data-ttu-id="4acd3-321">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="4acd3-321">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4acd3-322">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4acd3-322">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4acd3-323">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="4acd3-323">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4acd3-324">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="4acd3-324">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4acd3-325">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-325">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4acd3-326">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-326">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4acd3-327">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-327">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4acd3-328">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-328">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4acd3-329">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-329">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-330">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-330">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4acd3-331">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-331">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4acd3-332">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-332">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4acd3-333">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-333">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4acd3-334">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-334">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="4acd3-335">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-335">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4acd3-336">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="4acd3-336">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4acd3-337">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-337">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4acd3-338">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-338">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4acd3-339">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-339">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4acd3-340">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-340">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4acd3-341">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-341">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4acd3-342">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="4acd3-342">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4acd3-343">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-343">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4acd3-344">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-344">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4acd3-345">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="4acd3-345">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4acd3-346">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-346">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-347">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-347">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-348">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4acd3-348">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4acd3-349">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-349">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="4acd3-350">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="4acd3-350">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="4acd3-351">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="4acd3-351">**mvc, razor**</span></span>

<span data-ttu-id="4acd3-352">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="4acd3-352">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4acd3-353">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="4acd3-353">The possible values are:</span></span>

- <span data-ttu-id="4acd3-354">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="4acd3-354">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4acd3-355">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="4acd3-355">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="4acd3-356">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4acd3-356">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4acd3-357">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="4acd3-357">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4acd3-358">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="4acd3-358">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="4acd3-359">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="4acd3-359">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4acd3-360">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-360">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4acd3-361">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-361">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4acd3-362">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-362">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4acd3-363">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-363">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4acd3-364">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-364">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-365">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-365">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="4acd3-366">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-366">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-367">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-367">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="4acd3-368">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-369">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-369">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4acd3-370">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-370">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="4acd3-371">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-371">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4acd3-372">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-372">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4acd3-373">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-373">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="4acd3-374">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-374">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4acd3-375">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="4acd3-375">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4acd3-376">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-376">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4acd3-377">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-377">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4acd3-378">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-378">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4acd3-379">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-379">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4acd3-380">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-380">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4acd3-381">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="4acd3-381">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="4acd3-382">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-382">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4acd3-383">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-383">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="4acd3-384">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="4acd3-384">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4acd3-385">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-385">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4acd3-386">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-386">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="4acd3-387">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-387">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="4acd3-388">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="4acd3-388">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4acd3-389">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-389">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-390">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-390">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-391">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="4acd3-391">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="4acd3-392">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-392">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="4acd3-393">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="4acd3-393">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="4acd3-394">**page**</span><span class="sxs-lookup"><span data-stu-id="4acd3-394">**page**</span></span>

<span data-ttu-id="4acd3-395">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-395">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4acd3-396">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-396">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="4acd3-397">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="4acd3-397">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="4acd3-398">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="4acd3-398">**viewimports**</span></span>

<span data-ttu-id="4acd3-399">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4acd3-400">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-400">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="4acd3-401">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="4acd3-401">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="4acd3-402">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="4acd3-402">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="4acd3-403">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-403">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-404">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4acd3-404">**classlib**</span></span>

<span data-ttu-id="4acd3-405">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4acd3-405">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4acd3-406">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4acd3-406">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="4acd3-407">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-407">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="4acd3-408">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-408">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-409">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="4acd3-409">**mstest, xunit**</span></span>

<span data-ttu-id="4acd3-410">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="4acd3-410">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="4acd3-411">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-411">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-412">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="4acd3-412">**globaljson**</span></span>

<span data-ttu-id="4acd3-413">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="4acd3-413">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="4acd3-414">**web**</span><span class="sxs-lookup"><span data-stu-id="4acd3-414">**web**</span></span>

<span data-ttu-id="4acd3-415">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-415">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4acd3-416">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-416">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-417">**webapi**</span><span class="sxs-lookup"><span data-stu-id="4acd3-417">**webapi**</span></span>

<span data-ttu-id="4acd3-418">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="4acd3-418">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4acd3-419">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="4acd3-419">The possible values are:</span></span>

- <span data-ttu-id="4acd3-420">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="4acd3-420">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4acd3-421">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4acd3-421">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4acd3-422">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="4acd3-422">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4acd3-423">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="4acd3-423">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4acd3-424">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-424">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4acd3-425">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-425">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4acd3-426">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-426">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4acd3-427">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-427">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4acd3-428">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-428">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-429">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-429">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4acd3-430">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-430">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4acd3-431">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-431">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4acd3-432">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-432">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4acd3-433">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-433">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="4acd3-434">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-434">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4acd3-435">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="4acd3-435">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4acd3-436">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-436">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4acd3-437">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-437">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4acd3-438">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-438">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4acd3-439">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-439">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4acd3-440">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-440">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4acd3-441">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="4acd3-441">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4acd3-442">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-442">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4acd3-443">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-443">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4acd3-444">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="4acd3-444">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4acd3-445">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-445">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-446">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-446">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-447">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="4acd3-447">**mvc, razor**</span></span>

<span data-ttu-id="4acd3-448">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="4acd3-448">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="4acd3-449">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="4acd3-449">The possible values are:</span></span>

- <span data-ttu-id="4acd3-450">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="4acd3-450">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="4acd3-451">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="4acd3-451">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="4acd3-452">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="4acd3-452">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="4acd3-453">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="4acd3-453">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="4acd3-454">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="4acd3-454">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="4acd3-455">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="4acd3-455">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="4acd3-456">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-456">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="4acd3-457">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-457">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="4acd3-458">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-458">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="4acd3-459">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-459">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="4acd3-460">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-460">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-461">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-461">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="4acd3-462">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-462">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-463">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-463">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="4acd3-464">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-465">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-465">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="4acd3-466">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-466">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="4acd3-467">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-467">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="4acd3-468">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-468">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="4acd3-469">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-469">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="4acd3-470">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-470">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="4acd3-471">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="4acd3-471">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="4acd3-472">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-472">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4acd3-473">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-473">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="4acd3-474">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="4acd3-474">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="4acd3-475">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-475">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="4acd3-476">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-476">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="4acd3-477">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="4acd3-477">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="4acd3-478">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-478">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="4acd3-479">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-479">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="4acd3-480">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="4acd3-480">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="4acd3-481">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-481">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="4acd3-482">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-482">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="4acd3-483">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-483">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="4acd3-484">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="4acd3-484">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="4acd3-485">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-485">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="4acd3-486">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="4acd3-486">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="4acd3-487">**page**</span><span class="sxs-lookup"><span data-stu-id="4acd3-487">**page**</span></span>

<span data-ttu-id="4acd3-488">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-488">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4acd3-489">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-489">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="4acd3-490">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="4acd3-490">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="4acd3-491">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="4acd3-491">**viewimports**</span></span>

<span data-ttu-id="4acd3-492">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="4acd3-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="4acd3-493">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-493">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4acd3-494">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4acd3-494">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4acd3-495">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="4acd3-495">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="4acd3-496">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4acd3-496">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4acd3-497">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-497">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="4acd3-498">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-498">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="4acd3-499">**classlib**</span><span class="sxs-lookup"><span data-stu-id="4acd3-499">**classlib**</span></span>

<span data-ttu-id="4acd3-500">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4acd3-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4acd3-501">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-501">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="4acd3-502">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-502">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="4acd3-503">**mvc**</span><span class="sxs-lookup"><span data-stu-id="4acd3-503">**mvc**</span></span>

<span data-ttu-id="4acd3-504">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4acd3-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="4acd3-505">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-505">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="4acd3-506">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-506">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="4acd3-507">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="4acd3-507">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="4acd3-508">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-508">Values: `None` or `Individual`.</span></span> <span data-ttu-id="4acd3-509">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-509">The default value is `None`.</span></span>

<span data-ttu-id="4acd3-510">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="4acd3-510">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="4acd3-511">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-511">Values: `true` or `false`.</span></span> <span data-ttu-id="4acd3-512">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="4acd3-512">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="4acd3-513">Esempi</span><span class="sxs-lookup"><span data-stu-id="4acd3-513">Examples</span></span>

<span data-ttu-id="4acd3-514">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="4acd3-514">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="4acd3-515">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="4acd3-515">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="4acd3-516">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="4acd3-516">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="4acd3-517">Creare una nuova applicazione xUnit:</span><span class="sxs-lookup"><span data-stu-id="4acd3-517">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="4acd3-518">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="4acd3-518">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="4acd3-519">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="4acd3-519">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="4acd3-520">Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):</span><span class="sxs-lookup"><span data-stu-id="4acd3-520">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="4acd3-521">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4acd3-521">See also</span></span>

* [<span data-ttu-id="4acd3-522">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="4acd3-522">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="4acd3-523">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="4acd3-523">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="4acd3-524">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="4acd3-524">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="4acd3-525">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="4acd3-525">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
