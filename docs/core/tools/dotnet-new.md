---
title: Comando dotnet new - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
author: mairaw
ms.author: mairaw
ms.date: 10/24/2018
ms.openlocfilehash: 56d76f1dd54097f9cf20129d74057235290c273c
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188202"
---
# <a name="dotnet-new"></a><span data-ttu-id="24755-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="24755-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="24755-104">nome</span><span class="sxs-lookup"><span data-stu-id="24755-104">Name</span></span>

<span data-ttu-id="24755-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="24755-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="24755-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="24755-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="24755-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="24755-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="24755-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="24755-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="24755-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="24755-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="24755-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="24755-110">Description</span></span>

<span data-ttu-id="24755-111">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="24755-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="24755-112">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="24755-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="24755-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="24755-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="24755-114">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="24755-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="24755-115">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="24755-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="24755-116">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="24755-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="24755-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="24755-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="24755-118">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="24755-118">The command contains a default list of templates.</span></span> <span data-ttu-id="24755-119">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="24755-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="24755-120">La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="24755-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="24755-121">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="24755-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="24755-122">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="24755-122">Template description</span></span>                          | <span data-ttu-id="24755-123">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="24755-123">Template name</span></span>    | <span data-ttu-id="24755-124">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="24755-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="24755-125">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="24755-125">Console application</span></span>                          | `console`        | <span data-ttu-id="24755-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="24755-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="24755-127">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="24755-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="24755-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="24755-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="24755-129">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="24755-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="24755-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="24755-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="24755-131">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="24755-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="24755-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="24755-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="24755-133">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="24755-133">Razor page</span></span>                                   | `page`           | <span data-ttu-id="24755-134">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-134">[C#]</span></span>          |
| <span data-ttu-id="24755-135">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="24755-135">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="24755-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-136">[C#]</span></span>          |
| <span data-ttu-id="24755-137">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="24755-137">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="24755-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-138">[C#]</span></span>          |
| <span data-ttu-id="24755-139">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="24755-139">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="24755-140">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-140">[C#], F#</span></span>      |
| <span data-ttu-id="24755-141">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="24755-141">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="24755-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-142">[C#], F#</span></span>      |
| <span data-ttu-id="24755-143">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="24755-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="24755-144">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="24755-144">`razor`, `webapp`</span></span>| <span data-ttu-id="24755-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-145">[C#]</span></span>          |
| <span data-ttu-id="24755-146">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="24755-146">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="24755-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-147">[C#]</span></span>          |
| <span data-ttu-id="24755-148">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="24755-148">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="24755-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-149">[C#]</span></span>          |
| <span data-ttu-id="24755-150">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="24755-150">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="24755-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-151">[C#]</span></span>          |
| <span data-ttu-id="24755-152">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="24755-152">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="24755-153">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-153">[C#], F#</span></span>      |
| <span data-ttu-id="24755-154">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="24755-154">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="24755-155">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-155">[C#]</span></span>          |
| <span data-ttu-id="24755-156">File global.json</span><span class="sxs-lookup"><span data-stu-id="24755-156">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="24755-157">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="24755-157">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="24755-158">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="24755-158">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="24755-159">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="24755-159">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="24755-160">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="24755-160">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="24755-161">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="24755-161">The command contains a default list of templates.</span></span> <span data-ttu-id="24755-162">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="24755-162">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="24755-163">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="24755-163">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="24755-164">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="24755-164">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="24755-165">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="24755-165">Template description</span></span>                          | <span data-ttu-id="24755-166">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="24755-166">Template name</span></span> | <span data-ttu-id="24755-167">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="24755-167">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="24755-168">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="24755-168">Console application</span></span>                          | `console`     | <span data-ttu-id="24755-169">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="24755-169">[C#], F#, VB</span></span>  |
| <span data-ttu-id="24755-170">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="24755-170">Class library</span></span>                                | `classlib`    | <span data-ttu-id="24755-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="24755-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="24755-172">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="24755-172">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="24755-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="24755-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="24755-174">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="24755-174">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="24755-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="24755-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="24755-176">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="24755-176">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="24755-177">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-177">[C#], F#</span></span>      |
| <span data-ttu-id="24755-178">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="24755-178">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="24755-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-179">[C#], F#</span></span>      |
| <span data-ttu-id="24755-180">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="24755-180">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="24755-181">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-181">[C#]</span></span>          |
| <span data-ttu-id="24755-182">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="24755-182">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="24755-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-183">[C#]</span></span>          |
| <span data-ttu-id="24755-184">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="24755-184">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="24755-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-185">[C#]</span></span>          |
| <span data-ttu-id="24755-186">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="24755-186">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="24755-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-187">[C#]</span></span>          |
| <span data-ttu-id="24755-188">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="24755-188">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="24755-189">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-189">[C#], F#</span></span>      |
| <span data-ttu-id="24755-190">File global.json</span><span class="sxs-lookup"><span data-stu-id="24755-190">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="24755-191">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="24755-191">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="24755-192">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="24755-192">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="24755-193">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="24755-193">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="24755-194">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="24755-194">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="24755-195">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="24755-195">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="24755-196">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="24755-196">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="24755-197">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="24755-197">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="24755-198">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="24755-198">The command contains a default list of templates.</span></span> <span data-ttu-id="24755-199">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="24755-199">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="24755-200">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.x.</span><span class="sxs-lookup"><span data-stu-id="24755-200">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="24755-201">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="24755-201">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="24755-202">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="24755-202">Template description</span></span>  | <span data-ttu-id="24755-203">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="24755-203">Template name</span></span> | <span data-ttu-id="24755-204">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="24755-204">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="24755-205">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="24755-205">Console application</span></span>  | `console`     | <span data-ttu-id="24755-206">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-206">[C#], F#</span></span>  |
| <span data-ttu-id="24755-207">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="24755-207">Class library</span></span>        | `classlib`    | <span data-ttu-id="24755-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-208">[C#], F#</span></span>  |
| <span data-ttu-id="24755-209">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="24755-209">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="24755-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-210">[C#], F#</span></span>  |
| <span data-ttu-id="24755-211">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="24755-211">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="24755-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-212">[C#], F#</span></span>  |
| <span data-ttu-id="24755-213">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="24755-213">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="24755-214">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-214">[C#]</span></span>      |
| <span data-ttu-id="24755-215">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="24755-215">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="24755-216">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="24755-216">[C#], F#</span></span>  |
| <span data-ttu-id="24755-217">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="24755-217">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="24755-218">[C#]</span><span class="sxs-lookup"><span data-stu-id="24755-218">[C#]</span></span>      |
| <span data-ttu-id="24755-219">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="24755-219">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="24755-220">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="24755-220">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="24755-221">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="24755-221">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="24755-222">Opzioni</span><span class="sxs-lookup"><span data-stu-id="24755-222">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="24755-223">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="24755-223">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="24755-224">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="24755-224">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="24755-225">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-225">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="24755-226">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="24755-226">Prints out help for the command.</span></span> <span data-ttu-id="24755-227">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="24755-227">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="24755-228">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="24755-228">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="24755-229">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="24755-229">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="24755-230">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="24755-230">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="24755-231">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="24755-231">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="24755-232">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="24755-232">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="24755-233">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="24755-233">Lists templates containing the specified name.</span></span> <span data-ttu-id="24755-234">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="24755-234">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="24755-235">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-235">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="24755-236">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="24755-236">The language of the template to create.</span></span> <span data-ttu-id="24755-237">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="24755-237">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="24755-238">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="24755-238">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="24755-239">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="24755-239">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="24755-240">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="24755-240">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="24755-241">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="24755-241">The name for the created output.</span></span> <span data-ttu-id="24755-242">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="24755-242">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="24755-243">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="24755-243">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="24755-244">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="24755-244">Location to place the generated output.</span></span> <span data-ttu-id="24755-245">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="24755-245">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="24755-246">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="24755-246">Filters templates based on available types.</span></span> <span data-ttu-id="24755-247">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="24755-247">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="24755-248">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="24755-248">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="24755-249">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="24755-249">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="24755-250">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="24755-250">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="24755-251">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="24755-251">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="24755-252">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="24755-252">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="24755-253">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="24755-253">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="24755-254">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-254">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="24755-255">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="24755-255">Prints out help for the command.</span></span> <span data-ttu-id="24755-256">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="24755-256">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="24755-257">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="24755-257">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="24755-258">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="24755-258">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="24755-259">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="24755-259">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="24755-260">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="24755-260">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="24755-261">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="24755-261">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="24755-262">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="24755-262">Lists templates containing the specified name.</span></span> <span data-ttu-id="24755-263">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="24755-263">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="24755-264">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-264">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="24755-265">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="24755-265">The language of the template to create.</span></span> <span data-ttu-id="24755-266">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="24755-266">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="24755-267">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="24755-267">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="24755-268">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="24755-268">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="24755-269">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="24755-269">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="24755-270">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="24755-270">The name for the created output.</span></span> <span data-ttu-id="24755-271">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="24755-271">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="24755-272">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="24755-272">Location to place the generated output.</span></span> <span data-ttu-id="24755-273">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="24755-273">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="24755-274">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="24755-274">Filters templates based on available types.</span></span> <span data-ttu-id="24755-275">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="24755-275">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="24755-276">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="24755-276">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="24755-277">Per disinstallare un modello con un valore `PATH` di origine, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="24755-277">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="24755-278">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="24755-278">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="24755-279">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="24755-279">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="24755-280">Se non è possibile determinare l'argomento `PATH` o `NUGET_ID` necessario per disinstallare un modello, eseguendo `dotnet new --uninstall` senza un argomento, verranno elencati tutti i modelli installati e l'argomento necessario per disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="24755-280">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="24755-281">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="24755-281">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="24755-282">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="24755-282">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="24755-283">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="24755-283">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="24755-284">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-284">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="24755-285">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="24755-285">Prints out help for the command.</span></span> <span data-ttu-id="24755-286">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="24755-286">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="24755-287">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="24755-287">Lists templates containing the specified name.</span></span> <span data-ttu-id="24755-288">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="24755-288">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="24755-289">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-289">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="24755-290">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="24755-290">The language of the template to create.</span></span> <span data-ttu-id="24755-291">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="24755-291">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="24755-292">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="24755-292">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="24755-293">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="24755-293">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="24755-294">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="24755-294">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="24755-295">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="24755-295">The name for the created output.</span></span> <span data-ttu-id="24755-296">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="24755-296">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="24755-297">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="24755-297">Location to place the generated output.</span></span> <span data-ttu-id="24755-298">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="24755-298">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="24755-299">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="24755-299">Template options</span></span>

<span data-ttu-id="24755-300">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="24755-300">Each project template may have additional options available.</span></span> <span data-ttu-id="24755-301">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="24755-301">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="24755-302">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="24755-302">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="24755-303">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="24755-303">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="24755-304">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-304">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-305">**classlib**</span><span class="sxs-lookup"><span data-stu-id="24755-305">**classlib**</span></span>

<span data-ttu-id="24755-306">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="24755-306">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="24755-307">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="24755-307">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="24755-308">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="24755-308">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="24755-309">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-309">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-310">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="24755-310">**mstest, xunit**</span></span>

<span data-ttu-id="24755-311">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="24755-311">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="24755-312">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-312">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-313">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="24755-313">**globaljson**</span></span>

<span data-ttu-id="24755-314">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="24755-314">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="24755-315">**web**</span><span class="sxs-lookup"><span data-stu-id="24755-315">**web**</span></span>

<span data-ttu-id="24755-316">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="24755-316">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="24755-317">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-317">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-318">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="24755-318">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="24755-319">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="24755-319">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="24755-320">**webapi**</span><span class="sxs-lookup"><span data-stu-id="24755-320">**webapi**</span></span>

<span data-ttu-id="24755-321">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="24755-321">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="24755-322">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="24755-322">The possible values are:</span></span>

- <span data-ttu-id="24755-323">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="24755-323">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="24755-324">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="24755-324">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="24755-325">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="24755-325">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="24755-326">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="24755-326">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="24755-327">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-327">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="24755-328">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-328">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="24755-329">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="24755-329">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="24755-330">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-330">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="24755-331">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-331">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-332">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-332">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="24755-333">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-333">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="24755-334">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="24755-334">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="24755-335">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-335">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="24755-336">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-336">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="24755-337">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="24755-337">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="24755-338">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="24755-338">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="24755-339">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-339">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="24755-340">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="24755-340">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="24755-341">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-341">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="24755-342">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-342">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="24755-343">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="24755-343">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="24755-344">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="24755-344">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="24755-345">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-345">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="24755-346">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="24755-346">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="24755-347">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="24755-347">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="24755-348">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-348">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-349">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-349">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-350">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="24755-350">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="24755-351">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="24755-351">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="24755-352">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="24755-352">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="24755-353">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="24755-353">**mvc, razor**</span></span>

<span data-ttu-id="24755-354">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="24755-354">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="24755-355">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="24755-355">The possible values are:</span></span>

- <span data-ttu-id="24755-356">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="24755-356">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="24755-357">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="24755-357">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="24755-358">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="24755-358">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="24755-359">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="24755-359">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="24755-360">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="24755-360">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="24755-361">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="24755-361">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="24755-362">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-362">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="24755-363">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-363">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="24755-364">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="24755-364">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="24755-365">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-365">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="24755-366">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-366">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-367">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-367">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="24755-368">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-369">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-369">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="24755-370">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-371">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-371">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="24755-372">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-372">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="24755-373">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="24755-373">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="24755-374">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-374">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="24755-375">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-375">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="24755-376">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="24755-376">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="24755-377">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="24755-377">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="24755-378">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-378">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="24755-379">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="24755-379">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="24755-380">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-380">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="24755-381">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-381">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="24755-382">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="24755-382">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="24755-383">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="24755-383">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="24755-384">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-384">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="24755-385">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="24755-385">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="24755-386">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="24755-386">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="24755-387">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-387">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="24755-388">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="24755-388">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="24755-389">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-389">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="24755-390">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="24755-390">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="24755-391">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-391">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-392">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-392">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-393">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="24755-393">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="24755-394">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="24755-394">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="24755-395">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="24755-395">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="24755-396">**page**</span><span class="sxs-lookup"><span data-stu-id="24755-396">**page**</span></span>

<span data-ttu-id="24755-397">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="24755-397">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="24755-398">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="24755-398">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="24755-399">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="24755-399">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="24755-400">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="24755-400">**viewimports**</span></span>

<span data-ttu-id="24755-401">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="24755-401">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="24755-402">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="24755-402">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="24755-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="24755-403">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="24755-404">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="24755-404">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="24755-405">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-405">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-406">**classlib**</span><span class="sxs-lookup"><span data-stu-id="24755-406">**classlib**</span></span>

<span data-ttu-id="24755-407">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="24755-407">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="24755-408">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="24755-408">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="24755-409">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="24755-409">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="24755-410">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-410">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-411">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="24755-411">**mstest, xunit**</span></span>

<span data-ttu-id="24755-412">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="24755-412">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="24755-413">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-413">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-414">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="24755-414">**globaljson**</span></span>

<span data-ttu-id="24755-415">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="24755-415">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="24755-416">**web**</span><span class="sxs-lookup"><span data-stu-id="24755-416">**web**</span></span>

<span data-ttu-id="24755-417">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="24755-417">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="24755-418">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-418">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-419">**webapi**</span><span class="sxs-lookup"><span data-stu-id="24755-419">**webapi**</span></span>

<span data-ttu-id="24755-420">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="24755-420">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="24755-421">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="24755-421">The possible values are:</span></span>

- <span data-ttu-id="24755-422">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="24755-422">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="24755-423">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="24755-423">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="24755-424">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="24755-424">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="24755-425">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="24755-425">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="24755-426">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-426">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="24755-427">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-427">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="24755-428">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="24755-428">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="24755-429">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-429">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="24755-430">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-430">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-431">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-431">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="24755-432">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-432">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="24755-433">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="24755-433">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="24755-434">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-434">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="24755-435">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-435">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="24755-436">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="24755-436">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="24755-437">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="24755-437">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="24755-438">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-438">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="24755-439">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="24755-439">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="24755-440">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-440">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="24755-441">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-441">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="24755-442">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="24755-442">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="24755-443">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="24755-443">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="24755-444">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-444">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="24755-445">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="24755-445">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="24755-446">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="24755-446">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="24755-447">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-447">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-448">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-448">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-449">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="24755-449">**mvc, razor**</span></span>

<span data-ttu-id="24755-450">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="24755-450">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="24755-451">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="24755-451">The possible values are:</span></span>

- <span data-ttu-id="24755-452">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="24755-452">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="24755-453">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="24755-453">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="24755-454">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="24755-454">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="24755-455">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="24755-455">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="24755-456">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="24755-456">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="24755-457">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="24755-457">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="24755-458">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-458">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="24755-459">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-459">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="24755-460">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="24755-460">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="24755-461">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-461">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="24755-462">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-462">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-463">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-463">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="24755-464">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-465">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-465">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="24755-466">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-467">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-467">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="24755-468">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-468">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="24755-469">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="24755-469">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="24755-470">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-470">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="24755-471">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-471">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="24755-472">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="24755-472">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="24755-473">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="24755-473">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="24755-474">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-474">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="24755-475">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="24755-475">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="24755-476">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="24755-476">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="24755-477">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-477">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="24755-478">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="24755-478">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="24755-479">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="24755-479">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="24755-480">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-480">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="24755-481">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="24755-481">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="24755-482">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="24755-482">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="24755-483">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="24755-483">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="24755-484">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="24755-484">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="24755-485">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-485">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="24755-486">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="24755-486">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="24755-487">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="24755-487">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="24755-488">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="24755-488">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="24755-489">**page**</span><span class="sxs-lookup"><span data-stu-id="24755-489">**page**</span></span>

<span data-ttu-id="24755-490">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="24755-490">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="24755-491">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="24755-491">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="24755-492">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="24755-492">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="24755-493">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="24755-493">**viewimports**</span></span>

<span data-ttu-id="24755-494">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="24755-494">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="24755-495">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="24755-495">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="24755-496">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="24755-496">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="24755-497">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="24755-497">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="24755-498">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="24755-498">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="24755-499">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="24755-499">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="24755-500">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="24755-500">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="24755-501">**classlib**</span><span class="sxs-lookup"><span data-stu-id="24755-501">**classlib**</span></span>

<span data-ttu-id="24755-502">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="24755-502">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="24755-503">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="24755-503">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="24755-504">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="24755-504">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="24755-505">**mvc**</span><span class="sxs-lookup"><span data-stu-id="24755-505">**mvc**</span></span>

<span data-ttu-id="24755-506">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="24755-506">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="24755-507">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="24755-507">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="24755-508">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="24755-508">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="24755-509">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="24755-509">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="24755-510">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="24755-510">Values: `None` or `Individual`.</span></span> <span data-ttu-id="24755-511">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="24755-511">The default value is `None`.</span></span>

<span data-ttu-id="24755-512">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="24755-512">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="24755-513">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="24755-513">Values: `true` or `false`.</span></span> <span data-ttu-id="24755-514">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="24755-514">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="24755-515">Esempi</span><span class="sxs-lookup"><span data-stu-id="24755-515">Examples</span></span>

<span data-ttu-id="24755-516">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="24755-516">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="24755-517">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="24755-517">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="24755-518">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="24755-518">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="24755-519">Creare una nuova applicazione xUnit:</span><span class="sxs-lookup"><span data-stu-id="24755-519">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="24755-520">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="24755-520">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="24755-521">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="24755-521">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="24755-522">Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):</span><span class="sxs-lookup"><span data-stu-id="24755-522">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="24755-523">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24755-523">See also</span></span>

* [<span data-ttu-id="24755-524">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="24755-524">Custom templates for dotnet new</span></span>](custom-templates.md)  
* [<span data-ttu-id="24755-525">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="24755-525">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
* [<span data-ttu-id="24755-526">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="24755-526">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="24755-527">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="24755-527">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
