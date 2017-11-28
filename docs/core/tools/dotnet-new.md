---
title: Comando dotnet new - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
keywords: dotnet-new, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.openlocfilehash: d64881380febee08414f57a36ed92079e8d69ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-new"></a><span data-ttu-id="d2abb-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="d2abb-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="d2abb-105">Nome</span><span class="sxs-lookup"><span data-stu-id="d2abb-105">Name</span></span>

<span data-ttu-id="d2abb-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d2abb-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="d2abb-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d2abb-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d2abb-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d2abb-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d2abb-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="d2abb-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d2abb-110">Description</span></span>

<span data-ttu-id="d2abb-111">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="d2abb-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="d2abb-112">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="d2abb-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="d2abb-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d2abb-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="d2abb-114">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="d2abb-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="d2abb-115">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="d2abb-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="d2abb-116">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="d2abb-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d2abb-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d2abb-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d2abb-118">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="d2abb-118">The command contains a default list of templates.</span></span> <span data-ttu-id="d2abb-119">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="d2abb-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="d2abb-120">La tabella seguente descrive i modelli preinstallati con .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="d2abb-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="d2abb-121">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="d2abb-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d2abb-122">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="d2abb-122">Template description</span></span>                          | <span data-ttu-id="d2abb-123">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="d2abb-123">Template name</span></span>  | <span data-ttu-id="d2abb-124">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="d2abb-124">Languages</span></span>     |
|----------------------------------------------|----------------|---------------|
| <span data-ttu-id="d2abb-125">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="d2abb-125">Console application</span></span>                          | <span data-ttu-id="d2abb-126">console</span><span class="sxs-lookup"><span data-stu-id="d2abb-126">console</span></span>        | <span data-ttu-id="d2abb-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d2abb-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d2abb-128">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="d2abb-128">Class library</span></span>                                | <span data-ttu-id="d2abb-129">classlib</span><span class="sxs-lookup"><span data-stu-id="d2abb-129">classlib</span></span>       | <span data-ttu-id="d2abb-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d2abb-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d2abb-131">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="d2abb-131">Unit test project</span></span>                            | <span data-ttu-id="d2abb-132">mstest</span><span class="sxs-lookup"><span data-stu-id="d2abb-132">mstest</span></span>         | <span data-ttu-id="d2abb-133">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d2abb-133">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d2abb-134">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="d2abb-134">xUnit test project</span></span>                           | <span data-ttu-id="d2abb-135">xunit</span><span class="sxs-lookup"><span data-stu-id="d2abb-135">xunit</span></span>          | <span data-ttu-id="d2abb-136">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="d2abb-136">[C#], F#, VB</span></span>  |
| <span data-ttu-id="d2abb-137">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="d2abb-137">ASP.NET Core empty</span></span>                           | <span data-ttu-id="d2abb-138">Web</span><span class="sxs-lookup"><span data-stu-id="d2abb-138">web</span></span>            | <span data-ttu-id="d2abb-139">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2abb-139">[C#], F#</span></span>      |
| <span data-ttu-id="d2abb-140">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="d2abb-140">ASP.NET Core Web App (Model-View-Controller)</span></span> | <span data-ttu-id="d2abb-141">mvc</span><span class="sxs-lookup"><span data-stu-id="d2abb-141">mvc</span></span>            | <span data-ttu-id="d2abb-142">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2abb-142">[C#], F#</span></span>      |
| <span data-ttu-id="d2abb-143">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d2abb-143">ASP.NET Core Web App</span></span>                         | <span data-ttu-id="d2abb-144">razor</span><span class="sxs-lookup"><span data-stu-id="d2abb-144">razor</span></span>          | <span data-ttu-id="d2abb-145">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2abb-145">[C#]</span></span>          |
| <span data-ttu-id="d2abb-146">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="d2abb-146">ASP.NET Core with Angular</span></span>                    | <span data-ttu-id="d2abb-147">angular</span><span class="sxs-lookup"><span data-stu-id="d2abb-147">angular</span></span>        | <span data-ttu-id="d2abb-148">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2abb-148">[C#]</span></span>          |
| <span data-ttu-id="d2abb-149">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="d2abb-149">ASP.NET Core with React.js</span></span>                   | <span data-ttu-id="d2abb-150">react</span><span class="sxs-lookup"><span data-stu-id="d2abb-150">react</span></span>          | <span data-ttu-id="d2abb-151">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2abb-151">[C#]</span></span>          |
| <span data-ttu-id="d2abb-152">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="d2abb-152">ASP.NET Core with React.js and Redux</span></span>         | <span data-ttu-id="d2abb-153">reactredux</span><span class="sxs-lookup"><span data-stu-id="d2abb-153">reactredux</span></span>     | <span data-ttu-id="d2abb-154">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2abb-154">[C#]</span></span>          |
| <span data-ttu-id="d2abb-155">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d2abb-155">ASP.NET Core Web API</span></span>                         | <span data-ttu-id="d2abb-156">webapi</span><span class="sxs-lookup"><span data-stu-id="d2abb-156">webapi</span></span>         | <span data-ttu-id="d2abb-157">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2abb-157">[C#], F#</span></span>      |
| <span data-ttu-id="d2abb-158">File global.json</span><span class="sxs-lookup"><span data-stu-id="d2abb-158">global.json file</span></span>                             | <span data-ttu-id="d2abb-159">globaljson</span><span class="sxs-lookup"><span data-stu-id="d2abb-159">globaljson</span></span>     |               |
| <span data-ttu-id="d2abb-160">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="d2abb-160">Nuget config</span></span>                                 | <span data-ttu-id="d2abb-161">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="d2abb-161">nugetconfig</span></span>    |               |
| <span data-ttu-id="d2abb-162">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="d2abb-162">Web config</span></span>                                   | <span data-ttu-id="d2abb-163">webconfig</span><span class="sxs-lookup"><span data-stu-id="d2abb-163">webconfig</span></span>      |               |
| <span data-ttu-id="d2abb-164">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="d2abb-164">Solution file</span></span>                                | <span data-ttu-id="d2abb-165">sln</span><span class="sxs-lookup"><span data-stu-id="d2abb-165">sln</span></span>            |               |
| <span data-ttu-id="d2abb-166">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="d2abb-166">Razor page</span></span>                                   | <span data-ttu-id="d2abb-167">pagina</span><span class="sxs-lookup"><span data-stu-id="d2abb-167">page</span></span>           |               |
| <span data-ttu-id="d2abb-168">MVC/ViewImports</span><span class="sxs-lookup"><span data-stu-id="d2abb-168">MVC/ViewImports</span></span>                              | <span data-ttu-id="d2abb-169">viewimports</span><span class="sxs-lookup"><span data-stu-id="d2abb-169">viewimports</span></span>    |               |
| <span data-ttu-id="d2abb-170">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="d2abb-170">MVC ViewStart</span></span>                                | <span data-ttu-id="d2abb-171">viewstart</span><span class="sxs-lookup"><span data-stu-id="d2abb-171">viewstart</span></span>      |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d2abb-172">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d2abb-172">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d2abb-173">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="d2abb-173">The command contains a default list of templates.</span></span> <span data-ttu-id="d2abb-174">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="d2abb-174">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="d2abb-175">La tabella seguente descrive i modelli preinstallati con .NET Core 1.x SDK.</span><span class="sxs-lookup"><span data-stu-id="d2abb-175">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="d2abb-176">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="d2abb-176">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="d2abb-177">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="d2abb-177">Template description</span></span>  | <span data-ttu-id="d2abb-178">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="d2abb-178">Template name</span></span>  | <span data-ttu-id="d2abb-179">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="d2abb-179">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="d2abb-180">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="d2abb-180">Console application</span></span>  | <span data-ttu-id="d2abb-181">console</span><span class="sxs-lookup"><span data-stu-id="d2abb-181">console</span></span>        | <span data-ttu-id="d2abb-182">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2abb-182">[C#], F#</span></span>  |
| <span data-ttu-id="d2abb-183">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="d2abb-183">Class library</span></span>        | <span data-ttu-id="d2abb-184">classlib</span><span class="sxs-lookup"><span data-stu-id="d2abb-184">classlib</span></span>       | <span data-ttu-id="d2abb-185">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2abb-185">[C#], F#</span></span>  |
| <span data-ttu-id="d2abb-186">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="d2abb-186">Unit test project</span></span>    | <span data-ttu-id="d2abb-187">mstest</span><span class="sxs-lookup"><span data-stu-id="d2abb-187">mstest</span></span>         | <span data-ttu-id="d2abb-188">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2abb-188">[C#], F#</span></span>  |
| <span data-ttu-id="d2abb-189">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="d2abb-189">xUnit test project</span></span>   | <span data-ttu-id="d2abb-190">xunit</span><span class="sxs-lookup"><span data-stu-id="d2abb-190">xunit</span></span>          | <span data-ttu-id="d2abb-191">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2abb-191">[C#], F#</span></span>  |
| <span data-ttu-id="d2abb-192">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="d2abb-192">ASP.NET Core empty</span></span>   | <span data-ttu-id="d2abb-193">Web</span><span class="sxs-lookup"><span data-stu-id="d2abb-193">web</span></span>            | <span data-ttu-id="d2abb-194">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2abb-194">[C#]</span></span>      |
| <span data-ttu-id="d2abb-195">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d2abb-195">ASP.NET Core Web App</span></span> | <span data-ttu-id="d2abb-196">mvc</span><span class="sxs-lookup"><span data-stu-id="d2abb-196">mvc</span></span>            | <span data-ttu-id="d2abb-197">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="d2abb-197">[C#], F#</span></span>  |
| <span data-ttu-id="d2abb-198">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d2abb-198">ASP.NET Core Web API</span></span> | <span data-ttu-id="d2abb-199">webapi</span><span class="sxs-lookup"><span data-stu-id="d2abb-199">webapi</span></span>         | <span data-ttu-id="d2abb-200">[C#]</span><span class="sxs-lookup"><span data-stu-id="d2abb-200">[C#]</span></span>      |
| <span data-ttu-id="d2abb-201">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="d2abb-201">Nuget config</span></span>         | <span data-ttu-id="d2abb-202">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="d2abb-202">nugetconfig</span></span>    |           |
| <span data-ttu-id="d2abb-203">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="d2abb-203">Web config</span></span>           | <span data-ttu-id="d2abb-204">webconfig</span><span class="sxs-lookup"><span data-stu-id="d2abb-204">webconfig</span></span>      |           |
| <span data-ttu-id="d2abb-205">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="d2abb-205">Solution file</span></span>        | <span data-ttu-id="d2abb-206">sln</span><span class="sxs-lookup"><span data-stu-id="d2abb-206">sln</span></span>            |           |

---

## <a name="options"></a><span data-ttu-id="d2abb-207">Opzioni</span><span class="sxs-lookup"><span data-stu-id="d2abb-207">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d2abb-208">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d2abb-208">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="d2abb-209">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="d2abb-209">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="d2abb-210">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-210">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d2abb-211">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="d2abb-211">Prints out help for the command.</span></span> <span data-ttu-id="d2abb-212">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-212">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="d2abb-213">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="d2abb-213">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="d2abb-214">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="d2abb-214">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="d2abb-215">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-215">Lists templates containing the specified name.</span></span> <span data-ttu-id="d2abb-216">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="d2abb-216">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d2abb-217">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-217">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="d2abb-218">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="d2abb-218">The language of the template to create.</span></span> <span data-ttu-id="d2abb-219">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="d2abb-219">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d2abb-220">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="d2abb-220">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d2abb-221">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-221">The name for the created output.</span></span> <span data-ttu-id="d2abb-222">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d2abb-222">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d2abb-223">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-223">Location to place the generated output.</span></span> <span data-ttu-id="d2abb-224">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d2abb-224">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="d2abb-225">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="d2abb-225">Filters templates based on available types.</span></span> <span data-ttu-id="d2abb-226">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="d2abb-226">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="d2abb-227">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="d2abb-227">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="d2abb-228">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="d2abb-228">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="d2abb-229">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="d2abb-229">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="d2abb-230">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="d2abb-230">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d2abb-231">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d2abb-231">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="d2abb-232">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="d2abb-232">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="d2abb-233">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="d2abb-233">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="d2abb-234">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-234">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="d2abb-235">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="d2abb-235">Prints out help for the command.</span></span> <span data-ttu-id="d2abb-236">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-236">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="d2abb-237">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-237">Lists templates containing the specified name.</span></span> <span data-ttu-id="d2abb-238">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="d2abb-238">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="d2abb-239">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-239">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="d2abb-240">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="d2abb-240">The language of the template to create.</span></span> <span data-ttu-id="d2abb-241">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="d2abb-241">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="d2abb-242">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="d2abb-242">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="d2abb-243">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-243">The name for the created output.</span></span> <span data-ttu-id="d2abb-244">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d2abb-244">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="d2abb-245">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-245">Location to place the generated output.</span></span> <span data-ttu-id="d2abb-246">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="d2abb-246">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="d2abb-247">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="d2abb-247">Template options</span></span>

<span data-ttu-id="d2abb-248">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="d2abb-248">Each project template may have additional options available.</span></span> <span data-ttu-id="d2abb-249">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2abb-249">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="d2abb-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="d2abb-250">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="d2abb-251">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="d2abb-251">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="d2abb-252">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-252">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d2abb-253">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d2abb-253">**classlib**</span></span>

<span data-ttu-id="d2abb-254">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d2abb-254">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2abb-255">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d2abb-255">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="d2abb-256">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-256">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="d2abb-257">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-257">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d2abb-258">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="d2abb-258">**mstest, xunit**</span></span>

<span data-ttu-id="d2abb-259">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="d2abb-259">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="d2abb-260">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-260">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d2abb-261">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="d2abb-261">**globaljson**</span></span>

<span data-ttu-id="d2abb-262">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="d2abb-262">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="d2abb-263">**web**</span><span class="sxs-lookup"><span data-stu-id="d2abb-263">**web**</span></span>

<span data-ttu-id="d2abb-264">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d2abb-265">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-265">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d2abb-266">**webapi**</span><span class="sxs-lookup"><span data-stu-id="d2abb-266">**webapi**</span></span>

<span data-ttu-id="d2abb-267">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="d2abb-267">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d2abb-268">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="d2abb-268">The possible values are:</span></span>

- <span data-ttu-id="d2abb-269">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="d2abb-269">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d2abb-270">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="d2abb-270">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d2abb-271">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="d2abb-271">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d2abb-272">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="d2abb-272">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d2abb-273">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="d2abb-273">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d2abb-274">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-274">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2abb-275">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-275">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="d2abb-276">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-276">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d2abb-277">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-277">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d2abb-278">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="d2abb-278">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d2abb-279">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-279">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d2abb-280">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-280">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d2abb-281">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-281">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d2abb-282">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-282">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="d2abb-283">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-283">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d2abb-284">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="d2abb-284">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d2abb-285">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-285">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2abb-286">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-286">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d2abb-287">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="d2abb-287">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d2abb-288">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-288">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="d2abb-289">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-289">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d2abb-290">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="d2abb-290">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d2abb-291">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-291">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d2abb-292">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-292">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d2abb-293">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="d2abb-293">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d2abb-294">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-294">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d2abb-295">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-295">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d2abb-296">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="d2abb-296">**mvc, razor**</span></span>

<span data-ttu-id="d2abb-297">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="d2abb-297">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="d2abb-298">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="d2abb-298">The possible values are:</span></span>

- <span data-ttu-id="d2abb-299">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="d2abb-299">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="d2abb-300">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="d2abb-300">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="d2abb-301">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="d2abb-301">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="d2abb-302">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="d2abb-302">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="d2abb-303">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="d2abb-303">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="d2abb-304">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="d2abb-304">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="d2abb-305">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="d2abb-305">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="d2abb-306">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-306">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="d2abb-307">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-307">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="d2abb-308">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-308">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="d2abb-309">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-309">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d2abb-310">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-310">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="d2abb-311">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-311">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d2abb-312">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-312">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="d2abb-313">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-313">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d2abb-314">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="d2abb-314">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="d2abb-315">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-315">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="d2abb-316">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-316">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="d2abb-317">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-317">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="d2abb-318">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-318">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="d2abb-319">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-319">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="d2abb-320">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="d2abb-320">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="d2abb-321">Usare con l'autenticazione `SingleOrg`, `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-321">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="d2abb-322">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-322">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="d2abb-323">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="d2abb-323">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="d2abb-324">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-324">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="d2abb-325">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-325">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="d2abb-326">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="d2abb-326">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="d2abb-327">Usare con l'autenticazione `SingleOrg`, `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-327">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="d2abb-328">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-328">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="d2abb-329">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="d2abb-329">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="d2abb-330">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-330">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="d2abb-331">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-331">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="d2abb-332">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-332">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="d2abb-333">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="d2abb-333">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="d2abb-334">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-334">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="d2abb-335">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="d2abb-335">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="d2abb-336">**page**</span><span class="sxs-lookup"><span data-stu-id="d2abb-336">**page**</span></span>

<span data-ttu-id="d2abb-337">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-337">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d2abb-338">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-338">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="d2abb-339">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="d2abb-339">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="d2abb-340">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="d2abb-340">**viewimports**</span></span>

<span data-ttu-id="d2abb-341">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="d2abb-341">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="d2abb-342">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-342">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="d2abb-343">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="d2abb-343">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="d2abb-344">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="d2abb-344">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="d2abb-345">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d2abb-345">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2abb-346">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-346">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="d2abb-347">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-347">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="d2abb-348">**classlib**</span><span class="sxs-lookup"><span data-stu-id="d2abb-348">**classlib**</span></span>

<span data-ttu-id="d2abb-349">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d2abb-349">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2abb-350">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-350">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="d2abb-351">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-351">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="d2abb-352">**mvc**</span><span class="sxs-lookup"><span data-stu-id="d2abb-352">**mvc**</span></span>

<span data-ttu-id="d2abb-353">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d2abb-353">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="d2abb-354">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-354">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="d2abb-355">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-355">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="d2abb-356">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="d2abb-356">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="d2abb-357">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-357">Values: `None` or `Individual`.</span></span> <span data-ttu-id="d2abb-358">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-358">The default value is `None`.</span></span>

<span data-ttu-id="d2abb-359">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="d2abb-359">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="d2abb-360">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-360">Values: `true` or `false`.</span></span> <span data-ttu-id="d2abb-361">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="d2abb-361">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="d2abb-362">Esempi</span><span class="sxs-lookup"><span data-stu-id="d2abb-362">Examples</span></span>

<span data-ttu-id="d2abb-363">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="d2abb-363">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="d2abb-364">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core 2.0 SDK o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="d2abb-364">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="d2abb-365">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione con destinazione a .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="d2abb-365">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="d2abb-366">Creare una nuova applicazione xUnit con destinazione .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="d2abb-366">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="d2abb-367">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="d2abb-367">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="d2abb-368">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d2abb-368">See also</span></span>

[<span data-ttu-id="d2abb-369">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="d2abb-369">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="d2abb-370">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="d2abb-370">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="d2abb-371">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="d2abb-371">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="d2abb-372">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="d2abb-372">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
