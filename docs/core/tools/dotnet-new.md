---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 10/24/2018
ms.openlocfilehash: 5177c920fee6fa946d2bf5d96644f26309ed0a99
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54516148"
---
# <a name="dotnet-new"></a><span data-ttu-id="5b711-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="5b711-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="5b711-104">nome</span><span class="sxs-lookup"><span data-stu-id="5b711-104">Name</span></span>

<span data-ttu-id="5b711-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="5b711-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5b711-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="5b711-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5b711-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5b711-107">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output]
    [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5b711-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5b711-108">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5b711-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5b711-109">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="5b711-110">Description</span><span class="sxs-lookup"><span data-stu-id="5b711-110">Description</span></span>

<span data-ttu-id="5b711-111">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="5b711-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="5b711-112">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="5b711-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="5b711-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="5b711-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="5b711-114">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="5b711-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="5b711-115">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="5b711-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="5b711-116">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="5b711-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5b711-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5b711-117">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="5b711-118">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="5b711-118">The command contains a default list of templates.</span></span> <span data-ttu-id="5b711-119">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="5b711-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="5b711-120">La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="5b711-120">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="5b711-121">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="5b711-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="5b711-122">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="5b711-122">Template description</span></span>                          | <span data-ttu-id="5b711-123">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="5b711-123">Template name</span></span>    | <span data-ttu-id="5b711-124">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="5b711-124">Languages</span></span>     |
|----------------------------------------------|------------------|---------------|
| <span data-ttu-id="5b711-125">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="5b711-125">Console application</span></span>                          | `console`        | <span data-ttu-id="5b711-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b711-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="5b711-127">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="5b711-127">Class library</span></span>                                | `classlib`       | <span data-ttu-id="5b711-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b711-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="5b711-129">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="5b711-129">Unit test project</span></span>                            | `mstest`         | <span data-ttu-id="5b711-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b711-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="5b711-131">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="5b711-131">xUnit test project</span></span>                           | `xunit`          | <span data-ttu-id="5b711-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b711-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="5b711-133">Progetto di NUnit test</span><span class="sxs-lookup"><span data-stu-id="5b711-133">NUnit test project</span></span>                           | `nunit`          | <span data-ttu-id="5b711-134">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b711-134">[C#], F#, VB</span></span>  |
| <span data-ttu-id="5b711-135">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="5b711-135">Razor page</span></span>                                   | `page`           | <span data-ttu-id="5b711-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-136">[C#]</span></span>          |
| <span data-ttu-id="5b711-137">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="5b711-137">MVC ViewImports</span></span>                              | `viewimports`    | <span data-ttu-id="5b711-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-138">[C#]</span></span>          |
| <span data-ttu-id="5b711-139">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="5b711-139">MVC ViewStart</span></span>                                | `viewstart`      | <span data-ttu-id="5b711-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-140">[C#]</span></span>          |
| <span data-ttu-id="5b711-141">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="5b711-141">ASP.NET Core empty</span></span>                           | `web`            | <span data-ttu-id="5b711-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-142">[C#], F#</span></span>      |
| <span data-ttu-id="5b711-143">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="5b711-143">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`            | <span data-ttu-id="5b711-144">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-144">[C#], F#</span></span>      |
| <span data-ttu-id="5b711-145">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5b711-145">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="5b711-146">`razor`, `webapp`</span><span class="sxs-lookup"><span data-stu-id="5b711-146">`razor`, `webapp`</span></span>| <span data-ttu-id="5b711-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-147">[C#]</span></span>          |
| <span data-ttu-id="5b711-148">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="5b711-148">ASP.NET Core with Angular</span></span>                    | `angular`        | <span data-ttu-id="5b711-149">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-149">[C#]</span></span>          |
| <span data-ttu-id="5b711-150">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="5b711-150">ASP.NET Core with React.js</span></span>                   | `react`          | <span data-ttu-id="5b711-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-151">[C#]</span></span>          |
| <span data-ttu-id="5b711-152">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="5b711-152">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`     | <span data-ttu-id="5b711-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-153">[C#]</span></span>          |
| <span data-ttu-id="5b711-154">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5b711-154">ASP.NET Core Web API</span></span>                         | `webapi`         | <span data-ttu-id="5b711-155">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-155">[C#], F#</span></span>      |
| <span data-ttu-id="5b711-156">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="5b711-156">Razor class library</span></span>                          | `razorclasslib`  | <span data-ttu-id="5b711-157">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-157">[C#]</span></span>          |
| <span data-ttu-id="5b711-158">File global.json</span><span class="sxs-lookup"><span data-stu-id="5b711-158">global.json file</span></span>                             | `globaljson`     |               |
| <span data-ttu-id="5b711-159">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="5b711-159">NuGet config</span></span>                                 | `nugetconfig`    |               |
| <span data-ttu-id="5b711-160">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="5b711-160">Web config</span></span>                                   | `webconfig`      |               |
| <span data-ttu-id="5b711-161">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="5b711-161">Solution file</span></span>                                | `sln`            |               |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5b711-162">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5b711-162">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="5b711-163">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="5b711-163">The command contains a default list of templates.</span></span> <span data-ttu-id="5b711-164">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="5b711-164">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="5b711-165">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.</span><span class="sxs-lookup"><span data-stu-id="5b711-165">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.</span></span> <span data-ttu-id="5b711-166">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="5b711-166">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="5b711-167">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="5b711-167">Template description</span></span>                          | <span data-ttu-id="5b711-168">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="5b711-168">Template name</span></span> | <span data-ttu-id="5b711-169">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="5b711-169">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="5b711-170">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="5b711-170">Console application</span></span>                          | `console`     | <span data-ttu-id="5b711-171">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b711-171">[C#], F#, VB</span></span>  |
| <span data-ttu-id="5b711-172">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="5b711-172">Class library</span></span>                                | `classlib`    | <span data-ttu-id="5b711-173">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b711-173">[C#], F#, VB</span></span>  |
| <span data-ttu-id="5b711-174">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="5b711-174">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="5b711-175">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b711-175">[C#], F#, VB</span></span>  |
| <span data-ttu-id="5b711-176">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="5b711-176">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="5b711-177">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="5b711-177">[C#], F#, VB</span></span>  |
| <span data-ttu-id="5b711-178">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="5b711-178">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="5b711-179">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-179">[C#], F#</span></span>      |
| <span data-ttu-id="5b711-180">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="5b711-180">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="5b711-181">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-181">[C#], F#</span></span>      |
| <span data-ttu-id="5b711-182">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5b711-182">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="5b711-183">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-183">[C#]</span></span>          |
| <span data-ttu-id="5b711-184">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="5b711-184">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="5b711-185">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-185">[C#]</span></span>          |
| <span data-ttu-id="5b711-186">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="5b711-186">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="5b711-187">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-187">[C#]</span></span>          |
| <span data-ttu-id="5b711-188">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="5b711-188">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="5b711-189">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-189">[C#]</span></span>          |
| <span data-ttu-id="5b711-190">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5b711-190">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="5b711-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-191">[C#], F#</span></span>      |
| <span data-ttu-id="5b711-192">File global.json</span><span class="sxs-lookup"><span data-stu-id="5b711-192">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="5b711-193">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="5b711-193">NuGet config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="5b711-194">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="5b711-194">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="5b711-195">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="5b711-195">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="5b711-196">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="5b711-196">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="5b711-197">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="5b711-197">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="5b711-198">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="5b711-198">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5b711-199">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5b711-199">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="5b711-200">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="5b711-200">The command contains a default list of templates.</span></span> <span data-ttu-id="5b711-201">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="5b711-201">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="5b711-202">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.x.</span><span class="sxs-lookup"><span data-stu-id="5b711-202">The following table shows the templates that come pre-installed with the .NET Core SDK 1.x.</span></span> <span data-ttu-id="5b711-203">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="5b711-203">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="5b711-204">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="5b711-204">Template description</span></span>  | <span data-ttu-id="5b711-205">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="5b711-205">Template name</span></span> | <span data-ttu-id="5b711-206">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="5b711-206">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="5b711-207">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="5b711-207">Console application</span></span>  | `console`     | <span data-ttu-id="5b711-208">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-208">[C#], F#</span></span>  |
| <span data-ttu-id="5b711-209">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="5b711-209">Class library</span></span>        | `classlib`    | <span data-ttu-id="5b711-210">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-210">[C#], F#</span></span>  |
| <span data-ttu-id="5b711-211">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="5b711-211">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="5b711-212">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-212">[C#], F#</span></span>  |
| <span data-ttu-id="5b711-213">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="5b711-213">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="5b711-214">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-214">[C#], F#</span></span>  |
| <span data-ttu-id="5b711-215">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="5b711-215">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="5b711-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-216">[C#]</span></span>      |
| <span data-ttu-id="5b711-217">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5b711-217">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="5b711-218">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="5b711-218">[C#], F#</span></span>  |
| <span data-ttu-id="5b711-219">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="5b711-219">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="5b711-220">[C#]</span><span class="sxs-lookup"><span data-stu-id="5b711-220">[C#]</span></span>      |
| <span data-ttu-id="5b711-221">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="5b711-221">NuGet config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="5b711-222">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="5b711-222">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="5b711-223">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="5b711-223">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="5b711-224">Opzioni</span><span class="sxs-lookup"><span data-stu-id="5b711-224">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5b711-225">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5b711-225">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="5b711-226">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="5b711-226">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="5b711-227">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-227">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="5b711-228">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="5b711-228">Prints out help for the command.</span></span> <span data-ttu-id="5b711-229">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="5b711-229">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="5b711-230">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="5b711-230">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="5b711-231">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="5b711-231">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="5b711-232">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-232">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="5b711-233">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="5b711-233">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="5b711-234">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5b711-234">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="5b711-235">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="5b711-235">Lists templates containing the specified name.</span></span> <span data-ttu-id="5b711-236">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="5b711-236">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="5b711-237">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-237">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="5b711-238">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="5b711-238">The language of the template to create.</span></span> <span data-ttu-id="5b711-239">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="5b711-239">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="5b711-240">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="5b711-240">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="5b711-241">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="5b711-241">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="5b711-242">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="5b711-242">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="5b711-243">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="5b711-243">The name for the created output.</span></span> <span data-ttu-id="5b711-244">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5b711-244">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="5b711-245">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="5b711-245">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5b711-246">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-246">Location to place the generated output.</span></span> <span data-ttu-id="5b711-247">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5b711-247">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="5b711-248">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="5b711-248">Filters templates based on available types.</span></span> <span data-ttu-id="5b711-249">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="5b711-249">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="5b711-250">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="5b711-250">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="5b711-251">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="5b711-251">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="5b711-252">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="5b711-252">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="5b711-253">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="5b711-253">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5b711-254">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5b711-254">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="5b711-255">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="5b711-255">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="5b711-256">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-256">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="5b711-257">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="5b711-257">Prints out help for the command.</span></span> <span data-ttu-id="5b711-258">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="5b711-258">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="5b711-259">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="5b711-259">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="5b711-260">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="5b711-260">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="5b711-261">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-261">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="5b711-262">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="5b711-262">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="5b711-263">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5b711-263">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="5b711-264">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="5b711-264">Lists templates containing the specified name.</span></span> <span data-ttu-id="5b711-265">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="5b711-265">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="5b711-266">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-266">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="5b711-267">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="5b711-267">The language of the template to create.</span></span> <span data-ttu-id="5b711-268">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="5b711-268">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="5b711-269">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="5b711-269">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="5b711-270">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="5b711-270">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="5b711-271">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="5b711-271">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="5b711-272">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="5b711-272">The name for the created output.</span></span> <span data-ttu-id="5b711-273">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5b711-273">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5b711-274">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-274">Location to place the generated output.</span></span> <span data-ttu-id="5b711-275">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5b711-275">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="5b711-276">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="5b711-276">Filters templates based on available types.</span></span> <span data-ttu-id="5b711-277">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="5b711-277">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="5b711-278">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="5b711-278">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="5b711-279">Per disinstallare un modello con un valore `PATH` di origine, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="5b711-279">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="5b711-280">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="5b711-280">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="5b711-281">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="5b711-281">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="5b711-282">Se non è possibile determinare l'argomento `PATH` o `NUGET_ID` necessario per disinstallare un modello, eseguendo `dotnet new --uninstall` senza un argomento, verranno elencati tutti i modelli installati e l'argomento necessario per disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="5b711-282">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5b711-283">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5b711-283">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="5b711-284">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="5b711-284">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="5b711-285">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="5b711-285">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="5b711-286">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-286">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="5b711-287">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="5b711-287">Prints out help for the command.</span></span> <span data-ttu-id="5b711-288">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="5b711-288">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="5b711-289">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="5b711-289">Lists templates containing the specified name.</span></span> <span data-ttu-id="5b711-290">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="5b711-290">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="5b711-291">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-291">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="5b711-292">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="5b711-292">The language of the template to create.</span></span> <span data-ttu-id="5b711-293">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="5b711-293">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="5b711-294">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="5b711-294">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="5b711-295">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="5b711-295">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="5b711-296">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="5b711-296">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="5b711-297">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="5b711-297">The name for the created output.</span></span> <span data-ttu-id="5b711-298">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5b711-298">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="5b711-299">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-299">Location to place the generated output.</span></span> <span data-ttu-id="5b711-300">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="5b711-300">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="5b711-301">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="5b711-301">Template options</span></span>

<span data-ttu-id="5b711-302">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="5b711-302">Each project template may have additional options available.</span></span> <span data-ttu-id="5b711-303">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b711-303">The core templates have the following additional options:</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="5b711-304">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5b711-304">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="5b711-305">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="5b711-305">**console, angular, react, reactredux, razorclasslib**</span></span>

  <span data-ttu-id="5b711-306">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-306">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-307">**classlib**</span><span class="sxs-lookup"><span data-stu-id="5b711-307">**classlib**</span></span>

<span data-ttu-id="5b711-308">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5b711-308">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b711-309">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="5b711-309">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="5b711-310">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="5b711-310">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="5b711-311">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-311">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-312">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="5b711-312">**mstest, xunit**</span></span>

<span data-ttu-id="5b711-313">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="5b711-313">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="5b711-314">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-314">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-315">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="5b711-315">**globaljson**</span></span>

<span data-ttu-id="5b711-316">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="5b711-316">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="5b711-317">**web**</span><span class="sxs-lookup"><span data-stu-id="5b711-317">**web**</span></span>

<span data-ttu-id="5b711-318">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-318">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="5b711-319">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-319">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-320">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b711-320">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="5b711-321">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="5b711-321">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="5b711-322">**webapi**</span><span class="sxs-lookup"><span data-stu-id="5b711-322">**webapi**</span></span>

<span data-ttu-id="5b711-323">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="5b711-323">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5b711-324">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="5b711-324">The possible values are:</span></span>

- <span data-ttu-id="5b711-325">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="5b711-325">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="5b711-326">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="5b711-326">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="5b711-327">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="5b711-327">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="5b711-328">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="5b711-328">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="5b711-329">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-329">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5b711-330">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-330">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b711-331">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="5b711-331">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="5b711-332">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-332">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5b711-333">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-333">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-334">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-334">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5b711-335">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-335">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5b711-336">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="5b711-336">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="5b711-337">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-337">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="5b711-338">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-338">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="5b711-339">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="5b711-339">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="5b711-340">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="5b711-340">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="5b711-341">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-341">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b711-342">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="5b711-342">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="5b711-343">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-343">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5b711-344">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-344">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5b711-345">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="5b711-345">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="5b711-346">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="5b711-346">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="5b711-347">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-347">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="5b711-348">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-348">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="5b711-349">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="5b711-349">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5b711-350">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-350">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-351">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-351">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-352">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b711-352">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="5b711-353">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="5b711-353">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="5b711-354">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="5b711-354">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="5b711-355">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="5b711-355">**mvc, razor**</span></span>

<span data-ttu-id="5b711-356">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="5b711-356">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5b711-357">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="5b711-357">The possible values are:</span></span>

- <span data-ttu-id="5b711-358">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="5b711-358">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="5b711-359">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="5b711-359">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="5b711-360">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="5b711-360">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="5b711-361">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="5b711-361">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="5b711-362">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="5b711-362">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="5b711-363">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="5b711-363">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="5b711-364">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-364">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5b711-365">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-365">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b711-366">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="5b711-366">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="5b711-367">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-367">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5b711-368">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-368">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-369">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-369">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="5b711-370">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-370">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-371">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-371">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="5b711-372">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-372">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-373">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-373">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5b711-374">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-374">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="5b711-375">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="5b711-375">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="5b711-376">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-376">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="5b711-377">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-377">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="5b711-378">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="5b711-378">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="5b711-379">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="5b711-379">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="5b711-380">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-380">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b711-381">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="5b711-381">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="5b711-382">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-382">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5b711-383">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-383">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5b711-384">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="5b711-384">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="5b711-385">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="5b711-385">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="5b711-386">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-386">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b711-387">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="5b711-387">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="5b711-388">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="5b711-388">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="5b711-389">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-389">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="5b711-390">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-390">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="5b711-391">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-391">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="5b711-392">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="5b711-392">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5b711-393">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-393">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-394">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-394">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-395">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5b711-395">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="5b711-396">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="5b711-396">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="5b711-397">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="5b711-397">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="5b711-398">**page**</span><span class="sxs-lookup"><span data-stu-id="5b711-398">**page**</span></span>

<span data-ttu-id="5b711-399">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-399">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="5b711-400">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="5b711-400">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="5b711-401">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="5b711-401">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="5b711-402">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="5b711-402">**viewimports**</span></span>

<span data-ttu-id="5b711-403">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-403">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="5b711-404">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="5b711-404">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="5b711-405">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="5b711-405">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="5b711-406">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="5b711-406">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="5b711-407">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-407">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-408">**classlib**</span><span class="sxs-lookup"><span data-stu-id="5b711-408">**classlib**</span></span>

<span data-ttu-id="5b711-409">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5b711-409">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b711-410">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="5b711-410">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="5b711-411">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="5b711-411">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="5b711-412">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-412">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-413">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="5b711-413">**mstest, xunit**</span></span>

<span data-ttu-id="5b711-414">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="5b711-414">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="5b711-415">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-415">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-416">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="5b711-416">**globaljson**</span></span>

<span data-ttu-id="5b711-417">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="5b711-417">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="5b711-418">**web**</span><span class="sxs-lookup"><span data-stu-id="5b711-418">**web**</span></span>

<span data-ttu-id="5b711-419">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-419">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="5b711-420">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-420">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-421">**webapi**</span><span class="sxs-lookup"><span data-stu-id="5b711-421">**webapi**</span></span>

<span data-ttu-id="5b711-422">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="5b711-422">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5b711-423">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="5b711-423">The possible values are:</span></span>

- <span data-ttu-id="5b711-424">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="5b711-424">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="5b711-425">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="5b711-425">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="5b711-426">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="5b711-426">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="5b711-427">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="5b711-427">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="5b711-428">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-428">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5b711-429">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-429">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b711-430">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="5b711-430">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="5b711-431">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-431">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5b711-432">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-432">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-433">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-433">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5b711-434">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-434">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5b711-435">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="5b711-435">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="5b711-436">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-436">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="5b711-437">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-437">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="5b711-438">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="5b711-438">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="5b711-439">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="5b711-439">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="5b711-440">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-440">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b711-441">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="5b711-441">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="5b711-442">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-442">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5b711-443">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-443">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5b711-444">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="5b711-444">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="5b711-445">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="5b711-445">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="5b711-446">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-446">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="5b711-447">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-447">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="5b711-448">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="5b711-448">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5b711-449">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-449">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-450">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-450">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-451">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="5b711-451">**mvc, razor**</span></span>

<span data-ttu-id="5b711-452">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="5b711-452">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="5b711-453">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="5b711-453">The possible values are:</span></span>

- <span data-ttu-id="5b711-454">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="5b711-454">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="5b711-455">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="5b711-455">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="5b711-456">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="5b711-456">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="5b711-457">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="5b711-457">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="5b711-458">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="5b711-458">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="5b711-459">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="5b711-459">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="5b711-460">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-460">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="5b711-461">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-461">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b711-462">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="5b711-462">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="5b711-463">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-463">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="5b711-464">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-464">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-465">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-465">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="5b711-466">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-466">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-467">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-467">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="5b711-468">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-468">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-469">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-469">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="5b711-470">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-470">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="5b711-471">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="5b711-471">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="5b711-472">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-472">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="5b711-473">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-473">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="5b711-474">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="5b711-474">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="5b711-475">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="5b711-475">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="5b711-476">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-476">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b711-477">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="5b711-477">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="5b711-478">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="5b711-478">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="5b711-479">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-479">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="5b711-480">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="5b711-480">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="5b711-481">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="5b711-481">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="5b711-482">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-482">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="5b711-483">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="5b711-483">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="5b711-484">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="5b711-484">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="5b711-485">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="5b711-485">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="5b711-486">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-486">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="5b711-487">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-487">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="5b711-488">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="5b711-488">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="5b711-489">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="5b711-489">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="5b711-490">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="5b711-490">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="5b711-491">**page**</span><span class="sxs-lookup"><span data-stu-id="5b711-491">**page**</span></span>

<span data-ttu-id="5b711-492">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-492">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="5b711-493">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="5b711-493">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="5b711-494">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="5b711-494">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="5b711-495">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="5b711-495">**viewimports**</span></span>

<span data-ttu-id="5b711-496">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="5b711-496">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="5b711-497">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="5b711-497">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="5b711-498">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="5b711-498">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="5b711-499">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="5b711-499">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="5b711-500">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5b711-500">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b711-501">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="5b711-501">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="5b711-502">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="5b711-502">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="5b711-503">**classlib**</span><span class="sxs-lookup"><span data-stu-id="5b711-503">**classlib**</span></span>

<span data-ttu-id="5b711-504">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5b711-504">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b711-505">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="5b711-505">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="5b711-506">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="5b711-506">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="5b711-507">**mvc**</span><span class="sxs-lookup"><span data-stu-id="5b711-507">**mvc**</span></span>

<span data-ttu-id="5b711-508">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5b711-508">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="5b711-509">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="5b711-509">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="5b711-510">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="5b711-510">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="5b711-511">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="5b711-511">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="5b711-512">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="5b711-512">Values: `None` or `Individual`.</span></span> <span data-ttu-id="5b711-513">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="5b711-513">The default value is `None`.</span></span>

<span data-ttu-id="5b711-514">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="5b711-514">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="5b711-515">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="5b711-515">Values: `true` or `false`.</span></span> <span data-ttu-id="5b711-516">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="5b711-516">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="5b711-517">Esempi</span><span class="sxs-lookup"><span data-stu-id="5b711-517">Examples</span></span>

<span data-ttu-id="5b711-518">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="5b711-518">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="5b711-519">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="5b711-519">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="5b711-520">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="5b711-520">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="5b711-521">Creare una nuova applicazione xUnit:</span><span class="sxs-lookup"><span data-stu-id="5b711-521">Create a new xUnit application:</span></span>

`dotnet new xunit`

<span data-ttu-id="5b711-522">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="5b711-522">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="5b711-523">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="5b711-523">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="5b711-524">Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):</span><span class="sxs-lookup"><span data-stu-id="5b711-524">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="5b711-525">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b711-525">See also</span></span>

- [<span data-ttu-id="5b711-526">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="5b711-526">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="5b711-527">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="5b711-527">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)
- [<span data-ttu-id="5b711-528">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="5b711-528">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="5b711-529">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="5b711-529">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
