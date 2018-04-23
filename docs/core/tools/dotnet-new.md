---
title: Comando dotnet new - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
author: mairaw
ms.author: mairaw
ms.date: 03/26/2018
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 4432587c0015c353a34816eee4206dc53cdefba9
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="f3109-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="f3109-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f3109-104">nome</span><span class="sxs-lookup"><span data-stu-id="f3109-104">Name</span></span>

<span data-ttu-id="f3109-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="f3109-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f3109-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="f3109-106">Synopsis</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="f3109-107">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f3109-107">.NET Core 2.0</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f3109-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f3109-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="f3109-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f3109-109">Description</span></span>

<span data-ttu-id="f3109-110">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="f3109-110">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="f3109-111">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="f3109-111">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="f3109-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="f3109-112">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="f3109-113">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="f3109-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="f3109-114">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="f3109-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="f3109-115">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="f3109-115">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="f3109-116">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f3109-116">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="f3109-117">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="f3109-117">The command contains a default list of templates.</span></span> <span data-ttu-id="f3109-118">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3109-118">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="f3109-119">La tabella seguente descrive i modelli preinstallati con .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="f3109-119">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="f3109-120">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="f3109-120">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="f3109-121">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="f3109-121">Template description</span></span>                          | <span data-ttu-id="f3109-122">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="f3109-122">Template name</span></span> | <span data-ttu-id="f3109-123">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="f3109-123">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="f3109-124">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="f3109-124">Console application</span></span>                          | `console`     | <span data-ttu-id="f3109-125">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f3109-125">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f3109-126">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="f3109-126">Class library</span></span>                                | `classlib`    | <span data-ttu-id="f3109-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f3109-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f3109-128">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="f3109-128">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="f3109-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f3109-129">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f3109-130">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="f3109-130">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="f3109-131">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="f3109-131">[C#], F#, VB</span></span>  |
| <span data-ttu-id="f3109-132">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="f3109-132">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="f3109-133">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f3109-133">[C#], F#</span></span>      |
| <span data-ttu-id="f3109-134">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="f3109-134">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="f3109-135">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f3109-135">[C#], F#</span></span>      |
| <span data-ttu-id="f3109-136">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f3109-136">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="f3109-137">[C#]</span><span class="sxs-lookup"><span data-stu-id="f3109-137">[C#]</span></span>          |
| <span data-ttu-id="f3109-138">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="f3109-138">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="f3109-139">[C#]</span><span class="sxs-lookup"><span data-stu-id="f3109-139">[C#]</span></span>          |
| <span data-ttu-id="f3109-140">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="f3109-140">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="f3109-141">[C#]</span><span class="sxs-lookup"><span data-stu-id="f3109-141">[C#]</span></span>          |
| <span data-ttu-id="f3109-142">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="f3109-142">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="f3109-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="f3109-143">[C#]</span></span>          |
| <span data-ttu-id="f3109-144">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f3109-144">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="f3109-145">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f3109-145">[C#], F#</span></span>      |
| <span data-ttu-id="f3109-146">File global.json</span><span class="sxs-lookup"><span data-stu-id="f3109-146">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="f3109-147">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="f3109-147">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="f3109-148">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="f3109-148">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="f3109-149">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="f3109-149">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="f3109-150">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="f3109-150">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="f3109-151">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="f3109-151">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="f3109-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="f3109-152">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f3109-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f3109-153">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="f3109-154">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="f3109-154">The command contains a default list of templates.</span></span> <span data-ttu-id="f3109-155">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3109-155">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="f3109-156">La tabella seguente descrive i modelli preinstallati con .NET Core 1.x SDK.</span><span class="sxs-lookup"><span data-stu-id="f3109-156">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="f3109-157">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="f3109-157">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="f3109-158">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="f3109-158">Template description</span></span>  | <span data-ttu-id="f3109-159">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="f3109-159">Template name</span></span> | <span data-ttu-id="f3109-160">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="f3109-160">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="f3109-161">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="f3109-161">Console application</span></span>  | `console`     | <span data-ttu-id="f3109-162">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f3109-162">[C#], F#</span></span>  |
| <span data-ttu-id="f3109-163">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="f3109-163">Class library</span></span>        | `classlib`    | <span data-ttu-id="f3109-164">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f3109-164">[C#], F#</span></span>  |
| <span data-ttu-id="f3109-165">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="f3109-165">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="f3109-166">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f3109-166">[C#], F#</span></span>  |
| <span data-ttu-id="f3109-167">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="f3109-167">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="f3109-168">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f3109-168">[C#], F#</span></span>  |
| <span data-ttu-id="f3109-169">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="f3109-169">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="f3109-170">[C#]</span><span class="sxs-lookup"><span data-stu-id="f3109-170">[C#]</span></span>      |
| <span data-ttu-id="f3109-171">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f3109-171">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="f3109-172">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="f3109-172">[C#], F#</span></span>  |
| <span data-ttu-id="f3109-173">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="f3109-173">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="f3109-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="f3109-174">[C#]</span></span>      |
| <span data-ttu-id="f3109-175">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="f3109-175">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="f3109-176">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="f3109-176">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="f3109-177">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="f3109-177">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="f3109-178">Opzioni</span><span class="sxs-lookup"><span data-stu-id="f3109-178">Options</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="f3109-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f3109-179">.NET Core 2.0</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="f3109-180">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="f3109-180">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="f3109-181">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-181">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="f3109-182">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="f3109-182">Prints out help for the command.</span></span> <span data-ttu-id="f3109-183">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="f3109-183">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="f3109-184">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="f3109-184">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="f3109-185">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="f3109-185">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="f3109-186">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-186">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="f3109-187">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="f3109-187">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="f3109-188">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="f3109-188">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="f3109-189">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="f3109-189">Lists templates containing the specified name.</span></span> <span data-ttu-id="f3109-190">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="f3109-190">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="f3109-191">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-191">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="f3109-192">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="f3109-192">The language of the template to create.</span></span> <span data-ttu-id="f3109-193">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="f3109-193">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="f3109-194">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="f3109-194">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="f3109-195">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="f3109-195">The name for the created output.</span></span> <span data-ttu-id="f3109-196">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="f3109-196">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f3109-197">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="f3109-197">Location to place the generated output.</span></span> <span data-ttu-id="f3109-198">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="f3109-198">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="f3109-199">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="f3109-199">Filters templates based on available types.</span></span> <span data-ttu-id="f3109-200">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="f3109-200">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="f3109-201">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="f3109-201">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="f3109-202">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="f3109-202">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="f3109-203">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="f3109-203">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="f3109-204">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="f3109-204">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f3109-205">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f3109-205">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="f3109-206">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="f3109-206">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="f3109-207">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="f3109-207">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="f3109-208">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-208">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="f3109-209">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="f3109-209">Prints out help for the command.</span></span> <span data-ttu-id="f3109-210">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="f3109-210">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="f3109-211">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="f3109-211">Lists templates containing the specified name.</span></span> <span data-ttu-id="f3109-212">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="f3109-212">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="f3109-213">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-213">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="f3109-214">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="f3109-214">The language of the template to create.</span></span> <span data-ttu-id="f3109-215">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="f3109-215">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="f3109-216">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="f3109-216">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="f3109-217">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="f3109-217">The name for the created output.</span></span> <span data-ttu-id="f3109-218">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="f3109-218">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="f3109-219">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="f3109-219">Location to place the generated output.</span></span> <span data-ttu-id="f3109-220">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="f3109-220">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="f3109-221">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="f3109-221">Template options</span></span>

<span data-ttu-id="f3109-222">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="f3109-222">Each project template may have additional options available.</span></span> <span data-ttu-id="f3109-223">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3109-223">The core templates have the following additional options:</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="f3109-224">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="f3109-224">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="f3109-225">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="f3109-225">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="f3109-226">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-226">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="f3109-227">**classlib**</span><span class="sxs-lookup"><span data-stu-id="f3109-227">**classlib**</span></span>

<span data-ttu-id="f3109-228">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f3109-228">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f3109-229">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="f3109-229">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="f3109-230">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="f3109-230">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="f3109-231">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-231">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="f3109-232">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="f3109-232">**mstest, xunit**</span></span>

<span data-ttu-id="f3109-233">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f3109-233">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="f3109-234">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-234">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="f3109-235">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="f3109-235">**globaljson**</span></span>

<span data-ttu-id="f3109-236">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="f3109-236">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="f3109-237">**web**</span><span class="sxs-lookup"><span data-stu-id="f3109-237">**web**</span></span>

<span data-ttu-id="f3109-238">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="f3109-238">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="f3109-239">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-239">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="f3109-240">**webapi**</span><span class="sxs-lookup"><span data-stu-id="f3109-240">**webapi**</span></span>

<span data-ttu-id="f3109-241">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="f3109-241">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="f3109-242">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="f3109-242">The possible values are:</span></span>

- <span data-ttu-id="f3109-243">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="f3109-243">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="f3109-244">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="f3109-244">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="f3109-245">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="f3109-245">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="f3109-246">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="f3109-246">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="f3109-247">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="f3109-247">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="f3109-248">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-248">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="f3109-249">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="f3109-249">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="f3109-250">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-250">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="f3109-251">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-251">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f3109-252">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="f3109-252">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="f3109-253">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f3109-253">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f3109-254">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="f3109-254">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="f3109-255">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-255">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="f3109-256">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f3109-256">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="f3109-257">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="f3109-257">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="f3109-258">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="f3109-258">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="f3109-259">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-259">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="f3109-260">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="f3109-260">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="f3109-261">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="f3109-261">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="f3109-262">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f3109-262">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="f3109-263">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="f3109-263">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="f3109-264">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="f3109-264">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="f3109-265">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f3109-265">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="f3109-266">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="f3109-266">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="f3109-267">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="f3109-267">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="f3109-268">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-268">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f3109-269">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-269">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="f3109-270">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="f3109-270">**mvc, razor**</span></span>

<span data-ttu-id="f3109-271">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="f3109-271">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="f3109-272">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="f3109-272">The possible values are:</span></span>

- <span data-ttu-id="f3109-273">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="f3109-273">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="f3109-274">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="f3109-274">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="f3109-275">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="f3109-275">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="f3109-276">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="f3109-276">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="f3109-277">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="f3109-277">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="f3109-278">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="f3109-278">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="f3109-279">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="f3109-279">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="f3109-280">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-280">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="f3109-281">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="f3109-281">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="f3109-282">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-282">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="f3109-283">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f3109-284">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-284">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="f3109-285">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f3109-286">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-286">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="f3109-287">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-287">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f3109-288">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="f3109-288">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="f3109-289">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f3109-289">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="f3109-290">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="f3109-290">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="f3109-291">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-291">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="f3109-292">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f3109-292">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="f3109-293">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="f3109-293">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="f3109-294">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="f3109-294">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="f3109-295">Usare con l'autenticazione `SingleOrg`, `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-295">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="f3109-296">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="f3109-296">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="f3109-297">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="f3109-297">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="f3109-298">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="f3109-298">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="f3109-299">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="f3109-299">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="f3109-300">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="f3109-300">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="f3109-301">Usare con l'autenticazione `SingleOrg`, `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-301">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="f3109-302">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="f3109-302">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="f3109-303">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="f3109-303">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="f3109-304">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="f3109-304">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="f3109-305">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="f3109-305">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="f3109-306">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-306">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="f3109-307">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="f3109-307">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="f3109-308">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="f3109-308">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="f3109-309">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="f3109-309">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="f3109-310">**page**</span><span class="sxs-lookup"><span data-stu-id="f3109-310">**page**</span></span>

<span data-ttu-id="f3109-311">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="f3109-311">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="f3109-312">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="f3109-312">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="f3109-313">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="f3109-313">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="f3109-314">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="f3109-314">**viewimports**</span></span>

<span data-ttu-id="f3109-315">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="f3109-315">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="f3109-316">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="f3109-316">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="f3109-317">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="f3109-317">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="f3109-318">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="f3109-318">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="f3109-319">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f3109-319">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f3109-320">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="f3109-320">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="f3109-321">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="f3109-321">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="f3109-322">**classlib**</span><span class="sxs-lookup"><span data-stu-id="f3109-322">**classlib**</span></span>

<span data-ttu-id="f3109-323">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f3109-323">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f3109-324">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="f3109-324">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="f3109-325">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="f3109-325">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="f3109-326">**mvc**</span><span class="sxs-lookup"><span data-stu-id="f3109-326">**mvc**</span></span>

<span data-ttu-id="f3109-327">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="f3109-327">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="f3109-328">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="f3109-328">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="f3109-329">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="f3109-329">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="f3109-330">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="f3109-330">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="f3109-331">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="f3109-331">Values: `None` or `Individual`.</span></span> <span data-ttu-id="f3109-332">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="f3109-332">The default value is `None`.</span></span>

<span data-ttu-id="f3109-333">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="f3109-333">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="f3109-334">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="f3109-334">Values: `true` or `false`.</span></span> <span data-ttu-id="f3109-335">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="f3109-335">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="f3109-336">Esempi</span><span class="sxs-lookup"><span data-stu-id="f3109-336">Examples</span></span>

<span data-ttu-id="f3109-337">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="f3109-337">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="f3109-338">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core 2.0 SDK o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="f3109-338">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="f3109-339">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione con destinazione a .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="f3109-339">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="f3109-340">Creare una nuova applicazione xUnit con destinazione .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="f3109-340">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="f3109-341">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="f3109-341">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="f3109-342">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="f3109-342">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

## <a name="see-also"></a><span data-ttu-id="f3109-343">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f3109-343">See also</span></span>

[<span data-ttu-id="f3109-344">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="f3109-344">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="f3109-345">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="f3109-345">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="f3109-346">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="f3109-346">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="f3109-347">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="f3109-347">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
