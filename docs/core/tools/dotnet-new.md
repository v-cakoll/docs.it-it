---
title: Comando dotnet new - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet new consente di creare nuovi progetti .NET Core in base al modello specificato.
author: mairaw
ms.author: mairaw
ms.date: 03/26/2018
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: ab8d6f779a428aab7bd2739105dcf08b51d14ab9
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-new"></a><span data-ttu-id="07bb6-103">dotnet new</span><span class="sxs-lookup"><span data-stu-id="07bb6-103">dotnet new</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="07bb6-104">nome</span><span class="sxs-lookup"><span data-stu-id="07bb6-104">Name</span></span>

<span data-ttu-id="07bb6-105">`dotnet new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-105">`dotnet new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="07bb6-106">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="07bb6-106">Synopsis</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="07bb6-107">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="07bb6-107">.NET Core 2.0</span></span>](#tab/netcore2x)
```
dotnet new <TEMPLATE> [--force] [-i|--install] [-lang|--language] [-n|--name] [-o|--output] [-u|--uninstall] [Template options]
dotnet new <TEMPLATE> [-l|--list] [--type]
dotnet new [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07bb6-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07bb6-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="07bb6-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07bb6-109">Description</span></span>

<span data-ttu-id="07bb6-110">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="07bb6-110">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span>

<span data-ttu-id="07bb6-111">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="07bb6-111">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="07bb6-112">Argomenti</span><span class="sxs-lookup"><span data-stu-id="07bb6-112">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="07bb6-113">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="07bb6-113">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="07bb6-114">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="07bb6-114">Each template might have specific options you can pass.</span></span> <span data-ttu-id="07bb6-115">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="07bb6-115">For more information, see [Template options](#template-options).</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="07bb6-116">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="07bb6-116">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="07bb6-117">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="07bb6-117">The command contains a default list of templates.</span></span> <span data-ttu-id="07bb6-118">Usare `dotnet new -l` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="07bb6-118">Use `dotnet new -l` to obtain a list of the available templates.</span></span> <span data-ttu-id="07bb6-119">La tabella seguente descrive i modelli preinstallati con .NET Core 2.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="07bb6-119">The following table shows the templates that come pre-installed with the .NET Core 2.0 SDK.</span></span> <span data-ttu-id="07bb6-120">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="07bb6-120">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="07bb6-121">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="07bb6-121">Template description</span></span>                          | <span data-ttu-id="07bb6-122">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="07bb6-122">Template name</span></span> | <span data-ttu-id="07bb6-123">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="07bb6-123">Languages</span></span>     |
|----------------------------------------------|---------------|---------------|
| <span data-ttu-id="07bb6-124">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="07bb6-124">Console application</span></span>                          | `console`     | <span data-ttu-id="07bb6-125">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="07bb6-125">[C#], F#, VB</span></span>  |
| <span data-ttu-id="07bb6-126">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="07bb6-126">Class library</span></span>                                | `classlib`    | <span data-ttu-id="07bb6-127">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="07bb6-127">[C#], F#, VB</span></span>  |
| <span data-ttu-id="07bb6-128">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="07bb6-128">Unit test project</span></span>                            | `mstest`      | <span data-ttu-id="07bb6-129">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="07bb6-129">[C#], F#, VB</span></span>  |
| <span data-ttu-id="07bb6-130">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="07bb6-130">xUnit test project</span></span>                           | `xunit`       | <span data-ttu-id="07bb6-131">[C#], F#, VB</span><span class="sxs-lookup"><span data-stu-id="07bb6-131">[C#], F#, VB</span></span>  |
| <span data-ttu-id="07bb6-132">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="07bb6-132">ASP.NET Core empty</span></span>                           | `web`         | <span data-ttu-id="07bb6-133">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="07bb6-133">[C#], F#</span></span>      |
| <span data-ttu-id="07bb6-134">App Web ASP.NET Core (Model-View-Controller)</span><span class="sxs-lookup"><span data-stu-id="07bb6-134">ASP.NET Core Web App (Model-View-Controller)</span></span> | `mvc`         | <span data-ttu-id="07bb6-135">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="07bb6-135">[C#], F#</span></span>      |
| <span data-ttu-id="07bb6-136">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07bb6-136">ASP.NET Core Web App</span></span>                         | `razor`       | <span data-ttu-id="07bb6-137">[C#]</span><span class="sxs-lookup"><span data-stu-id="07bb6-137">[C#]</span></span>          |
| <span data-ttu-id="07bb6-138">ASP.NET Core con Angular</span><span class="sxs-lookup"><span data-stu-id="07bb6-138">ASP.NET Core with Angular</span></span>                    | `angular`     | <span data-ttu-id="07bb6-139">[C#]</span><span class="sxs-lookup"><span data-stu-id="07bb6-139">[C#]</span></span>          |
| <span data-ttu-id="07bb6-140">ASP.NET Core con React.js</span><span class="sxs-lookup"><span data-stu-id="07bb6-140">ASP.NET Core with React.js</span></span>                   | `react`       | <span data-ttu-id="07bb6-141">[C#]</span><span class="sxs-lookup"><span data-stu-id="07bb6-141">[C#]</span></span>          |
| <span data-ttu-id="07bb6-142">ASP.NET Core con React.js e Redux</span><span class="sxs-lookup"><span data-stu-id="07bb6-142">ASP.NET Core with React.js and Redux</span></span>         | `reactredux`  | <span data-ttu-id="07bb6-143">[C#]</span><span class="sxs-lookup"><span data-stu-id="07bb6-143">[C#]</span></span>          |
| <span data-ttu-id="07bb6-144">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07bb6-144">ASP.NET Core Web API</span></span>                         | `webapi`      | <span data-ttu-id="07bb6-145">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="07bb6-145">[C#], F#</span></span>      |
| <span data-ttu-id="07bb6-146">File global.json</span><span class="sxs-lookup"><span data-stu-id="07bb6-146">global.json file</span></span>                             | `globaljson`  |               |
| <span data-ttu-id="07bb6-147">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="07bb6-147">Nuget config</span></span>                                 | `nugetconfig` |               |
| <span data-ttu-id="07bb6-148">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="07bb6-148">Web config</span></span>                                   | `webconfig`   |               |
| <span data-ttu-id="07bb6-149">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="07bb6-149">Solution file</span></span>                                | `sln`         |               |
| <span data-ttu-id="07bb6-150">Pagina Razor</span><span class="sxs-lookup"><span data-stu-id="07bb6-150">Razor page</span></span>                                   | `page`        |               |
| <span data-ttu-id="07bb6-151">MVC ViewImports</span><span class="sxs-lookup"><span data-stu-id="07bb6-151">MVC ViewImports</span></span>                              | `viewimports` |               |
| <span data-ttu-id="07bb6-152">MVC ViewStart</span><span class="sxs-lookup"><span data-stu-id="07bb6-152">MVC ViewStart</span></span>                                | `viewstart`   |               |

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07bb6-153">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07bb6-153">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="07bb6-154">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="07bb6-154">The command contains a default list of templates.</span></span> <span data-ttu-id="07bb6-155">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="07bb6-155">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="07bb6-156">La tabella seguente descrive i modelli preinstallati con .NET Core 1.x SDK.</span><span class="sxs-lookup"><span data-stu-id="07bb6-156">The following table shows the templates that come pre-installed with the .NET Core 1.x SDK.</span></span> <span data-ttu-id="07bb6-157">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="07bb6-157">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="07bb6-158">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="07bb6-158">Template description</span></span>  | <span data-ttu-id="07bb6-159">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="07bb6-159">Template name</span></span> | <span data-ttu-id="07bb6-160">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="07bb6-160">Languages</span></span> |
|----------------------|---------------|-----------|
| <span data-ttu-id="07bb6-161">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="07bb6-161">Console application</span></span>  | `console`     | <span data-ttu-id="07bb6-162">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="07bb6-162">[C#], F#</span></span>  |
| <span data-ttu-id="07bb6-163">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="07bb6-163">Class library</span></span>        | `classlib`    | <span data-ttu-id="07bb6-164">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="07bb6-164">[C#], F#</span></span>  |
| <span data-ttu-id="07bb6-165">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="07bb6-165">Unit test project</span></span>    | `mstest`      | <span data-ttu-id="07bb6-166">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="07bb6-166">[C#], F#</span></span>  |
| <span data-ttu-id="07bb6-167">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="07bb6-167">xUnit test project</span></span>   | `xunit`       | <span data-ttu-id="07bb6-168">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="07bb6-168">[C#], F#</span></span>  |
| <span data-ttu-id="07bb6-169">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="07bb6-169">ASP.NET Core empty</span></span>   | `web`         | <span data-ttu-id="07bb6-170">[C#]</span><span class="sxs-lookup"><span data-stu-id="07bb6-170">[C#]</span></span>      |
| <span data-ttu-id="07bb6-171">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07bb6-171">ASP.NET Core Web App</span></span> | `mvc`         | <span data-ttu-id="07bb6-172">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="07bb6-172">[C#], F#</span></span>  |
| <span data-ttu-id="07bb6-173">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="07bb6-173">ASP.NET Core Web API</span></span> | `webapi`      | <span data-ttu-id="07bb6-174">[C#]</span><span class="sxs-lookup"><span data-stu-id="07bb6-174">[C#]</span></span>      |
| <span data-ttu-id="07bb6-175">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="07bb6-175">Nuget config</span></span>         | `nugetconfig` |           |
| <span data-ttu-id="07bb6-176">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="07bb6-176">Web config</span></span>           | `webconfig`   |           |
| <span data-ttu-id="07bb6-177">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="07bb6-177">Solution file</span></span>        | `sln`         |           |

---

## <a name="options"></a><span data-ttu-id="07bb6-178">Opzioni</span><span class="sxs-lookup"><span data-stu-id="07bb6-178">Options</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="07bb6-179">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="07bb6-179">.NET Core 2.0</span></span>](#tab/netcore2x)

`--force`

<span data-ttu-id="07bb6-180">Forza la generazione del contenuto anche se ciò modifica i file esistenti.</span><span class="sxs-lookup"><span data-stu-id="07bb6-180">Forces content to be generated even if it would change existing files.</span></span> <span data-ttu-id="07bb6-181">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-181">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="07bb6-182">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="07bb6-182">Prints out help for the command.</span></span> <span data-ttu-id="07bb6-183">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-183">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-i|--install <PATH|NUGET_ID>`

<span data-ttu-id="07bb6-184">Installa un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="07bb6-184">Installs a source or template pack from the `PATH` or `NUGET_ID` provided.</span></span> <span data-ttu-id="07bb6-185">Se si vuole installare una versione provvisoria di un pacchetto di modelli, è necessario specificare la versione nel formato `<package-name>::<package-version>`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-185">If you want to install a prerelease version of a template package, you need to specify the version in the format of `<package-name>::<package-version>`.</span></span> <span data-ttu-id="07bb6-186">Per impostazione predefinita `dotnet new` passa \* per la versione, che rappresenta l'ultima versione stabile del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-186">By default, `dotnet new` passes \* for the version, which represents the last stable package version.</span></span> <span data-ttu-id="07bb6-187">Per un esempio, vedere la sezione [Esempi](#examples).</span><span class="sxs-lookup"><span data-stu-id="07bb6-187">See an example at the [Examples](#examples) section.</span></span>

<span data-ttu-id="07bb6-188">Per informazioni sulla creazione di modelli personalizzati, vedere [Modelli personalizzati per dotnet new](custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="07bb6-188">For information on creating custom templates, see [Custom templates for dotnet new](custom-templates.md).</span></span>

`-l|--list`

<span data-ttu-id="07bb6-189">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-189">Lists templates containing the specified name.</span></span> <span data-ttu-id="07bb6-190">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="07bb6-190">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="07bb6-191">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-191">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#|VB}`

<span data-ttu-id="07bb6-192">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="07bb6-192">The language of the template to create.</span></span> <span data-ttu-id="07bb6-193">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="07bb6-193">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="07bb6-194">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="07bb6-194">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="07bb6-195">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-195">The name for the created output.</span></span> <span data-ttu-id="07bb6-196">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="07bb6-196">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="07bb6-197">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-197">Location to place the generated output.</span></span> <span data-ttu-id="07bb6-198">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="07bb6-198">The default is the current directory.</span></span>

`--type`

<span data-ttu-id="07bb6-199">Filtra i modelli in base ai tipi disponibili.</span><span class="sxs-lookup"><span data-stu-id="07bb6-199">Filters templates based on available types.</span></span> <span data-ttu-id="07bb6-200">I valori predefiniti sono "project", "item" o "other".</span><span class="sxs-lookup"><span data-stu-id="07bb6-200">Predefined values are "project", "item" or "other".</span></span>

`-u|--uninstall <PATH|NUGET_ID>`

<span data-ttu-id="07bb6-201">Disinstalla un pacchetto di modelli o origine dal valore `PATH` o `NUGET_ID` fornito.</span><span class="sxs-lookup"><span data-stu-id="07bb6-201">Uninstalls a source or template pack at the `PATH` or `NUGET_ID` provided.</span></span>

> [!NOTE]
> <span data-ttu-id="07bb6-202">Per disinstallare un modello con `PATH`, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="07bb6-202">To uninstall a template using a `PATH`, you need to fully qualify the path.</span></span> <span data-ttu-id="07bb6-203">Ad esempio, *C:/Users/\<UTENTE>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="07bb6-203">For example, *C:/Users/\<USER>/Documents/Templates/GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="07bb6-204">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="07bb6-204">Additionally, do not include a final terminating directory slash on your template path.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07bb6-205">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07bb6-205">.NET Core 1.x</span></span>](#tab/netcore1x)

`-all|--show-all`

<span data-ttu-id="07bb6-206">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="07bb6-206">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="07bb6-207">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="07bb6-207">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="07bb6-208">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-208">This is required when the output directory already contains a project.</span></span>

`-h|--help`

<span data-ttu-id="07bb6-209">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="07bb6-209">Prints out help for the command.</span></span> <span data-ttu-id="07bb6-210">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-210">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="07bb6-211">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-211">Lists templates containing the specified name.</span></span> <span data-ttu-id="07bb6-212">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="07bb6-212">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="07bb6-213">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-213">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="07bb6-214">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="07bb6-214">The language of the template to create.</span></span> <span data-ttu-id="07bb6-215">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="07bb6-215">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="07bb6-216">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="07bb6-216">Not valid for some templates.</span></span>

    > [!NOTE]
    > Some shells interpret `#` as a special character. In those cases, you need to enclose the language parameter value, such as `dotnet new console -lang "F#"`.

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="07bb6-217">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-217">The name for the created output.</span></span> <span data-ttu-id="07bb6-218">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="07bb6-218">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="07bb6-219">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-219">Location to place the generated output.</span></span> <span data-ttu-id="07bb6-220">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="07bb6-220">The default is the current directory.</span></span>

---

## <a name="template-options"></a><span data-ttu-id="07bb6-221">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="07bb6-221">Template options</span></span>

<span data-ttu-id="07bb6-222">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="07bb6-222">Each project template may have additional options available.</span></span> <span data-ttu-id="07bb6-223">I modelli principali includono le opzioni aggiuntive seguenti:</span><span class="sxs-lookup"><span data-stu-id="07bb6-223">The core templates have the following additional options:</span></span>

# <a name="net-core-20tabnetcore2x"></a>[<span data-ttu-id="07bb6-224">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="07bb6-224">.NET Core 2.0</span></span>](#tab/netcore2x)

<span data-ttu-id="07bb6-225">**console, angular, react, reactredux**</span><span class="sxs-lookup"><span data-stu-id="07bb6-225">**console, angular, react, reactredux**</span></span>

  <span data-ttu-id="07bb6-226">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-226">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="07bb6-227">**classlib**</span><span class="sxs-lookup"><span data-stu-id="07bb6-227">**classlib**</span></span>

<span data-ttu-id="07bb6-228">`-f|--framework <FRAMEWORK>`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="07bb6-228">`-f|--framework <FRAMEWORK>` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="07bb6-229">Valori: `netcoreapp2.0` per creare una libreria di classi .NET Core o `netstandard2.0` per creare una libreria di classi .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="07bb6-229">Values: `netcoreapp2.0` to create a .NET Core Class Library or `netstandard2.0` to create a .NET Standard Class Library.</span></span> <span data-ttu-id="07bb6-230">Il valore predefinito è `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-230">The default value is `netstandard2.0`.</span></span>

<span data-ttu-id="07bb6-231">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-231">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="07bb6-232">**mstest, xunit**</span><span class="sxs-lookup"><span data-stu-id="07bb6-232">**mstest, xunit**</span></span>

<span data-ttu-id="07bb6-233">`-p|--enable-pack`: abilita la creazione del pacchetto per il progetto usando [dotnet pack](dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="07bb6-233">`-p|--enable-pack` - Enables packaging for the project using [dotnet pack](dotnet-pack.md).</span></span>

<span data-ttu-id="07bb6-234">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-234">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="07bb6-235">**globaljson**</span><span class="sxs-lookup"><span data-stu-id="07bb6-235">**globaljson**</span></span>

<span data-ttu-id="07bb6-236">`--sdk-version <VERSION_NUMBER>`: specifica la versione di .NET Core SDK da usare nel file *global.json*.</span><span class="sxs-lookup"><span data-stu-id="07bb6-236">`--sdk-version <VERSION_NUMBER>` - Specifies the version of the .NET Core SDK to use in the *global.json* file.</span></span>

<span data-ttu-id="07bb6-237">**web**</span><span class="sxs-lookup"><span data-stu-id="07bb6-237">**web**</span></span>

<span data-ttu-id="07bb6-238">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-238">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="07bb6-239">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-239">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="07bb6-240">**webapi**</span><span class="sxs-lookup"><span data-stu-id="07bb6-240">**webapi**</span></span>

<span data-ttu-id="07bb6-241">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="07bb6-241">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="07bb6-242">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="07bb6-242">The possible values are:</span></span>

- <span data-ttu-id="07bb6-243">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="07bb6-243">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="07bb6-244">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="07bb6-244">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="07bb6-245">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="07bb6-245">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="07bb6-246">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="07bb6-246">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="07bb6-247">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="07bb6-247">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="07bb6-248">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-248">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="07bb6-249">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-249">The default value is `https://login.microsoftonline.com/tfp/`.</span></span>

<span data-ttu-id="07bb6-250">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-250">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="07bb6-251">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-251">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="07bb6-252">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="07bb6-252">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="07bb6-253">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-253">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="07bb6-254">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-254">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="07bb6-255">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-255">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="07bb6-256">Usare con l'autenticazione `IndividualB2C` o `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-256">Use with `IndividualB2C` or `SingleOrg` authentication.</span></span> <span data-ttu-id="07bb6-257">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-257">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="07bb6-258">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="07bb6-258">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="07bb6-259">Usare con l'autenticazione `SingleOrg` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-259">Use with `SingleOrg` or `IndividualB2C` authentication.</span></span> <span data-ttu-id="07bb6-260">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-260">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="07bb6-261">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="07bb6-261">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="07bb6-262">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-262">Use with `SingleOrg` authentication.</span></span> <span data-ttu-id="07bb6-263">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-263">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="07bb6-264">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="07bb6-264">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="07bb6-265">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-265">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="07bb6-266">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-266">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="07bb6-267">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="07bb6-267">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="07bb6-268">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-268">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="07bb6-269">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-269">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="07bb6-270">**mvc, razor**</span><span class="sxs-lookup"><span data-stu-id="07bb6-270">**mvc, razor**</span></span>

<span data-ttu-id="07bb6-271">`-au|--auth <AUTHENTICATION_TYPE>`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="07bb6-271">`-au|--auth <AUTHENTICATION_TYPE>` - The type of authentication to use.</span></span> <span data-ttu-id="07bb6-272">I valori possibili sono:</span><span class="sxs-lookup"><span data-stu-id="07bb6-272">The possible values are:</span></span>

- <span data-ttu-id="07bb6-273">`None`: nessuna autenticazione (valore predefinito).</span><span class="sxs-lookup"><span data-stu-id="07bb6-273">`None` - No authentication (Default).</span></span>
- <span data-ttu-id="07bb6-274">`Individual`: autenticazione singola.</span><span class="sxs-lookup"><span data-stu-id="07bb6-274">`Individual` - Individual authentication.</span></span>
- <span data-ttu-id="07bb6-275">`IndividualB2C`: singola autenticazione con Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="07bb6-275">`IndividualB2C` - Individual authentication with Azure AD B2C.</span></span>
- <span data-ttu-id="07bb6-276">`SingleOrg`: autenticazione aziendale per un singolo tenant.</span><span class="sxs-lookup"><span data-stu-id="07bb6-276">`SingleOrg` - Organizational authentication for a single tenant.</span></span>
- <span data-ttu-id="07bb6-277">`MultiOrg`: autenticazione aziendale per più tenant.</span><span class="sxs-lookup"><span data-stu-id="07bb6-277">`MultiOrg` - Organizational authentication for multiple tenants.</span></span>
- <span data-ttu-id="07bb6-278">`Windows`: autenticazione di Windows.</span><span class="sxs-lookup"><span data-stu-id="07bb6-278">`Windows` - Windows authentication.</span></span>

<span data-ttu-id="07bb6-279">`--aad-b2c-instance <INSTANCE>`: istanza di Azure Active Directory B2C a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="07bb6-279">`--aad-b2c-instance <INSTANCE>` - The Azure Active Directory B2C instance to connect to.</span></span> <span data-ttu-id="07bb6-280">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-280">Use with `IndividualB2C` authentication.</span></span> <span data-ttu-id="07bb6-281">Il valore predefinito è `https://login.microsoftonline.com/tfp/`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-281">The default value is `https://login.microsoftonline.com/tfp/` .</span></span>

<span data-ttu-id="07bb6-282">`-ssp|--susi-policy-id <ID>`: l'ID di criteri di accesso e iscrizione per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-282">`-ssp|--susi-policy-id <ID>` - The sign-in and sign-up policy ID for this project.</span></span> <span data-ttu-id="07bb6-283">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-283">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="07bb6-284">`-rp|--reset-password-policy-id <ID>`: l'ID di criteri di reimpostazione della password per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-284">`-rp|--reset-password-policy-id <ID>` - The reset password policy ID for this project.</span></span> <span data-ttu-id="07bb6-285">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-285">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="07bb6-286">`-ep|--edit-profile-policy-id <ID>`: l'ID dei criteri del profilo di modifica per questo progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-286">`-ep|--edit-profile-policy-id <ID>` - The edit profile policy ID for this project.</span></span> <span data-ttu-id="07bb6-287">Usare con l'autenticazione `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-287">Use with `IndividualB2C` authentication.</span></span>

<span data-ttu-id="07bb6-288">`--aad-instance <INSTANCE>`: istanza di Azure Active Directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="07bb6-288">`--aad-instance <INSTANCE>` - The Azure Active Directory instance to connect to.</span></span> <span data-ttu-id="07bb6-289">Usare con l'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-289">Use with `SingleOrg` or `MultiOrg` authentication.</span></span> <span data-ttu-id="07bb6-290">Il valore predefinito è `https://login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-290">The default value is `https://login.microsoftonline.com/`.</span></span>

<span data-ttu-id="07bb6-291">`--client-id <ID>`: ID client per il progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-291">`--client-id <ID>` - The Client ID for this project.</span></span> <span data-ttu-id="07bb6-292">Usare con l'autenticazione `IndividualB2C`, `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-292">Use with `IndividualB2C`, `SingleOrg`, or `MultiOrg` authentication.</span></span> <span data-ttu-id="07bb6-293">Il valore predefinito è `11111111-1111-1111-11111111111111111`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-293">The default value is `11111111-1111-1111-11111111111111111`.</span></span>

<span data-ttu-id="07bb6-294">`--domain <DOMAIN>`: il dominio per il tenant della directory.</span><span class="sxs-lookup"><span data-stu-id="07bb6-294">`--domain <DOMAIN>` - The domain for the directory tenant.</span></span> <span data-ttu-id="07bb6-295">Usare con l'autenticazione `SingleOrg`, `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-295">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="07bb6-296">Il valore predefinito è `qualified.domain.name`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-296">The default value is `qualified.domain.name`.</span></span>

<span data-ttu-id="07bb6-297">`--tenant-id <ID>`: l'ID di tenantid all'interno della directory a cui connettersi.</span><span class="sxs-lookup"><span data-stu-id="07bb6-297">`--tenant-id <ID>` - The TenantId ID of the directory to connect to.</span></span> <span data-ttu-id="07bb6-298">Usare con l'autenticazione `SingleOrg`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-298">Use with `SingleOrg` authentication..</span></span> <span data-ttu-id="07bb6-299">Il valore predefinito è `22222222-2222-2222-2222-222222222222`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-299">The default value is `22222222-2222-2222-2222-222222222222`.</span></span>

<span data-ttu-id="07bb6-300">`--callback-path <PATH>`: il percorso della richiesta all'interno del percorso base dell'applicazione dell'URI di reindirizzamento.</span><span class="sxs-lookup"><span data-stu-id="07bb6-300">`--callback-path <PATH>` - The request path within the application's base path of the redirect URI.</span></span> <span data-ttu-id="07bb6-301">Usare con l'autenticazione `SingleOrg`, `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-301">Use with `SingleOrg` or `IndividualB2C` authentication..</span></span> <span data-ttu-id="07bb6-302">Il valore predefinito è `/signin-oidc`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-302">The default value is `/signin-oidc`.</span></span>

<span data-ttu-id="07bb6-303">`-r|--org-read-access`: consente all'applicazione l'accesso in lettura sulla directory.</span><span class="sxs-lookup"><span data-stu-id="07bb6-303">`-r|--org-read-access` - Allows this application read-access to the directory.</span></span> <span data-ttu-id="07bb6-304">Si applica solo all'autenticazione `SingleOrg` o `MultiOrg`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-304">Only applies to `SingleOrg` or `MultiOrg` authentication.</span></span>

<span data-ttu-id="07bb6-305">`--use-launch-settings`: include *launchSettings.json* nell'output del modello generato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-305">`--use-launch-settings` - Includes *launchSettings.json* in the generated template output.</span></span>

<span data-ttu-id="07bb6-306">`--use-browserlink`: include BrowserLink nel progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-306">`--use-browserlink` - Includes BrowserLink in the project.</span></span>

<span data-ttu-id="07bb6-307">`-uld|--use-local-db`: specifica che deve essere usato Local DB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="07bb6-307">`-uld|--use-local-db` - Specifies LocalDB should be used instead of SQLite.</span></span> <span data-ttu-id="07bb6-308">Si applica solo all'autenticazione `Individual` o `IndividualB2C`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-308">Only applies to `Individual` or `IndividualB2C` authentication.</span></span>

<span data-ttu-id="07bb6-309">`--no-restore`: non esegue un ripristino implicito durante la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="07bb6-309">`--no-restore` - Doesn't perform an implicit restore during project creation.</span></span>

<span data-ttu-id="07bb6-310">**page**</span><span class="sxs-lookup"><span data-stu-id="07bb6-310">**page**</span></span>

<span data-ttu-id="07bb6-311">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-311">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="07bb6-312">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-312">The default value is `MyApp.Namespace`.</span></span>

<span data-ttu-id="07bb6-313">`-np|--no-pagemodel`: crea la pagina senza un PageModel.</span><span class="sxs-lookup"><span data-stu-id="07bb6-313">`-np|--no-pagemodel` - Creates the page without a PageModel.</span></span>

<span data-ttu-id="07bb6-314">**viewimports**</span><span class="sxs-lookup"><span data-stu-id="07bb6-314">**viewimports**</span></span>

<span data-ttu-id="07bb6-315">`-na|--namespace <NAMESPACE_NAME>`: spazio dei nomi per il codice generato.</span><span class="sxs-lookup"><span data-stu-id="07bb6-315">`-na|--namespace <NAMESPACE_NAME>`- Namespace for the generated code.</span></span> <span data-ttu-id="07bb6-316">Il valore predefinito è `MyApp.Namespace`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-316">The default value is `MyApp.Namespace`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="07bb6-317">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="07bb6-317">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="07bb6-318">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="07bb6-318">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="07bb6-319">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="07bb6-319">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="07bb6-320">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-320">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="07bb6-321">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-321">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="07bb6-322">**classlib**</span><span class="sxs-lookup"><span data-stu-id="07bb6-322">**classlib**</span></span>

<span data-ttu-id="07bb6-323">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="07bb6-323">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="07bb6-324">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-324">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6`.</span></span> <span data-ttu-id="07bb6-325">Il valore predefinito è `netstandard1.4`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-325">The default value is `netstandard1.4`.</span></span>

<span data-ttu-id="07bb6-326">**mvc**</span><span class="sxs-lookup"><span data-stu-id="07bb6-326">**mvc**</span></span>

<span data-ttu-id="07bb6-327">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="07bb6-327">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="07bb6-328">Valori: `netcoreapp1.0` o `netcoreapp1.1`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-328">Values: `netcoreapp1.0` or `netcoreapp1.1`.</span></span> <span data-ttu-id="07bb6-329">Il valore predefinito è `netcoreapp1.0`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-329">The default value is `netcoreapp1.0`.</span></span>

<span data-ttu-id="07bb6-330">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="07bb6-330">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="07bb6-331">Valori: `None` o `Individual`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-331">Values: `None` or `Individual`.</span></span> <span data-ttu-id="07bb6-332">Il valore predefinito è `None`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-332">The default value is `None`.</span></span>

<span data-ttu-id="07bb6-333">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="07bb6-333">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="07bb6-334">Valori: `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-334">Values: `true` or `false`.</span></span> <span data-ttu-id="07bb6-335">Il valore predefinito è `false`.</span><span class="sxs-lookup"><span data-stu-id="07bb6-335">The default value is `false`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="07bb6-336">Esempi</span><span class="sxs-lookup"><span data-stu-id="07bb6-336">Examples</span></span>

<span data-ttu-id="07bb6-337">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="07bb6-337">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang F#`

<span data-ttu-id="07bb6-338">Creare un progetto di libreria di classi .NET Standard nella directory specificata, disponibile solo con .NET Core 2.0 SDK o versioni successive:</span><span class="sxs-lookup"><span data-stu-id="07bb6-338">Create a .NET Standard class library project in the specified directory (available only with .NET Core 2.0 SDK or later versions):</span></span>

`dotnet new classlib -lang VB -o MyLibrary`

<span data-ttu-id="07bb6-339">Creare un nuovo progetto di applicazione MVC con ASP.NET Core usando C# nella directory corrente senza autenticazione con destinazione a .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="07bb6-339">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 2.0:</span></span>

`dotnet new mvc -au None -f netcoreapp2.0`

<span data-ttu-id="07bb6-340">Creare una nuova applicazione xUnit con destinazione .NET Core 2.0:</span><span class="sxs-lookup"><span data-stu-id="07bb6-340">Create a new xUnit application targeting .NET Core 2.0:</span></span>

`dotnet new xunit --framework netcoreapp2.0`

<span data-ttu-id="07bb6-341">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="07bb6-341">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

<span data-ttu-id="07bb6-342">Installare la versione 2.0 dei modelli di applicazione a pagina singola per ASP.NET Core (opzione di comando disponibile solo per .NET Core SDK 1.1 e versioni successive):</span><span class="sxs-lookup"><span data-stu-id="07bb6-342">Install version 2.0 of the Single Page Application templates for ASP.NET Core (command option available for .NET Core SDK 1.1 and later versions only):</span></span>

`dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.0.0`

## <a name="see-also"></a><span data-ttu-id="07bb6-343">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07bb6-343">See also</span></span>

[<span data-ttu-id="07bb6-344">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="07bb6-344">Custom templates for dotnet new</span></span>](custom-templates.md)  
[<span data-ttu-id="07bb6-345">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="07bb6-345">Create a custom template for dotnet new</span></span>](~/docs/core/tutorials/create-custom-template.md)  
[<span data-ttu-id="07bb6-346">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="07bb6-346">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
[<span data-ttu-id="07bb6-347">Modelli disponibili per dotnet new</span><span class="sxs-lookup"><span data-stu-id="07bb6-347">Available templates for dotnet new</span></span>](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)
