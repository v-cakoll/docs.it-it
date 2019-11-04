---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 05/06/2019
ms.openlocfilehash: c9529e135f48c80f445c91038294a3e7266486f1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/01/2019
ms.locfileid: "73420469"
---
# <a name="dotnet-new"></a><span data-ttu-id="cdc26-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="cdc26-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="cdc26-104">Name</span><span class="sxs-lookup"><span data-stu-id="cdc26-104">Name</span></span>

<span data-ttu-id="cdc26-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="cdc26-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="cdc26-106">Synopsis</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="cdc26-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cdc26-107">.NET Core 2.2</span></span>](#tab/netcore22)

```dotnetcli
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cdc26-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cdc26-108">.NET Core 2.1</span></span>](#tab/netcore21)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cdc26-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cdc26-109">.NET Core 2.0</span></span>](#tab/netcore20)

```dotnetcli
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cdc26-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cdc26-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```dotnetcli
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="cdc26-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cdc26-111">Description</span></span>

<span data-ttu-id="cdc26-112">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="cdc26-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="cdc26-113">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="cdc26-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="cdc26-114">argomenti</span><span class="sxs-lookup"><span data-stu-id="cdc26-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="cdc26-115">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="cdc26-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="cdc26-116">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="cdc26-117">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="cdc26-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="cdc26-118">Se il valore di `TEMPLATE` non è una corrispondenza esatta del testo nella colonna **Modelli** o **Nome breve** viene eseguita una corrispondenza sottostringa in queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="cdc26-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="cdc26-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cdc26-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="cdc26-120">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="cdc26-120">The command contains a default list of templates.</span></span> <span data-ttu-id="cdc26-121">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="cdc26-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="cdc26-122">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.2.100.</span><span class="sxs-lookup"><span data-stu-id="cdc26-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="cdc26-123">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="cdc26-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="cdc26-124">Modelli</span><span class="sxs-lookup"><span data-stu-id="cdc26-124">Templates</span></span>                                    | <span data-ttu-id="cdc26-125">Nome breve</span><span class="sxs-lookup"><span data-stu-id="cdc26-125">Short Name</span></span>        | <span data-ttu-id="cdc26-126">Language</span><span class="sxs-lookup"><span data-stu-id="cdc26-126">Language</span></span>     | <span data-ttu-id="cdc26-127">Tag</span><span class="sxs-lookup"><span data-stu-id="cdc26-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="cdc26-128">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="cdc26-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="cdc26-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-129">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-130">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="cdc26-130">Common/Console</span></span>                        |
| <span data-ttu-id="cdc26-131">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="cdc26-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="cdc26-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-132">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-133">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="cdc26-133">Common/Library</span></span>                        |
| <span data-ttu-id="cdc26-134">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="cdc26-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="cdc26-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-135">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-136">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="cdc26-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="cdc26-137">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="cdc26-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="cdc26-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-138">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-139">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="cdc26-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="cdc26-140">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="cdc26-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="cdc26-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-141">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-142">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="cdc26-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="cdc26-143">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="cdc26-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="cdc26-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-144">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-145">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="cdc26-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="cdc26-146">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="cdc26-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="cdc26-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-147">[C#]</span></span>         | <span data-ttu-id="cdc26-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cdc26-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cdc26-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="cdc26-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="cdc26-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-150">[C#]</span></span>         | <span data-ttu-id="cdc26-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cdc26-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cdc26-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="cdc26-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="cdc26-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-153">[C#]</span></span>         | <span data-ttu-id="cdc26-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cdc26-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cdc26-155">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="cdc26-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="cdc26-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-156">[C#], F#</span></span>     | <span data-ttu-id="cdc26-157">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="cdc26-157">Web/Empty</span></span>                             |
| <span data-ttu-id="cdc26-158">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="cdc26-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="cdc26-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-159">[C#], F#</span></span>     | <span data-ttu-id="cdc26-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="cdc26-160">Web/MVC</span></span>                               |
| <span data-ttu-id="cdc26-161">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cdc26-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="cdc26-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="cdc26-162">`webapp`, `razor`</span></span> | <span data-ttu-id="cdc26-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-163">[C#]</span></span>         | <span data-ttu-id="cdc26-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="cdc26-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="cdc26-165">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="cdc26-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="cdc26-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-166">[C#]</span></span>         | <span data-ttu-id="cdc26-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="cdc26-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="cdc26-168">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="cdc26-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="cdc26-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-169">[C#]</span></span>         | <span data-ttu-id="cdc26-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="cdc26-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="cdc26-171">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="cdc26-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="cdc26-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-172">[C#]</span></span>         | <span data-ttu-id="cdc26-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="cdc26-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="cdc26-174">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="cdc26-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="cdc26-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-175">[C#]</span></span>         | <span data-ttu-id="cdc26-176">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="cdc26-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="cdc26-177">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cdc26-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="cdc26-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-178">[C#], F#</span></span>     | <span data-ttu-id="cdc26-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="cdc26-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="cdc26-180">File global.json</span><span class="sxs-lookup"><span data-stu-id="cdc26-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="cdc26-181">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-181">Config</span></span>                                |
| <span data-ttu-id="cdc26-182">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="cdc26-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="cdc26-183">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-183">Config</span></span>                                |
| <span data-ttu-id="cdc26-184">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="cdc26-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="cdc26-185">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-185">Config</span></span>                                |
| <span data-ttu-id="cdc26-186">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="cdc26-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="cdc26-187">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cdc26-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cdc26-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cdc26-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="cdc26-189">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="cdc26-189">The command contains a default list of templates.</span></span> <span data-ttu-id="cdc26-190">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="cdc26-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="cdc26-191">La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="cdc26-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="cdc26-192">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="cdc26-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="cdc26-193">Modelli</span><span class="sxs-lookup"><span data-stu-id="cdc26-193">Templates</span></span>                                    | <span data-ttu-id="cdc26-194">Nome breve</span><span class="sxs-lookup"><span data-stu-id="cdc26-194">Short Name</span></span>      | <span data-ttu-id="cdc26-195">Language</span><span class="sxs-lookup"><span data-stu-id="cdc26-195">Language</span></span>     | <span data-ttu-id="cdc26-196">Tag</span><span class="sxs-lookup"><span data-stu-id="cdc26-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="cdc26-197">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="cdc26-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="cdc26-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-198">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-199">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="cdc26-199">Common/Console</span></span>                        |
| <span data-ttu-id="cdc26-200">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="cdc26-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="cdc26-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-201">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-202">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="cdc26-202">Common/Library</span></span>                        |
| <span data-ttu-id="cdc26-203">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="cdc26-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="cdc26-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-204">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-205">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="cdc26-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="cdc26-206">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="cdc26-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="cdc26-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-207">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-208">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="cdc26-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="cdc26-209">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="cdc26-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="cdc26-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-210">[C#]</span></span>         | <span data-ttu-id="cdc26-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cdc26-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cdc26-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="cdc26-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="cdc26-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-213">[C#]</span></span>         | <span data-ttu-id="cdc26-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cdc26-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cdc26-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="cdc26-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="cdc26-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-216">[C#]</span></span>         | <span data-ttu-id="cdc26-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cdc26-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="cdc26-218">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="cdc26-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="cdc26-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-219">[C#], F#</span></span>     | <span data-ttu-id="cdc26-220">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="cdc26-220">Web/Empty</span></span>                             |
| <span data-ttu-id="cdc26-221">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="cdc26-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="cdc26-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-222">[C#], F#</span></span>     | <span data-ttu-id="cdc26-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="cdc26-223">Web/MVC</span></span>                               |
| <span data-ttu-id="cdc26-224">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cdc26-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="cdc26-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-225">[C#]</span></span>         | <span data-ttu-id="cdc26-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="cdc26-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="cdc26-227">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="cdc26-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="cdc26-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-228">[C#]</span></span>         | <span data-ttu-id="cdc26-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="cdc26-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="cdc26-230">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="cdc26-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="cdc26-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-231">[C#]</span></span>         | <span data-ttu-id="cdc26-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="cdc26-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="cdc26-233">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="cdc26-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="cdc26-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-234">[C#]</span></span>         | <span data-ttu-id="cdc26-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="cdc26-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="cdc26-236">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="cdc26-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="cdc26-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-237">[C#]</span></span>         | <span data-ttu-id="cdc26-238">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="cdc26-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="cdc26-239">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cdc26-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="cdc26-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-240">[C#], F#</span></span>     | <span data-ttu-id="cdc26-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="cdc26-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="cdc26-242">File global.json</span><span class="sxs-lookup"><span data-stu-id="cdc26-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="cdc26-243">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-243">Config</span></span>                                |
| <span data-ttu-id="cdc26-244">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="cdc26-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="cdc26-245">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-245">Config</span></span>                                |
| <span data-ttu-id="cdc26-246">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="cdc26-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="cdc26-247">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-247">Config</span></span>                                |
| <span data-ttu-id="cdc26-248">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="cdc26-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="cdc26-249">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cdc26-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cdc26-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cdc26-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="cdc26-251">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="cdc26-251">The command contains a default list of templates.</span></span> <span data-ttu-id="cdc26-252">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="cdc26-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="cdc26-253">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="cdc26-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="cdc26-254">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="cdc26-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="cdc26-255">Modelli</span><span class="sxs-lookup"><span data-stu-id="cdc26-255">Templates</span></span>                                    | <span data-ttu-id="cdc26-256">Nome breve</span><span class="sxs-lookup"><span data-stu-id="cdc26-256">Short Name</span></span>    | <span data-ttu-id="cdc26-257">Language</span><span class="sxs-lookup"><span data-stu-id="cdc26-257">Language</span></span>     | <span data-ttu-id="cdc26-258">Tag</span><span class="sxs-lookup"><span data-stu-id="cdc26-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="cdc26-259">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="cdc26-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="cdc26-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-260">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-261">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="cdc26-261">Common/Console</span></span>      |
| <span data-ttu-id="cdc26-262">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="cdc26-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="cdc26-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-263">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-264">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="cdc26-264">Common/Library</span></span>      |
| <span data-ttu-id="cdc26-265">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="cdc26-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="cdc26-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-266">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-267">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="cdc26-267">Test/MSTest</span></span>         |
| <span data-ttu-id="cdc26-268">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="cdc26-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="cdc26-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="cdc26-269">[C#], F#, VB</span></span> | <span data-ttu-id="cdc26-270">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="cdc26-270">Test/xUnit</span></span>          |
| <span data-ttu-id="cdc26-271">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="cdc26-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="cdc26-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-272">[C#], F#</span></span>     | <span data-ttu-id="cdc26-273">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="cdc26-273">Web/Empty</span></span>           |
| <span data-ttu-id="cdc26-274">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="cdc26-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="cdc26-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-275">[C#], F#</span></span>     | <span data-ttu-id="cdc26-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="cdc26-276">Web/MVC</span></span>             |
| <span data-ttu-id="cdc26-277">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cdc26-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="cdc26-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-278">[C#]</span></span>         | <span data-ttu-id="cdc26-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="cdc26-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="cdc26-280">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="cdc26-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="cdc26-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-281">[C#]</span></span>         | <span data-ttu-id="cdc26-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="cdc26-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="cdc26-283">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="cdc26-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="cdc26-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-284">[C#]</span></span>         | <span data-ttu-id="cdc26-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="cdc26-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="cdc26-286">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="cdc26-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="cdc26-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-287">[C#]</span></span>         | <span data-ttu-id="cdc26-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="cdc26-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="cdc26-289">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cdc26-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="cdc26-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-290">[C#], F#</span></span>     | <span data-ttu-id="cdc26-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="cdc26-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="cdc26-292">File global.json</span><span class="sxs-lookup"><span data-stu-id="cdc26-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="cdc26-293">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-293">Config</span></span>              |
| <span data-ttu-id="cdc26-294">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="cdc26-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="cdc26-295">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-295">Config</span></span>              |
| <span data-ttu-id="cdc26-296">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="cdc26-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="cdc26-297">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-297">Config</span></span>              |
| <span data-ttu-id="cdc26-298">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="cdc26-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="cdc26-299">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cdc26-299">Solution</span></span>            |
| <span data-ttu-id="cdc26-300">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="cdc26-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="cdc26-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cdc26-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="cdc26-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="cdc26-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="cdc26-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cdc26-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="cdc26-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="cdc26-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="cdc26-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cdc26-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cdc26-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cdc26-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="cdc26-307">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="cdc26-307">The command contains a default list of templates.</span></span> <span data-ttu-id="cdc26-308">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="cdc26-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="cdc26-309">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.0.1.</span><span class="sxs-lookup"><span data-stu-id="cdc26-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="cdc26-310">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="cdc26-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="cdc26-311">Modelli</span><span class="sxs-lookup"><span data-stu-id="cdc26-311">Templates</span></span>            | <span data-ttu-id="cdc26-312">Nome breve</span><span class="sxs-lookup"><span data-stu-id="cdc26-312">Short Name</span></span>    | <span data-ttu-id="cdc26-313">Language</span><span class="sxs-lookup"><span data-stu-id="cdc26-313">Language</span></span> | <span data-ttu-id="cdc26-314">Tag</span><span class="sxs-lookup"><span data-stu-id="cdc26-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="cdc26-315">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="cdc26-315">Console Application</span></span>  | `console`     | <span data-ttu-id="cdc26-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-316">[C#], F#</span></span> | <span data-ttu-id="cdc26-317">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="cdc26-317">Common/Console</span></span> |
| <span data-ttu-id="cdc26-318">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="cdc26-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="cdc26-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-319">[C#], F#</span></span> | <span data-ttu-id="cdc26-320">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="cdc26-320">Common/Library</span></span> |
| <span data-ttu-id="cdc26-321">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="cdc26-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="cdc26-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-322">[C#], F#</span></span> | <span data-ttu-id="cdc26-323">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="cdc26-323">Test/MSTest</span></span>    |
| <span data-ttu-id="cdc26-324">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="cdc26-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="cdc26-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-325">[C#], F#</span></span> | <span data-ttu-id="cdc26-326">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="cdc26-326">Test/xUnit</span></span>     |
| <span data-ttu-id="cdc26-327">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="cdc26-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="cdc26-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-328">[C#]</span></span>     | <span data-ttu-id="cdc26-329">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="cdc26-329">Web/Empty</span></span>      |
| <span data-ttu-id="cdc26-330">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cdc26-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="cdc26-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="cdc26-331">[C#], F#</span></span> | <span data-ttu-id="cdc26-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="cdc26-332">Web/MVC</span></span>        |
| <span data-ttu-id="cdc26-333">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="cdc26-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="cdc26-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="cdc26-334">[C#]</span></span>     | <span data-ttu-id="cdc26-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="cdc26-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="cdc26-336">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="cdc26-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="cdc26-337">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-337">Config</span></span>         |
| <span data-ttu-id="cdc26-338">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="cdc26-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="cdc26-339">Config</span><span class="sxs-lookup"><span data-stu-id="cdc26-339">Config</span></span>         |
| <span data-ttu-id="cdc26-340">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="cdc26-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="cdc26-341">Soluzione</span><span class="sxs-lookup"><span data-stu-id="cdc26-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="cdc26-342">Opzioni</span><span class="sxs-lookup"><span data-stu-id="cdc26-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="cdc26-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cdc26-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="cdc26-344">Visualizza un riepilogo di cosa accadrebbe se venisse eseguito il comando specificato e se venisse creato un modello.</span><span class="sxs-lookup"><span data-stu-id="cdc26-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="cdc26-345">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="cdc26-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="cdc26-346">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="cdc26-347">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="cdc26-347">Prints out help for the command.</span></span> <span data-ttu-id="cdc26-348">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="cdc26-349">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="cdc26-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="cdc26-350">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="cdc26-351">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="cdc26-352">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="cdc26-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="cdc26-353">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="cdc26-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="cdc26-354">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="cdc26-355">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="cdc26-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="cdc26-356">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="cdc26-357">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-357">The language of the template to create.</span></span> <span data-ttu-id="cdc26-358">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="cdc26-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="cdc26-359">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="cdc26-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc26-360">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="cdc26-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="cdc26-361">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="cdc26-362">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-362">The name for the created output.</span></span> <span data-ttu-id="cdc26-363">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cdc26-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="cdc26-364">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="cdc26-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cdc26-365">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-365">Location to place the generated output.</span></span> <span data-ttu-id="cdc26-366">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cdc26-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="cdc26-367">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="cdc26-367">Filters templates based on available types.</span></span> <span data-ttu-id="cdc26-368">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="cdc26-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="cdc26-369">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="cdc26-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="cdc26-370">Quando si esclude il valore di `<PATH|NUGET_ID>` vengono visualizzati tutti i pacchetti di modelli attualmente installati e i relativi modelli associati.</span><span class="sxs-lookup"><span data-stu-id="cdc26-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc26-371">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="cdc26-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="cdc26-372">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="cdc26-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="cdc26-373">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="cdc26-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cdc26-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cdc26-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="cdc26-375">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="cdc26-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="cdc26-376">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="cdc26-377">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="cdc26-377">Prints out help for the command.</span></span> <span data-ttu-id="cdc26-378">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="cdc26-379">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="cdc26-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="cdc26-380">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="cdc26-381">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="cdc26-382">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="cdc26-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="cdc26-383">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="cdc26-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="cdc26-384">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="cdc26-385">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="cdc26-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="cdc26-386">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="cdc26-387">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-387">The language of the template to create.</span></span> <span data-ttu-id="cdc26-388">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="cdc26-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="cdc26-389">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="cdc26-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc26-390">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="cdc26-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="cdc26-391">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="cdc26-392">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-392">The name for the created output.</span></span> <span data-ttu-id="cdc26-393">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cdc26-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="cdc26-394">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="cdc26-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cdc26-395">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-395">Location to place the generated output.</span></span> <span data-ttu-id="cdc26-396">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cdc26-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="cdc26-397">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="cdc26-397">Filters templates based on available types.</span></span> <span data-ttu-id="cdc26-398">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="cdc26-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="cdc26-399">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="cdc26-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc26-400">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="cdc26-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="cdc26-401">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="cdc26-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="cdc26-402">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="cdc26-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cdc26-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cdc26-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="cdc26-404">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="cdc26-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="cdc26-405">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="cdc26-406">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="cdc26-406">Prints out help for the command.</span></span> <span data-ttu-id="cdc26-407">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="cdc26-408">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="cdc26-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="cdc26-409">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="cdc26-410">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="cdc26-411">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="cdc26-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="cdc26-412">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="cdc26-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="cdc26-413">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="cdc26-414">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="cdc26-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="cdc26-415">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="cdc26-416">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-416">The language of the template to create.</span></span> <span data-ttu-id="cdc26-417">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="cdc26-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="cdc26-418">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="cdc26-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc26-419">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="cdc26-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="cdc26-420">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="cdc26-421">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-421">The name for the created output.</span></span> <span data-ttu-id="cdc26-422">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cdc26-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cdc26-423">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-423">Location to place the generated output.</span></span> <span data-ttu-id="cdc26-424">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cdc26-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="cdc26-425">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="cdc26-425">Filters templates based on available types.</span></span> <span data-ttu-id="cdc26-426">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="cdc26-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="cdc26-427">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="cdc26-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc26-428">Per disinstallare un modello con un valore `PATH` di origine, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="cdc26-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="cdc26-429">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="cdc26-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="cdc26-430">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="cdc26-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="cdc26-431">Se non è possibile determinare l'argomento `PATH` o `NUGET_ID` necessario per disinstallare un modello, eseguendo `dotnet new --uninstall` senza un argomento, verranno elencati tutti i modelli installati e l'argomento necessario per disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="cdc26-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cdc26-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cdc26-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="cdc26-433">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="cdc26-434">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="cdc26-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="cdc26-435">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="cdc26-436">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="cdc26-436">Prints out help for the command.</span></span> <span data-ttu-id="cdc26-437">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="cdc26-438">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="cdc26-439">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="cdc26-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="cdc26-440">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="cdc26-441">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-441">The language of the template to create.</span></span> <span data-ttu-id="cdc26-442">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="cdc26-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="cdc26-443">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="cdc26-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc26-444">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="cdc26-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="cdc26-445">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="cdc26-446">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-446">The name for the created output.</span></span> <span data-ttu-id="cdc26-447">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cdc26-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="cdc26-448">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-448">Location to place the generated output.</span></span> <span data-ttu-id="cdc26-449">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="cdc26-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="cdc26-450">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="cdc26-450">Template options</span></span>

<span data-ttu-id="cdc26-451">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="cdc26-451">Each project template may have additional options available.</span></span> <span data-ttu-id="cdc26-452">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdc26-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="cdc26-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cdc26-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="cdc26-454">**console**</span><span class="sxs-lookup"><span data-stu-id="cdc26-454">**console**</span></span>

<span data-ttu-id="cdc26-455">`--langVersion <VERSION_NUMBER>`: imposta la proprietà `LangVersion` nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="cdc26-456">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="cdc26-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="cdc26-457">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="cdc26-457">Not supported for F#.</span></span>

<span data-ttu-id="cdc26-458">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="cdc26-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="cdc26-460">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cdc26-461">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-462">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cdc26-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cdc26-463">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="cdc26-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="cdc26-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="cdc26-464">**razorclasslib**</span></span>

<span data-ttu-id="cdc26-465">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="cdc26-466">**classlib**</span></span>

<span data-ttu-id="cdc26-467">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cdc26-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cdc26-468">Valori: `netcoreapp2.2` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="cdc26-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="cdc26-469">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="cdc26-470">`--langVersion <VERSION_NUMBER>`: imposta la proprietà `LangVersion` nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="cdc26-471">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="cdc26-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="cdc26-472">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="cdc26-472">Not supported for F#.</span></span>

<span data-ttu-id="cdc26-473">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="cdc26-474">**mstest, xunit**</span></span>

<span data-ttu-id="cdc26-475">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="cdc26-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="cdc26-476">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="cdc26-477">**nunit**</span></span>

<span data-ttu-id="cdc26-478">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cdc26-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cdc26-479">Il valore predefinito è `netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="cdc26-480">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="cdc26-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="cdc26-481">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-482">**page**</span><span class="sxs-lookup"><span data-stu-id="cdc26-482">**page**</span></span>

<span data-ttu-id="cdc26-483">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="cdc26-484">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="cdc26-485">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="cdc26-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="cdc26-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="cdc26-486">**viewimports**</span></span>

<span data-ttu-id="cdc26-487">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="cdc26-488">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="cdc26-489">**web**</span><span class="sxs-lookup"><span data-stu-id="cdc26-489">**web**</span></span>

<span data-ttu-id="cdc26-490">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cdc26-491">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-492">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cdc26-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cdc26-493">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="cdc26-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="cdc26-494">**mvc, webapp**</span><span class="sxs-lookup"><span data-stu-id="cdc26-494">**mvc, webapp**</span></span>

<span data-ttu-id="cdc26-495">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cdc26-496">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="cdc26-496">The possible values are:</span></span>

- <span data-ttu-id="cdc26-497">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="cdc26-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cdc26-498">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="cdc26-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="cdc26-499">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cdc26-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cdc26-500">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="cdc26-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cdc26-501">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="cdc26-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="cdc26-502">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="cdc26-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cdc26-503">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cdc26-504">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-505">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cdc26-506">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cdc26-507">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-508">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="cdc26-509">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-510">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="cdc26-511">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-512">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cdc26-513">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="cdc26-514">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cdc26-515">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cdc26-516">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="cdc26-517">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cdc26-518">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cdc26-519">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-520">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cdc26-521">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cdc26-522">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-523">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cdc26-524">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="cdc26-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="cdc26-525">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-526">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="cdc26-527">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cdc26-528">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cdc26-529">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cdc26-530">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cdc26-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cdc26-531">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="cdc26-532">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="cdc26-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="cdc26-533">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="cdc26-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cdc26-534">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-535">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="cdc26-536">**webapi**</span></span>

<span data-ttu-id="cdc26-537">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cdc26-538">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="cdc26-538">The possible values are:</span></span>

- <span data-ttu-id="cdc26-539">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="cdc26-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cdc26-540">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cdc26-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cdc26-541">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="cdc26-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cdc26-542">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="cdc26-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cdc26-543">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cdc26-544">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-545">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cdc26-546">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cdc26-547">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-548">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cdc26-549">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-550">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cdc26-551">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cdc26-552">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-553">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cdc26-554">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cdc26-555">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-556">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cdc26-557">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cdc26-558">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-559">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cdc26-560">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cdc26-561">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cdc26-562">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cdc26-563">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cdc26-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cdc26-564">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="cdc26-565">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="cdc26-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="cdc26-566">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="cdc26-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cdc26-567">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-568">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="cdc26-569">**globaljson**</span></span>

<span data-ttu-id="cdc26-570">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="cdc26-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="cdc26-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cdc26-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="cdc26-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="cdc26-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="cdc26-573">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="cdc26-574">**classlib**</span></span>

<span data-ttu-id="cdc26-575">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cdc26-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cdc26-576">Valori: `netcoreapp2.1` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="cdc26-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="cdc26-577">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="cdc26-578">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="cdc26-579">**mstest, xunit**</span></span>

<span data-ttu-id="cdc26-580">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="cdc26-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="cdc26-581">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="cdc26-582">**globaljson**</span></span>

<span data-ttu-id="cdc26-583">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="cdc26-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="cdc26-584">**web**</span><span class="sxs-lookup"><span data-stu-id="cdc26-584">**web**</span></span>

<span data-ttu-id="cdc26-585">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cdc26-586">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-587">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cdc26-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cdc26-588">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="cdc26-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="cdc26-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="cdc26-589">**webapi**</span></span>

<span data-ttu-id="cdc26-590">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cdc26-591">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="cdc26-591">The possible values are:</span></span>

- <span data-ttu-id="cdc26-592">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="cdc26-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cdc26-593">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cdc26-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cdc26-594">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="cdc26-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cdc26-595">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="cdc26-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cdc26-596">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cdc26-597">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-598">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cdc26-599">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cdc26-600">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-601">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cdc26-602">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-603">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cdc26-604">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cdc26-605">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-606">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cdc26-607">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cdc26-608">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-609">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cdc26-610">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cdc26-611">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-612">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cdc26-613">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cdc26-614">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cdc26-615">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cdc26-616">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="cdc26-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cdc26-617">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-618">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-619">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cdc26-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cdc26-620">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="cdc26-621">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="cdc26-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="cdc26-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="cdc26-622">**mvc, razor**</span></span>

<span data-ttu-id="cdc26-623">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cdc26-624">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="cdc26-624">The possible values are:</span></span>

- <span data-ttu-id="cdc26-625">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="cdc26-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cdc26-626">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="cdc26-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="cdc26-627">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cdc26-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cdc26-628">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="cdc26-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cdc26-629">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="cdc26-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="cdc26-630">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="cdc26-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cdc26-631">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cdc26-632">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-633">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cdc26-634">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cdc26-635">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-636">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="cdc26-637">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-638">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="cdc26-639">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-640">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cdc26-641">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="cdc26-642">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cdc26-643">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cdc26-644">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="cdc26-645">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cdc26-646">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cdc26-647">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-648">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cdc26-649">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cdc26-650">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-651">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cdc26-652">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="cdc26-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="cdc26-653">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-654">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="cdc26-655">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cdc26-656">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cdc26-657">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="cdc26-658">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="cdc26-659">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="cdc26-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cdc26-660">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-661">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-662">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cdc26-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="cdc26-663">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="cdc26-664">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="cdc26-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="cdc26-665">**page**</span><span class="sxs-lookup"><span data-stu-id="cdc26-665">**page**</span></span>

<span data-ttu-id="cdc26-666">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="cdc26-667">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="cdc26-668">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="cdc26-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="cdc26-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="cdc26-669">**viewimports**</span></span>

<span data-ttu-id="cdc26-670">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="cdc26-671">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="cdc26-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="cdc26-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="cdc26-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="cdc26-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="cdc26-674">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="cdc26-675">**classlib**</span></span>

<span data-ttu-id="cdc26-676">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cdc26-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cdc26-677">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="cdc26-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="cdc26-678">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="cdc26-679">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="cdc26-680">**mstest, xunit**</span></span>

<span data-ttu-id="cdc26-681">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="cdc26-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="cdc26-682">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="cdc26-683">**globaljson**</span></span>

<span data-ttu-id="cdc26-684">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="cdc26-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="cdc26-685">**web**</span><span class="sxs-lookup"><span data-stu-id="cdc26-685">**web**</span></span>

<span data-ttu-id="cdc26-686">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="cdc26-687">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="cdc26-688">**webapi**</span></span>

<span data-ttu-id="cdc26-689">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cdc26-690">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="cdc26-690">The possible values are:</span></span>

- <span data-ttu-id="cdc26-691">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="cdc26-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cdc26-692">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cdc26-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cdc26-693">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="cdc26-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cdc26-694">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="cdc26-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cdc26-695">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cdc26-696">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-697">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cdc26-698">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cdc26-699">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-700">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cdc26-701">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-702">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cdc26-703">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cdc26-704">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-705">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cdc26-706">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cdc26-707">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-708">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cdc26-709">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cdc26-710">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-711">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cdc26-712">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cdc26-713">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cdc26-714">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="cdc26-715">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="cdc26-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cdc26-716">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-717">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="cdc26-718">**mvc, razor**</span></span>

<span data-ttu-id="cdc26-719">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cdc26-720">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="cdc26-720">The possible values are:</span></span>

- <span data-ttu-id="cdc26-721">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="cdc26-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="cdc26-722">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="cdc26-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="cdc26-723">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="cdc26-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="cdc26-724">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="cdc26-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="cdc26-725">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="cdc26-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="cdc26-726">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="cdc26-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="cdc26-727">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="cdc26-728">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-729">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="cdc26-730">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="cdc26-731">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-732">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="cdc26-733">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-734">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="cdc26-735">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-736">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="cdc26-737">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="cdc26-738">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="cdc26-739">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="cdc26-740">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="cdc26-741">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="cdc26-742">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="cdc26-743">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-744">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="cdc26-745">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="cdc26-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="cdc26-746">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="cdc26-747">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="cdc26-748">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="cdc26-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="cdc26-749">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="cdc26-750">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="cdc26-751">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="cdc26-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="cdc26-752">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="cdc26-753">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="cdc26-754">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="cdc26-755">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="cdc26-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="cdc26-756">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="cdc26-757">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cdc26-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="cdc26-758">**page**</span><span class="sxs-lookup"><span data-stu-id="cdc26-758">**page**</span></span>

<span data-ttu-id="cdc26-759">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="cdc26-760">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="cdc26-761">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="cdc26-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="cdc26-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="cdc26-762">**viewimports**</span></span>

<span data-ttu-id="cdc26-763">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="cdc26-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="cdc26-764">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="cdc26-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="cdc26-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="cdc26-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="cdc26-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="cdc26-767">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cdc26-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cdc26-768">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="cdc26-769">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="cdc26-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="cdc26-770">**classlib**</span></span>

<span data-ttu-id="cdc26-771">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cdc26-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cdc26-772">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="cdc26-773">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="cdc26-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="cdc26-774">**mvc**</span></span>

<span data-ttu-id="cdc26-775">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="cdc26-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="cdc26-776">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="cdc26-777">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="cdc26-778">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="cdc26-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="cdc26-779">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="cdc26-780">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-780">The default value is `None`.</span></span>

<span data-ttu-id="cdc26-781">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="cdc26-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="cdc26-782">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-782">Values: `true` or `false`.</span></span> <span data-ttu-id="cdc26-783">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="cdc26-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="cdc26-784">Esempi</span><span class="sxs-lookup"><span data-stu-id="cdc26-784">Examples</span></span>

<span data-ttu-id="cdc26-785">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="cdc26-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="cdc26-786">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="cdc26-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="cdc26-787">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="cdc26-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="cdc26-788">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="cdc26-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="cdc26-789">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="cdc26-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="cdc26-790">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="cdc26-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="cdc26-791">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="cdc26-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="cdc26-792">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="cdc26-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="cdc26-793">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="cdc26-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="cdc26-794">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="cdc26-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="cdc26-795">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="cdc26-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="cdc26-796">Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):</span><span class="sxs-lookup"><span data-stu-id="cdc26-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="cdc26-797">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cdc26-797">See also</span></span>

- [<span data-ttu-id="cdc26-798">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="cdc26-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="cdc26-799">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="cdc26-799">Create a custom template for dotnet new</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="cdc26-800">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="cdc26-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="cdc26-801">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="cdc26-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
