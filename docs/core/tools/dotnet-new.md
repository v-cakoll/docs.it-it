---
title: Comando dotnet new
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
ms.date: 05/06/2019
ms.openlocfilehash: c9e960bab0e28e88b0cc8d431dad3b9f3f00c9c0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69660546"
---
# <a name="dotnet-new"></a><span data-ttu-id="a9c8f-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="a9c8f-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a9c8f-104">nome</span><span class="sxs-lookup"><span data-stu-id="a9c8f-104">Name</span></span>

<span data-ttu-id="a9c8f-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a9c8f-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="a9c8f-106">Synopsis</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="a9c8f-107">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a9c8f-107">.NET Core 2.2</span></span>](#tab/netcore22)

```console
dotnet new <TEMPLATE> [--dry-run] [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a9c8f-108">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a9c8f-108">.NET Core 2.1</span></span>](#tab/netcore21)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [--nuget-source] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a9c8f-109">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a9c8f-109">.NET Core 2.0</span></span>](#tab/netcore20)

```console
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a9c8f-110">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a9c8f-110">.NET Core 1.x</span></span>](#tab/netcore1x)

```console
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="a9c8f-111">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="a9c8f-111">Description</span></span>

<span data-ttu-id="a9c8f-112">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-112">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="a9c8f-113">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-113">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="a9c8f-114">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a9c8f-114">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="a9c8f-115">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-115">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="a9c8f-116">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-116">Each template might have specific options you can pass.</span></span> <span data-ttu-id="a9c8f-117">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-117">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="a9c8f-118">Se il valore di `TEMPLATE` non è una corrispondenza esatta del testo nella colonna **Modelli** o **Nome breve** viene eseguita una corrispondenza sottostringa in queste due colonne.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-118">If the `TEMPLATE` value isn't an exact match on text in the **Templates** or **Short Name** column, a substring match is performed on those two columns.</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="a9c8f-119">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a9c8f-119">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="a9c8f-120">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-120">The command contains a default list of templates.</span></span> <span data-ttu-id="a9c8f-121">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-121">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="a9c8f-122">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.2.100.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-122">The following table shows the templates that come pre-installed with the .NET Core SDK 2.2.100.</span></span> <span data-ttu-id="a9c8f-123">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-123">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="a9c8f-124">Modelli</span><span class="sxs-lookup"><span data-stu-id="a9c8f-124">Templates</span></span>                                    | <span data-ttu-id="a9c8f-125">Nome breve</span><span class="sxs-lookup"><span data-stu-id="a9c8f-125">Short Name</span></span>        | <span data-ttu-id="a9c8f-126">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="a9c8f-126">Language</span></span>     | <span data-ttu-id="a9c8f-127">Tag</span><span class="sxs-lookup"><span data-stu-id="a9c8f-127">Tags</span></span>                                  |
|----------------------------------------------|-------------------|--------------|---------------------------------------|
| <span data-ttu-id="a9c8f-128">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="a9c8f-128">Console Application</span></span>                          | `console`         | <span data-ttu-id="a9c8f-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-129">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-130">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="a9c8f-130">Common/Console</span></span>                        |
| <span data-ttu-id="a9c8f-131">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="a9c8f-131">Class library</span></span>                                | `classlib`        | <span data-ttu-id="a9c8f-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-132">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-133">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="a9c8f-133">Common/Library</span></span>                        |
| <span data-ttu-id="a9c8f-134">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="a9c8f-134">Unit Test Project</span></span>                            | `mstest`          | <span data-ttu-id="a9c8f-135">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-135">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-136">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="a9c8f-136">Test/MSTest</span></span>                           |
| <span data-ttu-id="a9c8f-137">Progetto di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="a9c8f-137">NUnit 3 Test Project</span></span>                         | `nunit`           | <span data-ttu-id="a9c8f-138">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-138">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-139">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="a9c8f-139">Test/NUnit</span></span>                            |
| <span data-ttu-id="a9c8f-140">Elemento di test NUnit 3</span><span class="sxs-lookup"><span data-stu-id="a9c8f-140">NUnit 3 Test Item</span></span>                            | `nunit-test`      | <span data-ttu-id="a9c8f-141">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-141">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-142">Test/NUnit</span><span class="sxs-lookup"><span data-stu-id="a9c8f-142">Test/NUnit</span></span>                            |
| <span data-ttu-id="a9c8f-143">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="a9c8f-143">xUnit Test Project</span></span>                           | `xunit`           | <span data-ttu-id="a9c8f-144">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-144">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-145">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="a9c8f-145">Test/xUnit</span></span>                            |
| <span data-ttu-id="a9c8f-146">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="a9c8f-146">Razor Page</span></span>                                   | `page`            | <span data-ttu-id="a9c8f-147">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-147">[C#]</span></span>         | <span data-ttu-id="a9c8f-148">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9c8f-148">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="a9c8f-149">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="a9c8f-149">MVC ViewImports</span></span>                              | `viewimports`     | <span data-ttu-id="a9c8f-150">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-150">[C#]</span></span>         | <span data-ttu-id="a9c8f-151">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9c8f-151">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="a9c8f-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="a9c8f-152">MVC ViewStart</span></span>                                | `viewstart`       | <span data-ttu-id="a9c8f-153">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-153">[C#]</span></span>         | <span data-ttu-id="a9c8f-154">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9c8f-154">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="a9c8f-155">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="a9c8f-155">ASP.NET Core Empty</span></span>                           | `web`             | <span data-ttu-id="a9c8f-156">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-156">[C#], F#</span></span>     | <span data-ttu-id="a9c8f-157">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="a9c8f-157">Web/Empty</span></span>                             |
| <span data-ttu-id="a9c8f-158">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="a9c8f-158">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`             | <span data-ttu-id="a9c8f-159">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-159">[C#], F#</span></span>     | <span data-ttu-id="a9c8f-160">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="a9c8f-160">Web/MVC</span></span>                               |
| <span data-ttu-id="a9c8f-161">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a9c8f-161">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="a9c8f-162">`webapp`, `razor`</span><span class="sxs-lookup"><span data-stu-id="a9c8f-162">`webapp`, `razor`</span></span> | <span data-ttu-id="a9c8f-163">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-163">[C#]</span></span>         | <span data-ttu-id="a9c8f-164">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="a9c8f-164">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="a9c8f-165">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="a9c8f-165">ASP.NET Core with Angular</span></span>                    | `angular`         | <span data-ttu-id="a9c8f-166">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-166">[C#]</span></span>         | <span data-ttu-id="a9c8f-167">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a9c8f-167">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="a9c8f-168">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="a9c8f-168">ASP.NET Core with React.js</span></span>                   | `react`           | <span data-ttu-id="a9c8f-169">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-169">[C#]</span></span>         | <span data-ttu-id="a9c8f-170">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a9c8f-170">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="a9c8f-171">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="a9c8f-171">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`      | <span data-ttu-id="a9c8f-172">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-172">[C#]</span></span>         | <span data-ttu-id="a9c8f-173">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a9c8f-173">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="a9c8f-174">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="a9c8f-174">Razor Class Library</span></span>                          | `razorclasslib`   | <span data-ttu-id="a9c8f-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-175">[C#]</span></span>         | <span data-ttu-id="a9c8f-176">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="a9c8f-176">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="a9c8f-177">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a9c8f-177">ASP.NET Core Web API</span></span>                         | `webapi`          | <span data-ttu-id="a9c8f-178">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-178">[C#], F#</span></span>     | <span data-ttu-id="a9c8f-179">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="a9c8f-179">Web/WebAPI</span></span>                            |
| <span data-ttu-id="a9c8f-180">File global.json</span><span class="sxs-lookup"><span data-stu-id="a9c8f-180">global.json file</span></span>                             | `globaljson`      |              | <span data-ttu-id="a9c8f-181">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-181">Config</span></span>                                |
| <span data-ttu-id="a9c8f-182">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="a9c8f-182">NuGet Config</span></span>                                 | `nugetconfig`     |              | <span data-ttu-id="a9c8f-183">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-183">Config</span></span>                                |
| <span data-ttu-id="a9c8f-184">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="a9c8f-184">Web Config</span></span>                                   | `webconfig`       |              | <span data-ttu-id="a9c8f-185">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-185">Config</span></span>                                |
| <span data-ttu-id="a9c8f-186">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="a9c8f-186">Solution File</span></span>                                | `sln`             |              | <span data-ttu-id="a9c8f-187">Soluzione</span><span class="sxs-lookup"><span data-stu-id="a9c8f-187">Solution</span></span>                              |

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a9c8f-188">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a9c8f-188">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="a9c8f-189">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-189">The command contains a default list of templates.</span></span> <span data-ttu-id="a9c8f-190">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-190">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="a9c8f-191">La tabella seguente descrive i modelli preinstallati con .NET Core SDK 2.1.300.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-191">The following table shows the templates that come pre-installed with the .NET Core SDK 2.1.300.</span></span> <span data-ttu-id="a9c8f-192">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-192">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="a9c8f-193">Modelli</span><span class="sxs-lookup"><span data-stu-id="a9c8f-193">Templates</span></span>                                    | <span data-ttu-id="a9c8f-194">Nome breve</span><span class="sxs-lookup"><span data-stu-id="a9c8f-194">Short Name</span></span>      | <span data-ttu-id="a9c8f-195">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="a9c8f-195">Language</span></span>     | <span data-ttu-id="a9c8f-196">Tag</span><span class="sxs-lookup"><span data-stu-id="a9c8f-196">Tags</span></span>                                  |
|----------------------------------------------|-----------------|--------------|---------------------------------------|
| <span data-ttu-id="a9c8f-197">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="a9c8f-197">Console Application</span></span>                          | `console`       | <span data-ttu-id="a9c8f-198">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-198">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-199">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="a9c8f-199">Common/Console</span></span>                        |
| <span data-ttu-id="a9c8f-200">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="a9c8f-200">Class library</span></span>                                | `classlib`      | <span data-ttu-id="a9c8f-201">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-201">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-202">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="a9c8f-202">Common/Library</span></span>                        |
| <span data-ttu-id="a9c8f-203">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="a9c8f-203">Unit Test Project</span></span>                            | `mstest`        | <span data-ttu-id="a9c8f-204">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-204">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-205">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="a9c8f-205">Test/MSTest</span></span>                           |
| <span data-ttu-id="a9c8f-206">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="a9c8f-206">xUnit Test Project</span></span>                           | `xunit`         | <span data-ttu-id="a9c8f-207">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-207">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-208">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="a9c8f-208">Test/xUnit</span></span>                            |
| <span data-ttu-id="a9c8f-209">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="a9c8f-209">Razor Page</span></span>                                   | `page`          | <span data-ttu-id="a9c8f-210">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-210">[C#]</span></span>         | <span data-ttu-id="a9c8f-211">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9c8f-211">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="a9c8f-212">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="a9c8f-212">MVC ViewImports</span></span>                              | `viewimports`   | <span data-ttu-id="a9c8f-213">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-213">[C#]</span></span>         | <span data-ttu-id="a9c8f-214">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9c8f-214">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="a9c8f-215">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="a9c8f-215">MVC ViewStart</span></span>                                | `viewstart`     | <span data-ttu-id="a9c8f-216">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-216">[C#]</span></span>         | <span data-ttu-id="a9c8f-217">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9c8f-217">Web/ASP.NET</span></span>                           |
| <span data-ttu-id="a9c8f-218">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="a9c8f-218">ASP.NET Core Empty</span></span>                           | `web`           | <span data-ttu-id="a9c8f-219">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-219">[C#], F#</span></span>     | <span data-ttu-id="a9c8f-220">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="a9c8f-220">Web/Empty</span></span>                             |
| <span data-ttu-id="a9c8f-221">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="a9c8f-221">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`           | <span data-ttu-id="a9c8f-222">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-222">[C#], F#</span></span>     | <span data-ttu-id="a9c8f-223">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="a9c8f-223">Web/MVC</span></span>                               |
| <span data-ttu-id="a9c8f-224">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a9c8f-224">ASP.NET Core Web App</span></span>                         | `razor`         | <span data-ttu-id="a9c8f-225">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-225">[C#]</span></span>         | <span data-ttu-id="a9c8f-226">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="a9c8f-226">Web/MVC/Razor Pages</span></span>                   |
| <span data-ttu-id="a9c8f-227">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="a9c8f-227">ASP.NET Core with Angular</span></span>                    | `angular`       | <span data-ttu-id="a9c8f-228">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-228">[C#]</span></span>         | <span data-ttu-id="a9c8f-229">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a9c8f-229">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="a9c8f-230">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="a9c8f-230">ASP.NET Core with React.js</span></span>                   | `react`         | <span data-ttu-id="a9c8f-231">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-231">[C#]</span></span>         | <span data-ttu-id="a9c8f-232">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a9c8f-232">Web/MVC/SPA</span></span>                           |
| <span data-ttu-id="a9c8f-233">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="a9c8f-233">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`    | <span data-ttu-id="a9c8f-234">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-234">[C#]</span></span>         | <span data-ttu-id="a9c8f-235">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a9c8f-235">Web/MVC/SPA</span></span>                           | 
| <span data-ttu-id="a9c8f-236">Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="a9c8f-236">Razor Class Library</span></span>                          | `razorclasslib` | <span data-ttu-id="a9c8f-237">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-237">[C#]</span></span>         | <span data-ttu-id="a9c8f-238">Web/Razor/Libreria/Libreria di classi Razor</span><span class="sxs-lookup"><span data-stu-id="a9c8f-238">Web/Razor/Library/Razor Class Library</span></span> |
| <span data-ttu-id="a9c8f-239">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a9c8f-239">ASP.NET Core Web API</span></span>                         | `webapi`        | <span data-ttu-id="a9c8f-240">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-240">[C#], F#</span></span>     | <span data-ttu-id="a9c8f-241">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="a9c8f-241">Web/WebAPI</span></span>                            |
| <span data-ttu-id="a9c8f-242">File global.json</span><span class="sxs-lookup"><span data-stu-id="a9c8f-242">global.json file</span></span>                             | `globaljson`    |              | <span data-ttu-id="a9c8f-243">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-243">Config</span></span>                                |
| <span data-ttu-id="a9c8f-244">Configurazione NuGet</span><span class="sxs-lookup"><span data-stu-id="a9c8f-244">NuGet Config</span></span>                                 | `nugetconfig`   |              | <span data-ttu-id="a9c8f-245">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-245">Config</span></span>                                |
| <span data-ttu-id="a9c8f-246">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="a9c8f-246">Web Config</span></span>                                   | `webconfig`     |              | <span data-ttu-id="a9c8f-247">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-247">Config</span></span>                                |
| <span data-ttu-id="a9c8f-248">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="a9c8f-248">Solution File</span></span>                                | `sln`           |              | <span data-ttu-id="a9c8f-249">Soluzione</span><span class="sxs-lookup"><span data-stu-id="a9c8f-249">Solution</span></span>                              |

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a9c8f-250">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a9c8f-250">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="a9c8f-251">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-251">The command contains a default list of templates.</span></span> <span data-ttu-id="a9c8f-252">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-252">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="a9c8f-253">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 2.0.0.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-253">The following table shows the templates that come pre-installed with the .NET Core SDK 2.0.0.</span></span> <span data-ttu-id="a9c8f-254">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-254">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="a9c8f-255">Modelli</span><span class="sxs-lookup"><span data-stu-id="a9c8f-255">Templates</span></span>                                    | <span data-ttu-id="a9c8f-256">Nome breve</span><span class="sxs-lookup"><span data-stu-id="a9c8f-256">Short Name</span></span>    | <span data-ttu-id="a9c8f-257">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="a9c8f-257">Language</span></span>     | <span data-ttu-id="a9c8f-258">Tag</span><span class="sxs-lookup"><span data-stu-id="a9c8f-258">Tags</span></span>                |
|----------------------------------------------|---------------|--------------|---------------------|
| <span data-ttu-id="a9c8f-259">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="a9c8f-259">Console Application</span></span>                          | `console`     | <span data-ttu-id="a9c8f-260">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-260">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-261">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="a9c8f-261">Common/Console</span></span>      |
| <span data-ttu-id="a9c8f-262">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="a9c8f-262">Class library</span></span>                                | `classlib`    | <span data-ttu-id="a9c8f-263">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-263">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-264">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="a9c8f-264">Common/Library</span></span>      |
| <span data-ttu-id="a9c8f-265">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="a9c8f-265">Unit Test Project</span></span>                            | `mstest`      | <span data-ttu-id="a9c8f-266">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-266">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-267">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="a9c8f-267">Test/MSTest</span></span>         |
| <span data-ttu-id="a9c8f-268">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="a9c8f-268">xUnit Test Project</span></span>                           | `xunit`       | <span data-ttu-id="a9c8f-269">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="a9c8f-269">[C#], F#, VB</span></span> | <span data-ttu-id="a9c8f-270">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="a9c8f-270">Test/xUnit</span></span>          |
| <span data-ttu-id="a9c8f-271">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="a9c8f-271">ASP.NET Core Empty</span></span>                           | `web`         | <span data-ttu-id="a9c8f-272">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-272">[C#], F#</span></span>     | <span data-ttu-id="a9c8f-273">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="a9c8f-273">Web/Empty</span></span>           |
| <span data-ttu-id="a9c8f-274">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="a9c8f-274">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="a9c8f-275">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-275">[C#], F#</span></span>     | <span data-ttu-id="a9c8f-276">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="a9c8f-276">Web/MVC</span></span>             |
| <span data-ttu-id="a9c8f-277">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a9c8f-277">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="a9c8f-278">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-278">[C#]</span></span>         | <span data-ttu-id="a9c8f-279">Web/MVC/Razor Pages</span><span class="sxs-lookup"><span data-stu-id="a9c8f-279">Web/MVC/Razor Pages</span></span> |
| <span data-ttu-id="a9c8f-280">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="a9c8f-280">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="a9c8f-281">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-281">[C#]</span></span>         | <span data-ttu-id="a9c8f-282">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a9c8f-282">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="a9c8f-283">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="a9c8f-283">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="a9c8f-284">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-284">[C#]</span></span>         | <span data-ttu-id="a9c8f-285">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a9c8f-285">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="a9c8f-286">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="a9c8f-286">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="a9c8f-287">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-287">[C#]</span></span>         | <span data-ttu-id="a9c8f-288">Web/MVC/SPA</span><span class="sxs-lookup"><span data-stu-id="a9c8f-288">Web/MVC/SPA</span></span>         |
| <span data-ttu-id="a9c8f-289">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a9c8f-289">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="a9c8f-290">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-290">[C#], F#</span></span>     | <span data-ttu-id="a9c8f-291">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="a9c8f-291">Web/WebAPI</span></span>          |
| <span data-ttu-id="a9c8f-292">File global.json</span><span class="sxs-lookup"><span data-stu-id="a9c8f-292">global.json file</span></span>                             | `globaljson`  |              | <span data-ttu-id="a9c8f-293">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-293">Config</span></span>              |
| <span data-ttu-id="a9c8f-294">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="a9c8f-294">Nuget Config</span></span>                                 | `nugetconfig` |              | <span data-ttu-id="a9c8f-295">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-295">Config</span></span>              |
| <span data-ttu-id="a9c8f-296">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="a9c8f-296">Web Config</span></span>                                   | `webconfig`   |              | <span data-ttu-id="a9c8f-297">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-297">Config</span></span>              |
| <span data-ttu-id="a9c8f-298">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="a9c8f-298">Solution File</span></span>                                | `sln`         |              | <span data-ttu-id="a9c8f-299">Soluzione</span><span class="sxs-lookup"><span data-stu-id="a9c8f-299">Solution</span></span>            |
| <span data-ttu-id="a9c8f-300">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="a9c8f-300">Razor Page</span></span>                                   | `page`        |              | <span data-ttu-id="a9c8f-301">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9c8f-301">Web/ASP.NET</span></span>         |
| <span data-ttu-id="a9c8f-302">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="a9c8f-302">MVC ViewImports</span></span>                              | `viewimports` |              | <span data-ttu-id="a9c8f-303">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9c8f-303">Web/ASP.NET</span></span>         |
| <span data-ttu-id="a9c8f-304">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="a9c8f-304">MVC ViewStart</span></span>                                | `viewstart`   |              | <span data-ttu-id="a9c8f-305">Web/ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a9c8f-305">Web/ASP.NET</span></span>         |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a9c8f-306">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a9c8f-306">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="a9c8f-307">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-307">The command contains a default list of templates.</span></span> <span data-ttu-id="a9c8f-308">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-308">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="a9c8f-309">La tabella seguente elenca i modelli preinstallati con .NET Core SDK 1.0.1.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-309">The following table shows the templates that come pre-installed with the .NET Core SDK 1.0.1.</span></span> <span data-ttu-id="a9c8f-310">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-310">The default language for the template is shown inside the brackets.</span></span>

| <span data-ttu-id="a9c8f-311">Modelli</span><span class="sxs-lookup"><span data-stu-id="a9c8f-311">Templates</span></span>            | <span data-ttu-id="a9c8f-312">Nome breve</span><span class="sxs-lookup"><span data-stu-id="a9c8f-312">Short Name</span></span>    | <span data-ttu-id="a9c8f-313">Linguaggio</span><span class="sxs-lookup"><span data-stu-id="a9c8f-313">Language</span></span> | <span data-ttu-id="a9c8f-314">Tag</span><span class="sxs-lookup"><span data-stu-id="a9c8f-314">Tags</span></span>           |
|----------------------|---------------|----------|----------------|
| <span data-ttu-id="a9c8f-315">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="a9c8f-315">Console Application</span></span>  | `console`     | <span data-ttu-id="a9c8f-316">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-316">[C#], F#</span></span> | <span data-ttu-id="a9c8f-317">Comune/Console</span><span class="sxs-lookup"><span data-stu-id="a9c8f-317">Common/Console</span></span> |
| <span data-ttu-id="a9c8f-318">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="a9c8f-318">Class library</span></span>        | `classlib`    | <span data-ttu-id="a9c8f-319">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-319">[C#], F#</span></span> | <span data-ttu-id="a9c8f-320">Comune/Library</span><span class="sxs-lookup"><span data-stu-id="a9c8f-320">Common/Library</span></span> |
| <span data-ttu-id="a9c8f-321">Progetto unit test</span><span class="sxs-lookup"><span data-stu-id="a9c8f-321">Unit Test Project</span></span>    | `mstest`      | <span data-ttu-id="a9c8f-322">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-322">[C#], F#</span></span> | <span data-ttu-id="a9c8f-323">Test/MSTest</span><span class="sxs-lookup"><span data-stu-id="a9c8f-323">Test/MSTest</span></span>    |
| <span data-ttu-id="a9c8f-324">Progetto di test xUnit</span><span class="sxs-lookup"><span data-stu-id="a9c8f-324">xUnit Test Project</span></span>   | `xunit`       | <span data-ttu-id="a9c8f-325">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-325">[C#], F#</span></span> | <span data-ttu-id="a9c8f-326">Test/xUnit</span><span class="sxs-lookup"><span data-stu-id="a9c8f-326">Test/xUnit</span></span>     |
| <span data-ttu-id="a9c8f-327">Progetto ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="a9c8f-327">ASP.NET Core Empty</span></span>   | `web`         | <span data-ttu-id="a9c8f-328">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-328">[C#]</span></span>     | <span data-ttu-id="a9c8f-329">Web/Vuoto</span><span class="sxs-lookup"><span data-stu-id="a9c8f-329">Web/Empty</span></span>      |
| <span data-ttu-id="a9c8f-330">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a9c8f-330">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="a9c8f-331">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="a9c8f-331">[C#], F#</span></span> | <span data-ttu-id="a9c8f-332">Web/MVC</span><span class="sxs-lookup"><span data-stu-id="a9c8f-332">Web/MVC</span></span>        |
| <span data-ttu-id="a9c8f-333">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="a9c8f-333">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="a9c8f-334">[C#]</span><span class="sxs-lookup"><span data-stu-id="a9c8f-334">[C#]</span></span>     | <span data-ttu-id="a9c8f-335">Web/WebAPI</span><span class="sxs-lookup"><span data-stu-id="a9c8f-335">Web/WebAPI</span></span>     |
| <span data-ttu-id="a9c8f-336">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="a9c8f-336">Nuget Config</span></span>         | `nugetconfig` |          | <span data-ttu-id="a9c8f-337">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-337">Config</span></span>         |
| <span data-ttu-id="a9c8f-338">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="a9c8f-338">Web Config</span></span>           | `webconfig`   |          | <span data-ttu-id="a9c8f-339">Config</span><span class="sxs-lookup"><span data-stu-id="a9c8f-339">Config</span></span>         |
| <span data-ttu-id="a9c8f-340">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="a9c8f-340">Solution File</span></span>        | `sln`         |          | <span data-ttu-id="a9c8f-341">Soluzione</span><span class="sxs-lookup"><span data-stu-id="a9c8f-341">Solution</span></span>       |

---

## <a name="options"></a><span data-ttu-id="a9c8f-342">Opzioni</span><span class="sxs-lookup"><span data-stu-id="a9c8f-342">Options</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="a9c8f-343">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a9c8f-343">.NET Core 2.2</span></span>](#tab/netcore22)

`--dry-run`

<span data-ttu-id="a9c8f-344">Visualizza un riepilogo di cosa accadrebbe se venisse eseguito il comando specificato e se venisse creato un modello.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-344">Displays a summary of what would happen if the given command were run if it would result in a template creation.</span></span>

`--force`

<span data-ttu-id="a9c8f-345">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-345">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="a9c8f-346">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-346">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="a9c8f-347">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-347">Prints out help for the command.</span></span> <span data-ttu-id="a9c8f-348">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-348">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="a9c8f-349">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-349">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="a9c8f-350">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-350">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="a9c8f-351">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-351">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="a9c8f-352">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-352">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="a9c8f-353">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-353">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="a9c8f-354">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-354">Lists templates containing the specified name.</span></span> <span data-ttu-id="a9c8f-355">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-355">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="a9c8f-356">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-356">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="a9c8f-357">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-357">The language of the template to create.</span></span> <span data-ttu-id="a9c8f-358">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-358">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="a9c8f-359">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-359">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="a9c8f-360">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-360">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="a9c8f-361">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-361">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="a9c8f-362">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-362">The name for the created output.</span></span> <span data-ttu-id="a9c8f-363">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-363">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="a9c8f-364">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-364">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="a9c8f-365">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-365">Location to place the generated output.</span></span> <span data-ttu-id="a9c8f-366">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-366">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="a9c8f-367">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-367">Filters templates based on available types.</span></span> <span data-ttu-id="a9c8f-368">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="a9c8f-368">Predefined values are "project", "item", or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="a9c8f-369">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-369">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="a9c8f-370">Quando si esclude il valore di `<PATH|NUGET_ID>` vengono visualizzati tutti i pacchetti di modelli attualmente installati e i relativi modelli associati.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-370">When excluding the `<PATH|NUGET_ID>` value, all currently installed template packs and their associated templates are displayed.</span></span>

> [!NOTE]
> <span data-ttu-id="a9c8f-371">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-371">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="a9c8f-372">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-372">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="a9c8f-373">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-373">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a9c8f-374">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a9c8f-374">.NET Core 2.1</span></span>](#tab/netcore21)

`--force`

<span data-ttu-id="a9c8f-375">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-375">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="a9c8f-376">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-376">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="a9c8f-377">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-377">Prints out help for the command.</span></span> <span data-ttu-id="a9c8f-378">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-378">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="a9c8f-379">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-379">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="a9c8f-380">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-380">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="a9c8f-381">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-381">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="a9c8f-382">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-382">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="a9c8f-383">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-383">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="a9c8f-384">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-384">Lists templates containing the specified name.</span></span> <span data-ttu-id="a9c8f-385">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-385">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="a9c8f-386">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-386">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="a9c8f-387">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-387">The language of the template to create.</span></span> <span data-ttu-id="a9c8f-388">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-388">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="a9c8f-389">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-389">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="a9c8f-390">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-390">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="a9c8f-391">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-391">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="a9c8f-392">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-392">The name for the created output.</span></span> <span data-ttu-id="a9c8f-393">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-393">If no name is specified, the name of the current directory is used.</span></span>

`--nuget-source`

<span data-ttu-id="a9c8f-394">Specifica un'origine NuGet da usare durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-394">Specifies a NuGet source to use during install.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="a9c8f-395">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-395">Location to place the generated output.</span></span> <span data-ttu-id="a9c8f-396">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-396">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="a9c8f-397">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-397">Filters templates based on available types.</span></span> <span data-ttu-id="a9c8f-398">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="a9c8f-398">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="a9c8f-399">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-399">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="a9c8f-400">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-400">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="a9c8f-401">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-401">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="a9c8f-402">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-402">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a9c8f-403">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a9c8f-403">.NET Core 2.0</span></span>](#tab/netcore20)

`--force`

<span data-ttu-id="a9c8f-404">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-404">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="a9c8f-405">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-405">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="a9c8f-406">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-406">Prints out help for the command.</span></span> <span data-ttu-id="a9c8f-407">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-407">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="a9c8f-408">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-408">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="a9c8f-409">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-409">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="a9c8f-410">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-410">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="a9c8f-411">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-411">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="a9c8f-412">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-412">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="a9c8f-413">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-413">Lists templates containing the specified name.</span></span> <span data-ttu-id="a9c8f-414">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-414">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="a9c8f-415">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-415">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="a9c8f-416">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-416">The language of the template to create.</span></span> <span data-ttu-id="a9c8f-417">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-417">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="a9c8f-418">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-418">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="a9c8f-419">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-419">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="a9c8f-420">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-420">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="a9c8f-421">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-421">The name for the created output.</span></span> <span data-ttu-id="a9c8f-422">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-422">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="a9c8f-423">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-423">Location to place the generated output.</span></span> <span data-ttu-id="a9c8f-424">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-424">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="a9c8f-425">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-425">Filters templates based on available types.</span></span> <span data-ttu-id="a9c8f-426">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="a9c8f-426">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="a9c8f-427">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-427">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="a9c8f-428">Per disinstallare un modello con un valore `PATH` di origine, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-428">To uninstall a template using a source `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="a9c8f-429">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-429">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span> <span data-ttu-id="a9c8f-430">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-430">Additionally, do not include a final terminating directory slash on your template path.</span></span>
> 
> <span data-ttu-id="a9c8f-431">Se non è possibile determinare l'argomento `PATH` o `NUGET_ID` necessario per disinstallare un modello, eseguendo `dotnet new --uninstall` senza un argomento, verranno elencati tutti i modelli installati e l'argomento necessario per disinstallarli.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-431">If you are unable to determine the `PATH` or `NUGET_ID` argument needed to uninstall a template, running `dotnet new --uninstall` without an argument will list all installed templates and the argument required to uninstall them.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a9c8f-432">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a9c8f-432">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="a9c8f-433">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-433">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="a9c8f-434">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-434">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="a9c8f-435">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-435">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="a9c8f-436">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-436">Prints out help for the command.</span></span> <span data-ttu-id="a9c8f-437">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-437">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="a9c8f-438">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-438">Lists templates containing the specified name.</span></span> <span data-ttu-id="a9c8f-439">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-439">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="a9c8f-440">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-440">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="a9c8f-441">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-441">The language of the template to create.</span></span> <span data-ttu-id="a9c8f-442">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-442">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="a9c8f-443">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-443">Not valid for some templates.</span></span>

> [!NOTE]
> <span data-ttu-id="a9c8f-444">Alcune shell interpretano `#` come un carattere speciale.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-444">Some shells interpret `#` as a special character.</span></span> <span data-ttu-id="a9c8f-445">In questi casi, è necessario racchiudere il valore del parametro relativo al linguaggio, ad esempio `dotnet new console -lang "F#"`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-445">In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="a9c8f-446">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-446">The name for the created output.</span></span> <span data-ttu-id="a9c8f-447">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-447">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="a9c8f-448">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-448">Location to place the generated output.</span></span> <span data-ttu-id="a9c8f-449">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-449">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="a9c8f-450">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="a9c8f-450">Template options</span></span>

<span data-ttu-id="a9c8f-451">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-451">Each project template may have additional options available.</span></span> <span data-ttu-id="a9c8f-452">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-452">The core templates have the following additional options:</span></span>

# <a name="net-core-22tabnetcore22"></a>[<span data-ttu-id="a9c8f-453">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a9c8f-453">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="a9c8f-454">**console**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-454">**console**</span></span>

<span data-ttu-id="a9c8f-455">`--langVersion <VERSION_NUMBER>`: imposta la proprietà `LangVersion` nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-455">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="a9c8f-456">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-456">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="a9c8f-457">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-457">Not supported for F#.</span></span>

<span data-ttu-id="a9c8f-458">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-458">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-459">**angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-459">**angular, react, reactredux**</span></span>

<span data-ttu-id="a9c8f-460">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-460">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="a9c8f-461">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-461">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-462">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-462">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="a9c8f-463">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-463">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="a9c8f-464">**razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-464">**razorclasslib**</span></span>

<span data-ttu-id="a9c8f-465">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-465">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-466">**classlib**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-466">**classlib**</span></span>

<span data-ttu-id="a9c8f-467">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-467">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a9c8f-468">Valori: `netcoreapp2.2` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-468">Values: `netcoreapp2.2` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="a9c8f-469">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-469">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="a9c8f-470">`--langVersion <VERSION_NUMBER>`: imposta la proprietà `LangVersion` nel file di progetto creato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-470">`--langVersion <VERSION_NUMBER>` - Sets the `LangVersion` property in the created project file.</span></span> <span data-ttu-id="a9c8f-471">Ad esempio, usare `--langVersion 7.3` per usare C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-471">For example, use `--langVersion 7.3` to use C# 7.3.</span></span> <span data-ttu-id="a9c8f-472">Non supportata per F#.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-472">Not supported for F#.</span></span>

<span data-ttu-id="a9c8f-473">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-473">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-474">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-474">**mstest, xunit**</span></span>

<span data-ttu-id="a9c8f-475">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-475">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="a9c8f-476">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-476">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-477">**nunit**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-477">**nunit**</span></span>

<span data-ttu-id="a9c8f-478">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-478">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a9c8f-479">Il valore predefinito è `netcoreapp2.1`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-479">The default value is `netcoreapp2.1`.</span></span>

<span data-ttu-id="a9c8f-480">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-480">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="a9c8f-481">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-481">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-482">**page**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-482">**page**</span></span>

<span data-ttu-id="a9c8f-483">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-483">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="a9c8f-484">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-484">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="a9c8f-485">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-485">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="a9c8f-486">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-486">**viewimports**</span></span>

<span data-ttu-id="a9c8f-487">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-487">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="a9c8f-488">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-488">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="a9c8f-489">**web**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-489">**web**</span></span>

<span data-ttu-id="a9c8f-490">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-490">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="a9c8f-491">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-491">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-492">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-492">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="a9c8f-493">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-493">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="a9c8f-494">**mvc, webapp**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-494">**mvc, webapp**</span></span>

<span data-ttu-id="a9c8f-495">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-495">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="a9c8f-496">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-496">The possible values are:</span></span>

- <span data-ttu-id="a9c8f-497">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-497">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="a9c8f-498">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-498">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="a9c8f-499">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-499">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="a9c8f-500">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-500">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="a9c8f-501">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-501">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="a9c8f-502">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-502">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="a9c8f-503">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-503">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a9c8f-504">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-504">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-505">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-505">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="a9c8f-506">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-506">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a9c8f-507">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-507">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-508">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-508">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="a9c8f-509">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-509">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-510">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-510">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="a9c8f-511">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-511">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-512">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-512">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a9c8f-513">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-513">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="a9c8f-514">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-514">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="a9c8f-515">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-515">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="a9c8f-516">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-516">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="a9c8f-517">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-517">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="a9c8f-518">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-518">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="a9c8f-519">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-519">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-520">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-520">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="a9c8f-521">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-521">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a9c8f-522">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-522">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-523">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-523">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="a9c8f-524">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-524">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="a9c8f-525">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-525">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-526">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-526">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="a9c8f-527">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-527">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="a9c8f-528">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-528">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="a9c8f-529">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-529">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="a9c8f-530">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-530">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="a9c8f-531">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-531">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="a9c8f-532">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-532">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="a9c8f-533">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-533">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a9c8f-534">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-534">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-535">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-535">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-536">**webapi**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-536">**webapi**</span></span>

<span data-ttu-id="a9c8f-537">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-537">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="a9c8f-538">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-538">The possible values are:</span></span>

- <span data-ttu-id="a9c8f-539">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-539">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="a9c8f-540">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-540">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="a9c8f-541">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-541">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="a9c8f-542">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-542">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="a9c8f-543">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-543">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a9c8f-544">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-544">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-545">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-545">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="a9c8f-546">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-546">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a9c8f-547">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-547">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-548">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-548">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a9c8f-549">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-549">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-550">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-550">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="a9c8f-551">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-551">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="a9c8f-552">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-552">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-553">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-553">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="a9c8f-554">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-554">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="a9c8f-555">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-555">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-556">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-556">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="a9c8f-557">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-557">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a9c8f-558">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-558">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-559">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-559">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="a9c8f-560">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-560">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="a9c8f-561">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-561">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="a9c8f-562">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-562">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="a9c8f-563">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-563">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="a9c8f-564">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-564">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="a9c8f-565">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-565">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="a9c8f-566">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-566">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a9c8f-567">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-567">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-568">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-568">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-569">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-569">**globaljson**</span></span>

<span data-ttu-id="a9c8f-570">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-570">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="a9c8f-571">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a9c8f-571">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="a9c8f-572">**console, angular, react, reactredux, razorclasslib**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-572">**console, angular, react, reactredux, razorclasslib**</span></span>

<span data-ttu-id="a9c8f-573">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-573">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-574">**classlib**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-574">**classlib**</span></span>

<span data-ttu-id="a9c8f-575">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-575">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a9c8f-576">Valori: `netcoreapp2.1` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-576">Values: `netcoreapp2.1` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="a9c8f-577">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-577">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="a9c8f-578">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-578">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-579">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-579">**mstest, xunit**</span></span>

<span data-ttu-id="a9c8f-580">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-580">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="a9c8f-581">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-581">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-582">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-582">**globaljson**</span></span>

<span data-ttu-id="a9c8f-583">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-583">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="a9c8f-584">**web**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-584">**web**</span></span>

<span data-ttu-id="a9c8f-585">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-585">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="a9c8f-586">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-586">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-587">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-587">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="a9c8f-588">Questa opzione si applica solo se `IndividualAuth` o `OrganizationalAuth` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-588">This option only applies if `IndividualAuth` or `OrganizationalAuth` are not being used.</span></span>

<span data-ttu-id="a9c8f-589">**webapi**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-589">**webapi**</span></span>

<span data-ttu-id="a9c8f-590">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-590">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="a9c8f-591">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-591">The possible values are:</span></span>

- <span data-ttu-id="a9c8f-592">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-592">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="a9c8f-593">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-593">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="a9c8f-594">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-594">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="a9c8f-595">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-595">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="a9c8f-596">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-596">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a9c8f-597">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-597">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-598">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-598">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="a9c8f-599">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-599">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a9c8f-600">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-600">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-601">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-601">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a9c8f-602">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-602">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-603">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-603">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="a9c8f-604">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-604">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="a9c8f-605">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-605">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-606">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-606">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="a9c8f-607">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-607">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="a9c8f-608">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-608">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-609">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-609">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="a9c8f-610">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-610">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a9c8f-611">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-611">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-612">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-612">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="a9c8f-613">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-613">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="a9c8f-614">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-614">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="a9c8f-615">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-615">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="a9c8f-616">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-616">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a9c8f-617">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-617">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-618">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-618">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-619">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-619">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="a9c8f-620">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-620">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="a9c8f-621">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-621">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="a9c8f-622">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-622">**mvc, razor**</span></span>

<span data-ttu-id="a9c8f-623">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-623">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="a9c8f-624">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-624">The possible values are:</span></span>

- <span data-ttu-id="a9c8f-625">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-625">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="a9c8f-626">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-626">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="a9c8f-627">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-627">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="a9c8f-628">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-628">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="a9c8f-629">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-629">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="a9c8f-630">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-630">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="a9c8f-631">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-631">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a9c8f-632">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-632">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-633">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-633">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="a9c8f-634">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-634">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a9c8f-635">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-635">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-636">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-636">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="a9c8f-637">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-637">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-638">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-638">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="a9c8f-639">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-639">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-640">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-640">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a9c8f-641">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-641">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="a9c8f-642">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-642">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="a9c8f-643">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-643">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="a9c8f-644">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-644">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="a9c8f-645">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-645">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="a9c8f-646">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-646">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="a9c8f-647">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-647">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-648">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-648">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="a9c8f-649">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-649">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a9c8f-650">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-650">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-651">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-651">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="a9c8f-652">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-652">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="a9c8f-653">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-653">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-654">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-654">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="a9c8f-655">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-655">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="a9c8f-656">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-656">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="a9c8f-657">`--exclude-launch-settings`: esclude *launchSettings.json* dal modello generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-657">`--exclude-launch-settings` - Exclude *launchSettings.json* from the generated template.</span></span>

<span data-ttu-id="a9c8f-658">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-658">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="a9c8f-659">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-659">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a9c8f-660">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-660">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-661">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-661">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-662">`--no-https`: il progetto non richiede HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-662">`--no-https` - Project doesn't require HTTPS.</span></span> <span data-ttu-id="a9c8f-663">`app.UseHsts` e `app.UseHttpsRedirection` non vengono aggiunti a `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-663">`app.UseHsts` and `app.UseHttpsRedirection` aren't added to `Startup.Configure`.</span></span> <span data-ttu-id="a9c8f-664">Questa opzione si applica solo se `Individual`, `IndividualB2C`, `SingleOrg` o `MultiOrg` non sono in uso.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-664">This option only applies if `Individual`, `IndividualB2C`, `SingleOrg`, or `MultiOrg` aren't being used.</span></span>

<span data-ttu-id="a9c8f-665">**page**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-665">**page**</span></span>

<span data-ttu-id="a9c8f-666">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-666">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="a9c8f-667">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-667">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="a9c8f-668">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-668">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="a9c8f-669">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-669">**viewimports**</span></span>

<span data-ttu-id="a9c8f-670">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-670">`-na|--namespace <NAMESPACE_NAME>` - Namespace for the generated code.</span></span> <span data-ttu-id="a9c8f-671">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-671">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="a9c8f-672">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="a9c8f-672">.NET Core 2.0</span></span>](#tab/netcore20)

<span data-ttu-id="a9c8f-673">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-673">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="a9c8f-674">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-674">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-675">**classlib**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-675">**classlib**</span></span>

<span data-ttu-id="a9c8f-676">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-676">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a9c8f-677">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-677">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="a9c8f-678">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-678">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="a9c8f-679">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-679">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-680">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-680">**mstest, xunit**</span></span>

<span data-ttu-id="a9c8f-681">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-681">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="a9c8f-682">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-682">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-683">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-683">**globaljson**</span></span>

<span data-ttu-id="a9c8f-684">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-684">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="a9c8f-685">**web**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-685">**web**</span></span>

<span data-ttu-id="a9c8f-686">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-686">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="a9c8f-687">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-687">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-688">**webapi**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-688">**webapi**</span></span>

<span data-ttu-id="a9c8f-689">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-689">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="a9c8f-690">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-690">The possible values are:</span></span>

- <span data-ttu-id="a9c8f-691">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-691">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="a9c8f-692">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-692">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="a9c8f-693">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-693">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="a9c8f-694">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-694">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="a9c8f-695">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-695">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a9c8f-696">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-696">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-697">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-697">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="a9c8f-698">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-698">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a9c8f-699">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-699">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-700">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-700">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a9c8f-701">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-701">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-702">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-702">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="a9c8f-703">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-703">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="a9c8f-704">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-704">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-705">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-705">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="a9c8f-706">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-706">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="a9c8f-707">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-707">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-708">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-708">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="a9c8f-709">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-709">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a9c8f-710">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-710">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-711">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-711">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="a9c8f-712">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-712">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="a9c8f-713">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-713">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="a9c8f-714">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-714">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="a9c8f-715">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-715">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a9c8f-716">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-716">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-717">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-717">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-718">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-718">**mvc, razor**</span></span>

<span data-ttu-id="a9c8f-719">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-719">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="a9c8f-720">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-720">The possible values are:</span></span>

- <span data-ttu-id="a9c8f-721">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="a9c8f-721">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="a9c8f-722">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-722">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="a9c8f-723">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-723">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="a9c8f-724">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-724">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="a9c8f-725">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-725">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="a9c8f-726">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-726">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="a9c8f-727">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-727">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="a9c8f-728">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-728">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-729">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-729">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="a9c8f-730">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-730">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="a9c8f-731">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-731">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-732">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-732">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="a9c8f-733">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-733">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-734">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-734">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="a9c8f-735">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-735">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-736">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-736">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="a9c8f-737">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-737">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="a9c8f-738">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-738">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="a9c8f-739">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-739">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="a9c8f-740">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-740">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="a9c8f-741">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-741">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="a9c8f-742">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-742">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="a9c8f-743">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-743">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-744">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-744">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="a9c8f-745">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-745">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="a9c8f-746">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-746">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="a9c8f-747">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-747">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="a9c8f-748">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-748">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="a9c8f-749">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-749">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="a9c8f-750">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-750">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="a9c8f-751">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-751">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="a9c8f-752">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-752">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="a9c8f-753">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-753">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="a9c8f-754">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-754">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="a9c8f-755">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-755">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="a9c8f-756">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-756">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="a9c8f-757">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-757">`--no-restore` - Doesn't execute an implicit restore during project creation.</span></span>

<span data-ttu-id="a9c8f-758">**page**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-758">**page**</span></span>

<span data-ttu-id="a9c8f-759">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-759">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="a9c8f-760">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-760">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="a9c8f-761">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-761">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="a9c8f-762">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-762">**viewimports**</span></span>

<span data-ttu-id="a9c8f-763">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-763">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="a9c8f-764">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-764">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="a9c8f-765">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="a9c8f-765">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="a9c8f-766">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-766">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="a9c8f-767">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-767">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a9c8f-768">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-768">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="a9c8f-769">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-769">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="a9c8f-770">**classlib**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-770">**classlib**</span></span>

<span data-ttu-id="a9c8f-771">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-771">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a9c8f-772">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-772">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="a9c8f-773">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-773">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="a9c8f-774">**mvc**</span><span class="sxs-lookup"><span data-stu-id="a9c8f-774">**mvc**</span></span>

<span data-ttu-id="a9c8f-775">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-775">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="a9c8f-776">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-776">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="a9c8f-777">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-777">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="a9c8f-778">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-778">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="a9c8f-779">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-779">Values: `None` or `Individual`.</span></span> <span data-ttu-id="a9c8f-780">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-780">The default value is `None`.</span></span>

<span data-ttu-id="a9c8f-781">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-781">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="a9c8f-782">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-782">Values: `true` or `false`.</span></span> <span data-ttu-id="a9c8f-783">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-783">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="a9c8f-784">Esempi</span><span class="sxs-lookup"><span data-stu-id="a9c8f-784">Examples</span></span>

<span data-ttu-id="a9c8f-785">Creare un progetto di applicazione console C# specificando il nome del modello:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-785">Create a C# console application project by specifying the template name:</span></span>

`dotnet new "Console Application"`

<span data-ttu-id="a9c8f-786">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-786">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="a9c8f-787">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core SDK 2.0 o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-787">Create a .NET Standard class library project in the specified directory (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="a9c8f-788">Creare un nuovo progetto MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-788">Create a new ASP.NET Core C# MVC project in the current directory with no authentication:</span></span>

`dotnet new mvc -au None`

<span data-ttu-id="a9c8f-789">Creare un nuovo progetto xUnit:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-789">Create a new xUnit project:</span></span>

`dotnet new xunit`

<span data-ttu-id="a9c8f-790">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="a9c8f-790">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="a9c8f-791">Elencare tutti i modelli corrispondenti alla sottostringa *we*.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-791">List all templates matching the *we* substring.</span></span> <span data-ttu-id="a9c8f-792">La corrispondenza esatta non viene trovata, quindi viene eseguita la corrispondenza sottostringhe nelle colonne del nome breve e del nome.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-792">No exact match is found, so substring matching runs against both the short name and name columns.</span></span>

`dotnet new we -l`

<span data-ttu-id="a9c8f-793">Provare a richiamare il modello corrispondente a *ng*.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-793">Attempt to invoke the template matching *ng*.</span></span> <span data-ttu-id="a9c8f-794">Se non è possibile determinare una corrispondenza singola vengono elencati i modelli con corrispondenze parziali.</span><span class="sxs-lookup"><span data-stu-id="a9c8f-794">If a single match can't be determined, list the templates that are partial matches.</span></span>

`dotnet new ng`

<span data-ttu-id="a9c8f-795">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="a9c8f-795">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

<span data-ttu-id="a9c8f-796">Creare un file *global.json* nell'impostazione di directory corrente impostando la versione SDK su 2.0.0 (disponibile solo con .NET Core SDK 2.0 o versioni successive):</span><span class="sxs-lookup"><span data-stu-id="a9c8f-796">Create a *global.json* in the current directory setting the SDK version to 2.0.0 (available only with .NET Core SDK 2.0 or later versions):</span></span>

`dotnet new globaljson --sdk-version 2.0.0`

## <a name="see-also"></a><span data-ttu-id="a9c8f-797">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9c8f-797">See also</span></span>

- [<span data-ttu-id="a9c8f-798">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="a9c8f-798">Custom templates for dotnet new</span></span>](custom-templates.md)
- [<span data-ttu-id="a9c8f-799">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="a9c8f-799">Create a custom template for dotnet new</span></span>](../tutorials/create-custom-template.md)
- [<span data-ttu-id="a9c8f-800">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="a9c8f-800">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="a9c8f-801">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="a9c8f-801">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
