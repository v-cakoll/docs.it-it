---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 05/06/2019
ms.openlocfilehash: 57b198d13984fb4585e1df6303afe481e7e0552d
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969743"
---
# <a name="dotnet-new"></a><span data-ttu-id="72ad8-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="72ad8-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="72ad8-104">Name</span><span class="sxs-lookup"><span data-stu-id="72ad8-104">Name</span></span>

<span data-ttu-id="72ad8-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="72ad8-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="72ad8-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="72ad8-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="72ad8-107">.NET Core 2.2</span></span>](#tab/netcore22)

```console
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="72ad8-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="72ad8-108">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="72ad8-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72ad8-109">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="72ad8-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="72ad8-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="72ad8-111">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="72ad8-111">Description</span></span>

<span data-ttu-id="72ad8-112">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="72ad8-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="72ad8-113">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="72ad8-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="72ad8-114">Argomenti</span><span class="sxs-lookup"><span data-stu-id="72ad8-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="72ad8-115">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="72ad8-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="72ad8-116">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="72ad8-117">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="72ad8-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="72ad8-118">Se il valore di `TEMPLATE` non è una corrispondenza esatta del testo nella colonna **Modelli** o **Nome breve** viene eseguita una corrispondenza sottostringa in queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="72ad8-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="72ad8-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="72ad8-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="72ad8-120">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="72ad8-120">The command contains a default list of templates.</span></span> <span data-ttu-id="72ad8-121">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="72ad8-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="72ad8-122">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.2.100.</span><span class="sxs-lookup"><span data-stu-id="72ad8-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="72ad8-123">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="72ad8-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="72ad8-124">Modelli</span><span class="sxs-lookup"><span data-stu-id="72ad8-124">Templates</span></span>                                    | <span data-ttu-id="72ad8-125">Nome breve</span><span class="sxs-lookup"><span data-stu-id="72ad8-125">Short Name</span></span>        | <span data-ttu-id="72ad8-126">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="72ad8-126">Language</span></span>     | <span data-ttu-id="72ad8-127">Tag</span><span class="sxs-lookup"><span data-stu-id="72ad8-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="72ad8-128">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="72ad8-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="72ad8-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-129">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-130">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="72ad8-130">Common/Console</span></span>                        |
| <span data-ttu-id="72ad8-131">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="72ad8-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="72ad8-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-132">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-133">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="72ad8-133">Common/Library</span></span>                        |
| <span data-ttu-id="72ad8-134">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="72ad8-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="72ad8-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-135">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-136">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="72ad8-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="72ad8-137">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="72ad8-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="72ad8-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-138">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-139">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="72ad8-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="72ad8-140">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="72ad8-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="72ad8-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-141">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-142">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="72ad8-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="72ad8-143">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="72ad8-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="72ad8-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-144">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-145">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="72ad8-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="72ad8-146">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="72ad8-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="72ad8-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-147">[C#]</span></span>         | <span data-ttu-id="72ad8-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72ad8-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72ad8-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="72ad8-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="72ad8-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-150">[C#]</span></span>         | <span data-ttu-id="72ad8-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72ad8-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72ad8-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="72ad8-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="72ad8-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-153">[C#]</span></span>         | <span data-ttu-id="72ad8-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72ad8-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72ad8-155">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="72ad8-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="72ad8-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-156">[C#], F#</span></span>     | <span data-ttu-id="72ad8-157">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="72ad8-157">Web/Empty</span></span>                             |
| <span data-ttu-id="72ad8-158">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="72ad8-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="72ad8-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-159">[C#], F#</span></span>     | <span data-ttu-id="72ad8-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="72ad8-160">Web/MVC</span></span>                               |
| <span data-ttu-id="72ad8-161">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72ad8-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="72ad8-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="72ad8-162">`webapp`, `razor`</span></span> | <span data-ttu-id="72ad8-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-163">[C#]</span></span>         | <span data-ttu-id="72ad8-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="72ad8-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="72ad8-165">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="72ad8-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="72ad8-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-166">[C#]</span></span>         | <span data-ttu-id="72ad8-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72ad8-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="72ad8-168">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="72ad8-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="72ad8-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-169">[C#]</span></span>         | <span data-ttu-id="72ad8-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72ad8-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="72ad8-171">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="72ad8-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="72ad8-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-172">[C#]</span></span>         | <span data-ttu-id="72ad8-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72ad8-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="72ad8-174">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="72ad8-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="72ad8-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-175">[C#]</span></span>         | <span data-ttu-id="72ad8-176">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="72ad8-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="72ad8-177">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72ad8-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="72ad8-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-178">[C#], F#</span></span>     | <span data-ttu-id="72ad8-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="72ad8-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="72ad8-180">File global.json</span><span class="sxs-lookup"><span data-stu-id="72ad8-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="72ad8-181">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-181">Config</span></span>                                |
| <span data-ttu-id="72ad8-182">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="72ad8-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="72ad8-183">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-183">Config</span></span>                                |
| <span data-ttu-id="72ad8-184">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="72ad8-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="72ad8-185">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-185">Config</span></span>                                |
| <span data-ttu-id="72ad8-186">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="72ad8-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="72ad8-187">Soluzione</span><span class="sxs-lookup"><span data-stu-id="72ad8-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="72ad8-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="72ad8-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="72ad8-189">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="72ad8-189">The command contains a default list of templates.</span></span> <span data-ttu-id="72ad8-190">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="72ad8-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="72ad8-191">La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="72ad8-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="72ad8-192">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="72ad8-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="72ad8-193">Modelli</span><span class="sxs-lookup"><span data-stu-id="72ad8-193">Templates</span></span>                                    | <span data-ttu-id="72ad8-194">Nome breve</span><span class="sxs-lookup"><span data-stu-id="72ad8-194">Short Name</span></span>      | <span data-ttu-id="72ad8-195">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="72ad8-195">Language</span></span>     | <span data-ttu-id="72ad8-196">Tag</span><span class="sxs-lookup"><span data-stu-id="72ad8-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="72ad8-197">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="72ad8-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="72ad8-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-198">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-199">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="72ad8-199">Common/Console</span></span>                        |
| <span data-ttu-id="72ad8-200">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="72ad8-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="72ad8-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-201">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-202">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="72ad8-202">Common/Library</span></span>                        |
| <span data-ttu-id="72ad8-203">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="72ad8-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="72ad8-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-204">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-205">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="72ad8-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="72ad8-206">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="72ad8-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="72ad8-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-207">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-208">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="72ad8-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="72ad8-209">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="72ad8-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="72ad8-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-210">[C#]</span></span>         | <span data-ttu-id="72ad8-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72ad8-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72ad8-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="72ad8-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="72ad8-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-213">[C#]</span></span>         | <span data-ttu-id="72ad8-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72ad8-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72ad8-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="72ad8-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="72ad8-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-216">[C#]</span></span>         | <span data-ttu-id="72ad8-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72ad8-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="72ad8-218">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="72ad8-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="72ad8-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-219">[C#], F#</span></span>     | <span data-ttu-id="72ad8-220">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="72ad8-220">Web/Empty</span></span>                             |
| <span data-ttu-id="72ad8-221">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="72ad8-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="72ad8-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-222">[C#], F#</span></span>     | <span data-ttu-id="72ad8-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="72ad8-223">Web/MVC</span></span>                               |
| <span data-ttu-id="72ad8-224">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72ad8-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="72ad8-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-225">[C#]</span></span>         | <span data-ttu-id="72ad8-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="72ad8-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="72ad8-227">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="72ad8-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="72ad8-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-228">[C#]</span></span>         | <span data-ttu-id="72ad8-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72ad8-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="72ad8-230">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="72ad8-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="72ad8-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-231">[C#]</span></span>         | <span data-ttu-id="72ad8-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72ad8-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="72ad8-233">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="72ad8-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="72ad8-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-234">[C#]</span></span>         | <span data-ttu-id="72ad8-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72ad8-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="72ad8-236">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="72ad8-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="72ad8-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-237">[C#]</span></span>         | <span data-ttu-id="72ad8-238">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="72ad8-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="72ad8-239">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72ad8-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="72ad8-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-240">[C#], F#</span></span>     | <span data-ttu-id="72ad8-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="72ad8-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="72ad8-242">File global.json</span><span class="sxs-lookup"><span data-stu-id="72ad8-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="72ad8-243">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-243">Config</span></span>                                |
| <span data-ttu-id="72ad8-244">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="72ad8-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="72ad8-245">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-245">Config</span></span>                                |
| <span data-ttu-id="72ad8-246">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="72ad8-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="72ad8-247">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-247">Config</span></span>                                |
| <span data-ttu-id="72ad8-248">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="72ad8-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="72ad8-249">Soluzione</span><span class="sxs-lookup"><span data-stu-id="72ad8-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="72ad8-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72ad8-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="72ad8-251">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="72ad8-251">The command contains a default list of templates.</span></span> <span data-ttu-id="72ad8-252">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="72ad8-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="72ad8-253">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="72ad8-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="72ad8-254">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="72ad8-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="72ad8-255">Modelli</span><span class="sxs-lookup"><span data-stu-id="72ad8-255">Templates</span></span>                                    | <span data-ttu-id="72ad8-256">Nome breve</span><span class="sxs-lookup"><span data-stu-id="72ad8-256">Short Name</span></span>    | <span data-ttu-id="72ad8-257">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="72ad8-257">Language</span></span>     | <span data-ttu-id="72ad8-258">Tag</span><span class="sxs-lookup"><span data-stu-id="72ad8-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="72ad8-259">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="72ad8-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="72ad8-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-260">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-261">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="72ad8-261">Common/Console</span></span>      |
| <span data-ttu-id="72ad8-262">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="72ad8-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="72ad8-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-263">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-264">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="72ad8-264">Common/Library</span></span>      |
| <span data-ttu-id="72ad8-265">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="72ad8-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="72ad8-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-266">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-267">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="72ad8-267">Test/MSTest</span></span>         |
| <span data-ttu-id="72ad8-268">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="72ad8-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="72ad8-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="72ad8-269">[C#], F#, VB</span></span> | <span data-ttu-id="72ad8-270">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="72ad8-270">Test/xUnit</span></span>          |
| <span data-ttu-id="72ad8-271">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="72ad8-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="72ad8-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-272">[C#], F#</span></span>     | <span data-ttu-id="72ad8-273">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="72ad8-273">Web/Empty</span></span>           |
| <span data-ttu-id="72ad8-274">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="72ad8-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="72ad8-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-275">[C#], F#</span></span>     | <span data-ttu-id="72ad8-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="72ad8-276">Web/MVC</span></span>             |
| <span data-ttu-id="72ad8-277">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72ad8-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="72ad8-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-278">[C#]</span></span>         | <span data-ttu-id="72ad8-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="72ad8-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="72ad8-280">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="72ad8-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="72ad8-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-281">[C#]</span></span>         | <span data-ttu-id="72ad8-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72ad8-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="72ad8-283">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="72ad8-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="72ad8-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-284">[C#]</span></span>         | <span data-ttu-id="72ad8-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72ad8-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="72ad8-286">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="72ad8-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="72ad8-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-287">[C#]</span></span>         | <span data-ttu-id="72ad8-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="72ad8-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="72ad8-289">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72ad8-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="72ad8-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-290">[C#], F#</span></span>     | <span data-ttu-id="72ad8-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="72ad8-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="72ad8-292">File global.json</span><span class="sxs-lookup"><span data-stu-id="72ad8-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="72ad8-293">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-293">Config</span></span>              |
| <span data-ttu-id="72ad8-294">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="72ad8-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="72ad8-295">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-295">Config</span></span>              |
| <span data-ttu-id="72ad8-296">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="72ad8-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="72ad8-297">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-297">Config</span></span>              |
| <span data-ttu-id="72ad8-298">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="72ad8-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="72ad8-299">Soluzione</span><span class="sxs-lookup"><span data-stu-id="72ad8-299">Solution</span></span>            |
| <span data-ttu-id="72ad8-300">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="72ad8-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="72ad8-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72ad8-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="72ad8-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="72ad8-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="72ad8-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72ad8-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="72ad8-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="72ad8-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="72ad8-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="72ad8-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="72ad8-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="72ad8-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="72ad8-307">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="72ad8-307">The command contains a default list of templates.</span></span> <span data-ttu-id="72ad8-308">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="72ad8-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="72ad8-309">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.0.1.</span><span class="sxs-lookup"><span data-stu-id="72ad8-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="72ad8-310">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="72ad8-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="72ad8-311">Modelli</span><span class="sxs-lookup"><span data-stu-id="72ad8-311">Templates</span></span>            | <span data-ttu-id="72ad8-312">Nome breve</span><span class="sxs-lookup"><span data-stu-id="72ad8-312">Short Name</span></span>    | <span data-ttu-id="72ad8-313">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="72ad8-313">Language</span></span> | <span data-ttu-id="72ad8-314">Tag</span><span class="sxs-lookup"><span data-stu-id="72ad8-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="72ad8-315">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="72ad8-315">Console Application</span></span>  | `console`     | <span data-ttu-id="72ad8-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-316">[C#], F#</span></span> | <span data-ttu-id="72ad8-317">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="72ad8-317">Common/Console</span></span> |
| <span data-ttu-id="72ad8-318">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="72ad8-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="72ad8-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-319">[C#], F#</span></span> | <span data-ttu-id="72ad8-320">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="72ad8-320">Common/Library</span></span> |
| <span data-ttu-id="72ad8-321">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="72ad8-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="72ad8-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-322">[C#], F#</span></span> | <span data-ttu-id="72ad8-323">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="72ad8-323">Test/MSTest</span></span>    |
| <span data-ttu-id="72ad8-324">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="72ad8-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="72ad8-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-325">[C#], F#</span></span> | <span data-ttu-id="72ad8-326">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="72ad8-326">Test/xUnit</span></span>     |
| <span data-ttu-id="72ad8-327">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="72ad8-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="72ad8-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-328">[C#]</span></span>     | <span data-ttu-id="72ad8-329">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="72ad8-329">Web/Empty</span></span>      |
| <span data-ttu-id="72ad8-330">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72ad8-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="72ad8-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="72ad8-331">[C#], F#</span></span> | <span data-ttu-id="72ad8-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="72ad8-332">Web/MVC</span></span>        |
| <span data-ttu-id="72ad8-333">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="72ad8-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="72ad8-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="72ad8-334">[C#]</span></span>     | <span data-ttu-id="72ad8-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="72ad8-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="72ad8-336">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="72ad8-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="72ad8-337">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-337">Config</span></span>         |
| <span data-ttu-id="72ad8-338">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="72ad8-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="72ad8-339">Config</span><span class="sxs-lookup"><span data-stu-id="72ad8-339">Config</span></span>         |
| <span data-ttu-id="72ad8-340">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="72ad8-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="72ad8-341">Soluzione</span><span class="sxs-lookup"><span data-stu-id="72ad8-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="72ad8-342">Opzioni</span><span class="sxs-lookup"><span data-stu-id="72ad8-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="72ad8-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="72ad8-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="72ad8-344">Visualizza un riepilogo di cosa accadrebbe se venisse eseguito il comando specificato e se venisse creato un modello.</span><span class="sxs-lookup"><span data-stu-id="72ad8-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="72ad8-345">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="72ad8-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="72ad8-346">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="72ad8-347">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="72ad8-347">Prints out help for the command.</span></span> <span data-ttu-id="72ad8-348">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="72ad8-349">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="72ad8-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="72ad8-350">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="72ad8-351">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="72ad8-352">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="72ad8-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="72ad8-353">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="72ad8-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="72ad8-354">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="72ad8-355">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="72ad8-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="72ad8-356">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="72ad8-357">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-357">The language of the template to create.</span></span> <span data-ttu-id="72ad8-358">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="72ad8-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="72ad8-359">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="72ad8-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="72ad8-360">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="72ad8-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="72ad8-361">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="72ad8-362">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-362">The name for the created output.</span></span> <span data-ttu-id="72ad8-363">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="72ad8-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="72ad8-364">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="72ad8-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72ad8-365">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-365">Location to place the generated output.</span></span> <span data-ttu-id="72ad8-366">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="72ad8-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="72ad8-367">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="72ad8-367">Filters templates based on available types.</span></span> <span data-ttu-id="72ad8-368">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="72ad8-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="72ad8-369">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="72ad8-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="72ad8-370">Quando si esclude il valore di `<PATH|NUGET_ID>` vengono visualizzati tutti i pacchetti di modelli attualmente installati e i relativi modelli associati.</span><span class="sxs-lookup"><span data-stu-id="72ad8-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="72ad8-371">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="72ad8-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="72ad8-372">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="72ad8-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="72ad8-373">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="72ad8-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="72ad8-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="72ad8-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="72ad8-375">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="72ad8-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="72ad8-376">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="72ad8-377">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="72ad8-377">Prints out help for the command.</span></span> <span data-ttu-id="72ad8-378">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="72ad8-379">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="72ad8-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="72ad8-380">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="72ad8-381">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="72ad8-382">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="72ad8-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="72ad8-383">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="72ad8-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="72ad8-384">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="72ad8-385">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="72ad8-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="72ad8-386">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="72ad8-387">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-387">The language of the template to create.</span></span> <span data-ttu-id="72ad8-388">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="72ad8-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="72ad8-389">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="72ad8-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="72ad8-390">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="72ad8-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="72ad8-391">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="72ad8-392">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-392">The name for the created output.</span></span> <span data-ttu-id="72ad8-393">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="72ad8-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="72ad8-394">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="72ad8-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72ad8-395">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-395">Location to place the generated output.</span></span> <span data-ttu-id="72ad8-396">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="72ad8-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="72ad8-397">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="72ad8-397">Filters templates based on available types.</span></span> <span data-ttu-id="72ad8-398">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="72ad8-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="72ad8-399">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="72ad8-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="72ad8-400">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="72ad8-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="72ad8-401">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="72ad8-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="72ad8-402">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="72ad8-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="72ad8-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72ad8-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="72ad8-404">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="72ad8-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="72ad8-405">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="72ad8-406">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="72ad8-406">Prints out help for the command.</span></span> <span data-ttu-id="72ad8-407">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="72ad8-408">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="72ad8-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="72ad8-409">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="72ad8-410">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="72ad8-411">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="72ad8-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="72ad8-412">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="72ad8-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="72ad8-413">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="72ad8-414">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="72ad8-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="72ad8-415">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="72ad8-416">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-416">The language of the template to create.</span></span> <span data-ttu-id="72ad8-417">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="72ad8-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="72ad8-418">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="72ad8-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="72ad8-419">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="72ad8-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="72ad8-420">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="72ad8-421">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-421">The name for the created output.</span></span> <span data-ttu-id="72ad8-422">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="72ad8-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72ad8-423">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-423">Location to place the generated output.</span></span> <span data-ttu-id="72ad8-424">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="72ad8-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="72ad8-425">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="72ad8-425">Filters templates based on available types.</span></span> <span data-ttu-id="72ad8-426">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="72ad8-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="72ad8-427">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="72ad8-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="72ad8-428">Per disinstallare un modello con un valore `PATH` di origine, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="72ad8-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="72ad8-429">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="72ad8-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="72ad8-430">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="72ad8-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="72ad8-431">Se non è possibile determinare l'argomento `PATH` o `NUGET_ID` necessario per disinstallare un modello, eseguendo `dotnet new --uninstall` senza un argomento, verranno elencati tutti i modelli installati e l'argomento necessario per disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="72ad8-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="72ad8-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="72ad8-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="72ad8-433">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="72ad8-434">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="72ad8-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="72ad8-435">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="72ad8-436">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="72ad8-436">Prints out help for the command.</span></span> <span data-ttu-id="72ad8-437">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="72ad8-438">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="72ad8-439">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="72ad8-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="72ad8-440">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="72ad8-441">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-441">The language of the template to create.</span></span> <span data-ttu-id="72ad8-442">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="72ad8-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="72ad8-443">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="72ad8-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="72ad8-444">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="72ad8-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="72ad8-445">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="72ad8-446">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-446">The name for the created output.</span></span> <span data-ttu-id="72ad8-447">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="72ad8-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="72ad8-448">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-448">Location to place the generated output.</span></span> <span data-ttu-id="72ad8-449">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="72ad8-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="72ad8-450">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="72ad8-450">Template options</span></span>

<span data-ttu-id="72ad8-451">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="72ad8-451">Each project template may have additional options available.</span></span> <span data-ttu-id="72ad8-452">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="72ad8-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="72ad8-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="72ad8-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="72ad8-454">**console**</span><span class="sxs-lookup"><span data-stu-id="72ad8-454">**console**</span></span>

<span data-ttu-id="72ad8-455">`--langVersion <VERSION_NUMBER>`: imposta la proprietà `LangVersion` nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="72ad8-456">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="72ad8-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="72ad8-457">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="72ad8-457">Not supported for F#.</span></span>

<span data-ttu-id="72ad8-458">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="72ad8-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="72ad8-460">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72ad8-461">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-462">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72ad8-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72ad8-463">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="72ad8-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="72ad8-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="72ad8-464">**razorclasslib**</span></span>

<span data-ttu-id="72ad8-465">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="72ad8-466">**classlib**</span></span>

<span data-ttu-id="72ad8-467">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="72ad8-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72ad8-468">Valori: `netcoreapp2.2` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="72ad8-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="72ad8-469">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="72ad8-470">`--langVersion <VERSION_NUMBER>`: imposta la proprietà `LangVersion` nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="72ad8-471">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="72ad8-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="72ad8-472">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="72ad8-472">Not supported for F#.</span></span>

<span data-ttu-id="72ad8-473">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="72ad8-474">**mstest, xunit**</span></span>

<span data-ttu-id="72ad8-475">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="72ad8-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="72ad8-476">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="72ad8-477">**nunit**</span></span>

<span data-ttu-id="72ad8-478">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="72ad8-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72ad8-479">Il valore predefinito è `netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="72ad8-480">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="72ad8-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="72ad8-481">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-482">**page**</span><span class="sxs-lookup"><span data-stu-id="72ad8-482">**page**</span></span>

<span data-ttu-id="72ad8-483">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="72ad8-484">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="72ad8-485">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="72ad8-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="72ad8-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="72ad8-486">**viewimports**</span></span>

<span data-ttu-id="72ad8-487">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="72ad8-488">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="72ad8-489">**web**</span><span class="sxs-lookup"><span data-stu-id="72ad8-489">**web**</span></span>

<span data-ttu-id="72ad8-490">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72ad8-491">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-492">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72ad8-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72ad8-493">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="72ad8-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="72ad8-494">**mvc, webapp**</span><span class="sxs-lookup"><span data-stu-id="72ad8-494">**mvc, webapp**</span></span>

<span data-ttu-id="72ad8-495">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72ad8-496">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="72ad8-496">The possible values are:</span></span>

- <span data-ttu-id="72ad8-497">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="72ad8-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72ad8-498">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="72ad8-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="72ad8-499">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="72ad8-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72ad8-500">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="72ad8-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72ad8-501">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="72ad8-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="72ad8-502">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="72ad8-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72ad8-503">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72ad8-504">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-505">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72ad8-506">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72ad8-507">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-508">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="72ad8-509">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-510">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="72ad8-511">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-512">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72ad8-513">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="72ad8-514">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72ad8-515">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72ad8-516">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="72ad8-517">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72ad8-518">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72ad8-519">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-520">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72ad8-521">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72ad8-522">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-523">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72ad8-524">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="72ad8-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="72ad8-525">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-526">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="72ad8-527">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72ad8-528">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72ad8-529">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72ad8-530">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72ad8-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72ad8-531">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="72ad8-532">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="72ad8-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="72ad8-533">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="72ad8-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72ad8-534">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-535">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="72ad8-536">**webapi**</span></span>

<span data-ttu-id="72ad8-537">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72ad8-538">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="72ad8-538">The possible values are:</span></span>

- <span data-ttu-id="72ad8-539">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="72ad8-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72ad8-540">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="72ad8-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72ad8-541">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="72ad8-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72ad8-542">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="72ad8-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72ad8-543">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72ad8-544">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-545">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72ad8-546">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72ad8-547">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-548">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72ad8-549">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-550">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72ad8-551">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72ad8-552">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-553">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72ad8-554">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72ad8-555">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-556">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72ad8-557">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72ad8-558">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-559">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72ad8-560">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72ad8-561">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72ad8-562">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72ad8-563">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72ad8-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72ad8-564">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="72ad8-565">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="72ad8-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="72ad8-566">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="72ad8-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72ad8-567">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-568">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="72ad8-569">**globaljson**</span></span>

<span data-ttu-id="72ad8-570">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="72ad8-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="72ad8-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="72ad8-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="72ad8-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="72ad8-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="72ad8-573">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="72ad8-574">**classlib**</span></span>

<span data-ttu-id="72ad8-575">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="72ad8-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72ad8-576">Valori: `netcoreapp2.1` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="72ad8-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="72ad8-577">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="72ad8-578">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="72ad8-579">**mstest, xunit**</span></span>

<span data-ttu-id="72ad8-580">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="72ad8-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="72ad8-581">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="72ad8-582">**globaljson**</span></span>

<span data-ttu-id="72ad8-583">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="72ad8-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="72ad8-584">**web**</span><span class="sxs-lookup"><span data-stu-id="72ad8-584">**web**</span></span>

<span data-ttu-id="72ad8-585">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72ad8-586">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-587">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72ad8-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72ad8-588">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="72ad8-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="72ad8-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="72ad8-589">**webapi**</span></span>

<span data-ttu-id="72ad8-590">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72ad8-591">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="72ad8-591">The possible values are:</span></span>

- <span data-ttu-id="72ad8-592">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="72ad8-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72ad8-593">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="72ad8-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72ad8-594">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="72ad8-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72ad8-595">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="72ad8-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72ad8-596">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72ad8-597">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-598">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72ad8-599">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72ad8-600">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-601">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72ad8-602">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-603">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72ad8-604">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72ad8-605">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-606">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72ad8-607">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72ad8-608">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-609">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72ad8-610">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72ad8-611">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-612">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72ad8-613">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72ad8-614">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72ad8-615">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72ad8-616">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="72ad8-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72ad8-617">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-618">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-619">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72ad8-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72ad8-620">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="72ad8-621">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="72ad8-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="72ad8-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="72ad8-622">**mvc, razor**</span></span>

<span data-ttu-id="72ad8-623">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72ad8-624">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="72ad8-624">The possible values are:</span></span>

- <span data-ttu-id="72ad8-625">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="72ad8-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72ad8-626">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="72ad8-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="72ad8-627">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="72ad8-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72ad8-628">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="72ad8-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72ad8-629">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="72ad8-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="72ad8-630">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="72ad8-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72ad8-631">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72ad8-632">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-633">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72ad8-634">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72ad8-635">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-636">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="72ad8-637">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-638">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="72ad8-639">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-640">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72ad8-641">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="72ad8-642">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72ad8-643">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72ad8-644">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="72ad8-645">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72ad8-646">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72ad8-647">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-648">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72ad8-649">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72ad8-650">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-651">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72ad8-652">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="72ad8-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="72ad8-653">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-654">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="72ad8-655">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72ad8-656">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72ad8-657">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="72ad8-658">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="72ad8-659">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="72ad8-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72ad8-660">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-661">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-662">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="72ad8-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="72ad8-663">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="72ad8-664">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="72ad8-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="72ad8-665">**page**</span><span class="sxs-lookup"><span data-stu-id="72ad8-665">**page**</span></span>

<span data-ttu-id="72ad8-666">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="72ad8-667">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="72ad8-668">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="72ad8-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="72ad8-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="72ad8-669">**viewimports**</span></span>

<span data-ttu-id="72ad8-670">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="72ad8-671">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="72ad8-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="72ad8-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="72ad8-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="72ad8-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="72ad8-674">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="72ad8-675">**classlib**</span></span>

<span data-ttu-id="72ad8-676">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="72ad8-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72ad8-677">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="72ad8-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="72ad8-678">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="72ad8-679">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="72ad8-680">**mstest, xunit**</span></span>

<span data-ttu-id="72ad8-681">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="72ad8-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="72ad8-682">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="72ad8-683">**globaljson**</span></span>

<span data-ttu-id="72ad8-684">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="72ad8-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="72ad8-685">**web**</span><span class="sxs-lookup"><span data-stu-id="72ad8-685">**web**</span></span>

<span data-ttu-id="72ad8-686">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="72ad8-687">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="72ad8-688">**webapi**</span></span>

<span data-ttu-id="72ad8-689">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72ad8-690">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="72ad8-690">The possible values are:</span></span>

- <span data-ttu-id="72ad8-691">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="72ad8-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72ad8-692">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="72ad8-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72ad8-693">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="72ad8-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72ad8-694">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="72ad8-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72ad8-695">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72ad8-696">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-697">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72ad8-698">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72ad8-699">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-700">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72ad8-701">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-702">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72ad8-703">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72ad8-704">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-705">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72ad8-706">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72ad8-707">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-708">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72ad8-709">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72ad8-710">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-711">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72ad8-712">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72ad8-713">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72ad8-714">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="72ad8-715">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="72ad8-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72ad8-716">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-717">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="72ad8-718">**mvc, razor**</span></span>

<span data-ttu-id="72ad8-719">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72ad8-720">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="72ad8-720">The possible values are:</span></span>

- <span data-ttu-id="72ad8-721">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="72ad8-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="72ad8-722">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="72ad8-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="72ad8-723">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="72ad8-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="72ad8-724">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="72ad8-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="72ad8-725">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="72ad8-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="72ad8-726">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="72ad8-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="72ad8-727">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="72ad8-728">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-729">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="72ad8-730">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="72ad8-731">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-732">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="72ad8-733">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-734">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="72ad8-735">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-736">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="72ad8-737">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="72ad8-738">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="72ad8-739">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="72ad8-740">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="72ad8-741">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="72ad8-742">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="72ad8-743">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-744">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="72ad8-745">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="72ad8-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="72ad8-746">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="72ad8-747">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="72ad8-748">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="72ad8-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="72ad8-749">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="72ad8-750">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="72ad8-751">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="72ad8-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="72ad8-752">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="72ad8-753">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="72ad8-754">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="72ad8-755">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="72ad8-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="72ad8-756">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="72ad8-757">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="72ad8-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="72ad8-758">**page**</span><span class="sxs-lookup"><span data-stu-id="72ad8-758">**page**</span></span>

<span data-ttu-id="72ad8-759">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="72ad8-760">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="72ad8-761">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="72ad8-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="72ad8-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="72ad8-762">**viewimports**</span></span>

<span data-ttu-id="72ad8-763">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="72ad8-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="72ad8-764">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="72ad8-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="72ad8-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="72ad8-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="72ad8-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="72ad8-767">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="72ad8-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72ad8-768">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="72ad8-769">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="72ad8-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="72ad8-770">**classlib**</span></span>

<span data-ttu-id="72ad8-771">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="72ad8-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72ad8-772">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="72ad8-773">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="72ad8-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="72ad8-774">**mvc**</span></span>

<span data-ttu-id="72ad8-775">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="72ad8-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="72ad8-776">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="72ad8-777">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="72ad8-778">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="72ad8-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="72ad8-779">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="72ad8-780">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-780">The default value is `None`.</span></span>

<span data-ttu-id="72ad8-781">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="72ad8-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="72ad8-782">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-782">Values: `true` or `false`.</span></span> <span data-ttu-id="72ad8-783">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="72ad8-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="72ad8-784">Esempi</span><span class="sxs-lookup"><span data-stu-id="72ad8-784">Examples</span></span>

<span data-ttu-id="72ad8-785">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="72ad8-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="72ad8-786">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="72ad8-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="72ad8-787">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="72ad8-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="72ad8-788">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="72ad8-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="72ad8-789">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="72ad8-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="72ad8-790">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="72ad8-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="72ad8-791">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="72ad8-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="72ad8-792">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="72ad8-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="72ad8-793">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="72ad8-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="72ad8-794">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="72ad8-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="72ad8-795">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="72ad8-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="72ad8-796">Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):</span><span class="sxs-lookup"><span data-stu-id="72ad8-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="72ad8-797">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72ad8-797">See also</span></span>

- [<span data-ttu-id="72ad8-798">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="72ad8-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="72ad8-799">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="72ad8-799">Create a custom template for dotnet new</span></span>](../tutorials/create-custom-template.md)
- [<span data-ttu-id="72ad8-800">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="72ad8-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="72ad8-801">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="72ad8-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
