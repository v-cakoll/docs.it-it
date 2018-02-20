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
ms.workload:
- dotnetcore
ms.openlocfilehash: ea94c875ae6fe82d0e5d35ba8ca3fd47971fbbe6
ms.sourcegitcommit: e2bf8e6bc365bd9a0e86fe81eeae7d14f85f48c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/13/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="65cd8-104">dotnet new</span><span class="sxs-lookup"><span data-stu-id="65cd8-104">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="65cd8-105">nome</span><span class="sxs-lookup"><span data-stu-id="65cd8-105">Name</span></span>

<span data-ttu-id="65cd8-106">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-106">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="65cd8-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="65cd8-107">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="65cd8-108">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="65cd8-108">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="65cd8-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="65cd8-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="65cd8-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="65cd8-110">Description</span></span>

<span data-ttu-id="65cd8-111">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="65cd8-111">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="65cd8-112">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="65cd8-112">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="65cd8-113">Argomenti</span><span class="sxs-lookup"><span data-stu-id="65cd8-113">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="65cd8-114">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="65cd8-114">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="65cd8-115">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="65cd8-115">Each template might have specific options you can pass.</span></span> <span data-ttu-id="65cd8-116">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="65cd8-116">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="65cd8-117">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="65cd8-117">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="65cd8-118">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="65cd8-118">The command contains a default list of templates.</span></span> <span data-ttu-id="65cd8-119">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="65cd8-119">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="65cd8-120">La tabella seguente descrive i modelli preinstallati con .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="65cd8-120">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="65cd8-121">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="65cd8-121">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="65cd8-122">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="65cd8-122">Template description</span></span>                          | <span data-ttu-id="65cd8-123">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="65cd8-123">Template name</span></span> | <span data-ttu-id="65cd8-124">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="65cd8-124">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="65cd8-125">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="65cd8-125">Console application</span></span>                          | `console`     | <span data-ttu-id="65cd8-126">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="65cd8-126">[C#], F#, VB</span></span>  |
| <span data-ttu-id="65cd8-127">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="65cd8-127">Class library</span></span>                                | `classlib`    | <span data-ttu-id="65cd8-128">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="65cd8-128">[C#], F#, VB</span></span>  |
| <span data-ttu-id="65cd8-129">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="65cd8-129">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="65cd8-130">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="65cd8-130">[C#], F#, VB</span></span>  |
| <span data-ttu-id="65cd8-131">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="65cd8-131">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="65cd8-132">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="65cd8-132">[C#], F#, VB</span></span>  |
| <span data-ttu-id="65cd8-133">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="65cd8-133">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="65cd8-134">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="65cd8-134">[C#], F#</span></span>      |
| <span data-ttu-id="65cd8-135">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="65cd8-135">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="65cd8-136">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="65cd8-136">[C#], F#</span></span>      |
| <span data-ttu-id="65cd8-137">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65cd8-137">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="65cd8-138">[C#]</span><span class="sxs-lookup"><span data-stu-id="65cd8-138">[C#]</span></span>          |
| <span data-ttu-id="65cd8-139">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="65cd8-139">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="65cd8-140">[C#]</span><span class="sxs-lookup"><span data-stu-id="65cd8-140">[C#]</span></span>          |
| <span data-ttu-id="65cd8-141">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="65cd8-141">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="65cd8-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="65cd8-142">[C#]</span></span>          |
| <span data-ttu-id="65cd8-143">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="65cd8-143">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="65cd8-144">[C#]</span><span class="sxs-lookup"><span data-stu-id="65cd8-144">[C#]</span></span>          |
| <span data-ttu-id="65cd8-145">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65cd8-145">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="65cd8-146">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="65cd8-146">[C#], F#</span></span>      |
| <span data-ttu-id="65cd8-147">File global.json</span><span class="sxs-lookup"><span data-stu-id="65cd8-147">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="65cd8-148">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="65cd8-148">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="65cd8-149">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="65cd8-149">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="65cd8-150">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="65cd8-150">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="65cd8-151">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="65cd8-151">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="65cd8-152">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="65cd8-152">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="65cd8-153">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="65cd8-153">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="65cd8-154">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="65cd8-154">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="65cd8-155">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="65cd8-155">The command contains a default list of templates.</span></span> <span data-ttu-id="65cd8-156">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="65cd8-156">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="65cd8-157">La tabella seguente descrive i modelli preinstallati con .NET Core 1.x SDK.</span><span class="sxs-lookup"><span data-stu-id="65cd8-157">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="65cd8-158">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="65cd8-158">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="65cd8-159">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="65cd8-159">Template description</span></span>  | <span data-ttu-id="65cd8-160">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="65cd8-160">Template name</span></span> | <span data-ttu-id="65cd8-161">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="65cd8-161">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="65cd8-162">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="65cd8-162">Console application</span></span>  | `console`     | <span data-ttu-id="65cd8-163">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="65cd8-163">[C#], F#</span></span>  |
| <span data-ttu-id="65cd8-164">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="65cd8-164">Class library</span></span>        | `classlib`    | <span data-ttu-id="65cd8-165">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="65cd8-165">[C#], F#</span></span>  |
| <span data-ttu-id="65cd8-166">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="65cd8-166">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="65cd8-167">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="65cd8-167">[C#], F#</span></span>  |
| <span data-ttu-id="65cd8-168">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="65cd8-168">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="65cd8-169">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="65cd8-169">[C#], F#</span></span>  |
| <span data-ttu-id="65cd8-170">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="65cd8-170">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="65cd8-171">[C#]</span><span class="sxs-lookup"><span data-stu-id="65cd8-171">[C#]</span></span>      |
| <span data-ttu-id="65cd8-172">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65cd8-172">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="65cd8-173">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="65cd8-173">[C#], F#</span></span>  |
| <span data-ttu-id="65cd8-174">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="65cd8-174">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="65cd8-175">[C#]</span><span class="sxs-lookup"><span data-stu-id="65cd8-175">[C#]</span></span>      |
| <span data-ttu-id="65cd8-176">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="65cd8-176">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="65cd8-177">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="65cd8-177">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="65cd8-178">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="65cd8-178">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="65cd8-179">Opzioni</span><span class="sxs-lookup"><span data-stu-id="65cd8-179">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="65cd8-180">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="65cd8-180">.NET Core 2.x</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="65cd8-181">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="65cd8-181">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="65cd8-182">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-182">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="65cd8-183">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="65cd8-183">Prints out help for the command.</span></span> <span data-ttu-id="65cd8-184">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-184">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="65cd8-185">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="65cd8-185">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="65cd8-186">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="65cd8-186">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="65cd8-187">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-187">Lists templates containing the specified name.</span></span> <span data-ttu-id="65cd8-188">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="65cd8-188">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="65cd8-189">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-189">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="65cd8-190">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="65cd8-190">The language of the template to create.</span></span> <span data-ttu-id="65cd8-191">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="65cd8-191">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="65cd8-192">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="65cd8-192">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="65cd8-193">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-193">The name for the created output.</span></span> <span data-ttu-id="65cd8-194">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="65cd8-194">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="65cd8-195">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-195">Location to place the generated output.</span></span> <span data-ttu-id="65cd8-196">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="65cd8-196">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="65cd8-197">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="65cd8-197">Filters templates based on available types.</span></span> <span data-ttu-id="65cd8-198">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="65cd8-198">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="65cd8-199">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="65cd8-199">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="65cd8-200">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="65cd8-200">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="65cd8-201">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="65cd8-201">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="65cd8-202">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="65cd8-202">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="65cd8-203">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="65cd8-203">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="65cd8-204">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="65cd8-204">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="65cd8-205">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="65cd8-205">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="65cd8-206">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-206">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="65cd8-207">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="65cd8-207">Prints out help for the command.</span></span> <span data-ttu-id="65cd8-208">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-208">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="65cd8-209">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-209">Lists templates containing the specified name.</span></span> <span data-ttu-id="65cd8-210">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="65cd8-210">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="65cd8-211">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-211">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="65cd8-212">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="65cd8-212">The language of the template to create.</span></span> <span data-ttu-id="65cd8-213">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="65cd8-213">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="65cd8-214">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="65cd8-214">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="65cd8-215">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-215">The name for the created output.</span></span> <span data-ttu-id="65cd8-216">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="65cd8-216">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="65cd8-217">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-217">Location to place the generated output.</span></span> <span data-ttu-id="65cd8-218">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="65cd8-218">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="65cd8-219">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="65cd8-219">Template options</span></span>

<span data-ttu-id="65cd8-220">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="65cd8-220">Each project template may have additional options available.</span></span> <span data-ttu-id="65cd8-221">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="65cd8-221">The core templates have the following additional options:</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="65cd8-222">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="65cd8-222">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="65cd8-223">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="65cd8-223">**console, angular, react, reactredux**</span></span>

<span data-ttu-id="65cd8-224">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-224">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="65cd8-225">**classlib**</span><span class="sxs-lookup"><span data-stu-id="65cd8-225">**classlib**</span></span>

<span data-ttu-id="65cd8-226">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="65cd8-226">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="65cd8-227">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="65cd8-227">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="65cd8-228">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-228">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="65cd8-229">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-229">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="65cd8-230">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="65cd8-230">**mstest, xunit**</span></span>

<span data-ttu-id="65cd8-231">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="65cd8-231">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="65cd8-232">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-232">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="65cd8-233">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="65cd8-233">**globaljson**</span></span>

<span data-ttu-id="65cd8-234">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="65cd8-234">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="65cd8-235">**web**</span><span class="sxs-lookup"><span data-stu-id="65cd8-235">**web**</span></span>

<span data-ttu-id="65cd8-236">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-236">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="65cd8-237">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-237">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="65cd8-238">**webapi**</span><span class="sxs-lookup"><span data-stu-id="65cd8-238">**webapi**</span></span>

<span data-ttu-id="65cd8-239">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="65cd8-239">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="65cd8-240">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="65cd8-240">The possible values are:</span></span>

- <span data-ttu-id="65cd8-241">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="65cd8-241">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="65cd8-242">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="65cd8-242">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="65cd8-243">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="65cd8-243">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="65cd8-244">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="65cd8-244">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="65cd8-245">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="65cd8-245">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="65cd8-246">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-246">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="65cd8-247">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-247">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="65cd8-248">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-248">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="65cd8-249">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-249">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="65cd8-250">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="65cd8-250">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="65cd8-251">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-251">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="65cd8-252">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-252">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="65cd8-253">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-253">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="65cd8-254">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-254">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="65cd8-255">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-255">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="65cd8-256">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="65cd8-256">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="65cd8-257">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-257">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="65cd8-258">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-258">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="65cd8-259">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="65cd8-259">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="65cd8-260">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-260">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="65cd8-261">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-261">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="65cd8-262">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="65cd8-262">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="65cd8-263">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-263">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="65cd8-264">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-264">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="65cd8-265">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="65cd8-265">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="65cd8-266">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-266">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="65cd8-267">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-267">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="65cd8-268">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="65cd8-268">**mvc, razor**</span></span>

<span data-ttu-id="65cd8-269">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="65cd8-269">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="65cd8-270">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="65cd8-270">The possible values are:</span></span>

- <span data-ttu-id="65cd8-271">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="65cd8-271">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="65cd8-272">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="65cd8-272">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="65cd8-273">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="65cd8-273">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="65cd8-274">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="65cd8-274">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="65cd8-275">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="65cd8-275">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="65cd8-276">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="65cd8-276">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="65cd8-277">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="65cd8-277">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="65cd8-278">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-278">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="65cd8-279">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-279">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="65cd8-280">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-280">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="65cd8-281">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-281">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="65cd8-282">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-282">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="65cd8-283">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="65cd8-284">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-284">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="65cd8-285">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="65cd8-286">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="65cd8-286">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="65cd8-287">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-287">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="65cd8-288">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-288">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="65cd8-289">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-289">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="65cd8-290">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-290">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="65cd8-291">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-291">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="65cd8-292">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="65cd8-292">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="65cd8-293">Usare con l'autenticazione `SingleOrg`, `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-293">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="65cd8-294">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-294">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="65cd8-295">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="65cd8-295">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="65cd8-296">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-296">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="65cd8-297">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-297">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="65cd8-298">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="65cd8-298">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="65cd8-299">Usare con l'autenticazione `SingleOrg`, `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-299">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="65cd8-300">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-300">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="65cd8-301">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="65cd8-301">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="65cd8-302">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-302">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="65cd8-303">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-303">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="65cd8-304">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-304">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="65cd8-305">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="65cd8-305">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="65cd8-306">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-306">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="65cd8-307">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="65cd8-307">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="65cd8-308">**page**</span><span class="sxs-lookup"><span data-stu-id="65cd8-308">**page**</span></span>

<span data-ttu-id="65cd8-309">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-309">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="65cd8-310">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-310">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="65cd8-311">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="65cd8-311">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="65cd8-312">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="65cd8-312">**viewimports**</span></span>

<span data-ttu-id="65cd8-313">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="65cd8-313">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="65cd8-314">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-314">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="65cd8-315">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="65cd8-315">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="65cd8-316">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="65cd8-316">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="65cd8-317">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="65cd8-317">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="65cd8-318">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-318">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="65cd8-319">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-319">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="65cd8-320">**classlib**</span><span class="sxs-lookup"><span data-stu-id="65cd8-320">**classlib**</span></span>

<span data-ttu-id="65cd8-321">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="65cd8-321">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="65cd8-322">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-322">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="65cd8-323">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-323">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="65cd8-324">**mvc**</span><span class="sxs-lookup"><span data-stu-id="65cd8-324">**mvc**</span></span>

<span data-ttu-id="65cd8-325">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="65cd8-325">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="65cd8-326">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-326">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="65cd8-327">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-327">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="65cd8-328">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="65cd8-328">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="65cd8-329">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-329">Values: `None` or `Individual`.</span></span> <span data-ttu-id="65cd8-330">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-330">The default value is `None`.</span></span>

<span data-ttu-id="65cd8-331">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="65cd8-331">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="65cd8-332">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-332">Values: `true` or `false`.</span></span> <span data-ttu-id="65cd8-333">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="65cd8-333">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="65cd8-334">Esempi</span><span class="sxs-lookup"><span data-stu-id="65cd8-334">Examples</span></span>

<span data-ttu-id="65cd8-335">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="65cd8-335">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#`

<span data-ttu-id="65cd8-336">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core 2.0 SDK o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="65cd8-336">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="65cd8-337">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione con destinazione a .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="65cd8-337">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="65cd8-338">Creare una nuova applicazione xUnit con destinazione .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="65cd8-338">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="65cd8-339">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="65cd8-339">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

## <a name="see-also"></a><span data-ttu-id="65cd8-340">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65cd8-340">See also</span></span>

[<span data-ttu-id="65cd8-341">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="65cd8-341">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="65cd8-342">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="65cd8-342">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="65cd8-343">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="65cd8-343">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="65cd8-344">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="65cd8-344">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
