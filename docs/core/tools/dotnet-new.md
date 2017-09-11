---
title: Comando dotnet-new - Interfaccia della riga di comando di .NET Core
description: Il comando dotnet-new consente di creare nuovi progetti .NET Core nella directory corrente.
keywords: dotnet-new, interfaccia della riga di comando, comando dell'interfaccia della riga di comando, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 56033295b2448b045d5a51dbd84d5429aed77451
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-new"></a><span data-ttu-id="3f3d0-104">dotnet-new</span><span class="sxs-lookup"><span data-stu-id="3f3d0-104">dotnet-new</span></span>

## <a name="name"></a><span data-ttu-id="3f3d0-105">Nome</span><span class="sxs-lookup"><span data-stu-id="3f3d0-105">Name</span></span>

<span data-ttu-id="3f3d0-106">`dotnet-new`: crea un nuovo progetto, un file di configurazione o una soluzione sulla base del modello specificato.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-106">`dotnet-new` - Creates a new project, configuration file, or solution based on the specified template.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3f3d0-107">Riepilogo</span><span class="sxs-lookup"><span data-stu-id="3f3d0-107">Synopsis</span></span>

```
dotnet new <TEMPLATE> [-lang|--language] [-n|--name] [-o|--output] [-all|--show-all] [-h|--help] [Template options]
dotnet new <TEMPLATE> [-l|--list]
dotnet new [-all|--show-all]
dotnet new [-h|--help]
```

## <a name="description"></a><span data-ttu-id="3f3d0-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f3d0-108">Description</span></span>

<span data-ttu-id="3f3d0-109">Il comando `dotnet new` rappresenta un modo pratico per inizializzare un progetto .NET Core valido.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-109">The `dotnet new` command provides a convenient way to initialize a valid .NET Core project.</span></span> 

<span data-ttu-id="3f3d0-110">Questo comando chiama il [motore del modello](https://github.com/dotnet/templating) per creare gli elementi su disco in base alle opzioni e al modello specificati.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-110">The command calls the [template engine](https://github.com/dotnet/templating) to create the artifacts on disk based on the specified template and options.</span></span>

## <a name="arguments"></a><span data-ttu-id="3f3d0-111">Argomenti</span><span class="sxs-lookup"><span data-stu-id="3f3d0-111">Arguments</span></span>

`TEMPLATE`

<span data-ttu-id="3f3d0-112">Modello di cui creare un'istanza quando viene richiamato il comando.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-112">The template to instantiate when the command is invoked.</span></span> <span data-ttu-id="3f3d0-113">Ogni modello può avere opzioni specifiche che è possibile passare.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-113">Each template might have specific options you can pass.</span></span> <span data-ttu-id="3f3d0-114">Per altre informazioni, vedere [Opzioni del modello](#template-options).</span><span class="sxs-lookup"><span data-stu-id="3f3d0-114">For more information, see [Template options](#template-options).</span></span>

<span data-ttu-id="3f3d0-115">Il comando contiene un elenco predefinito di modelli.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-115">The command contains a default list of templates.</span></span> <span data-ttu-id="3f3d0-116">Usare `dotnet new -all` per ottenere un elenco dei modelli disponibili.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-116">Use `dotnet new -all` to obtain a list of the available templates.</span></span> <span data-ttu-id="3f3d0-117">La tabella seguente descrive i modelli preinstallati nell'SDK.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-117">The following table shows the templates that come pre-installed with the SDK.</span></span> <span data-ttu-id="3f3d0-118">Il linguaggio predefinito per il modello è indicato tra parentesi quadre.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-118">The default language for the template is shown inside the brackets.</span></span>

|<span data-ttu-id="3f3d0-119">Descrizione del modello</span><span class="sxs-lookup"><span data-stu-id="3f3d0-119">Template description</span></span>  | <span data-ttu-id="3f3d0-120">Nome del modello</span><span class="sxs-lookup"><span data-stu-id="3f3d0-120">Template name</span></span>  | <span data-ttu-id="3f3d0-121">Linguaggi</span><span class="sxs-lookup"><span data-stu-id="3f3d0-121">Languages</span></span> |
|----------------------|----------------|-----------|
| <span data-ttu-id="3f3d0-122">Applicazione console</span><span class="sxs-lookup"><span data-stu-id="3f3d0-122">Console application</span></span>  | <span data-ttu-id="3f3d0-123">console</span><span class="sxs-lookup"><span data-stu-id="3f3d0-123">console</span></span>        | <span data-ttu-id="3f3d0-124">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3f3d0-124">[C#], F#</span></span>  |
| <span data-ttu-id="3f3d0-125">Libreria di classi</span><span class="sxs-lookup"><span data-stu-id="3f3d0-125">Class library</span></span>        | <span data-ttu-id="3f3d0-126">classlib</span><span class="sxs-lookup"><span data-stu-id="3f3d0-126">classlib</span></span>       | <span data-ttu-id="3f3d0-127">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3f3d0-127">[C#], F#</span></span>  |
| <span data-ttu-id="3f3d0-128">Progetto di unit test</span><span class="sxs-lookup"><span data-stu-id="3f3d0-128">Unit test project</span></span>    | <span data-ttu-id="3f3d0-129">mstest</span><span class="sxs-lookup"><span data-stu-id="3f3d0-129">mstest</span></span>         | <span data-ttu-id="3f3d0-130">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3f3d0-130">[C#], F#</span></span>  |
| <span data-ttu-id="3f3d0-131">Progetto di xUnit test</span><span class="sxs-lookup"><span data-stu-id="3f3d0-131">xUnit test project</span></span>   | <span data-ttu-id="3f3d0-132">xunit</span><span class="sxs-lookup"><span data-stu-id="3f3d0-132">xunit</span></span>          | <span data-ttu-id="3f3d0-133">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3f3d0-133">[C#], F#</span></span>  |
| <span data-ttu-id="3f3d0-134">ASP.NET Core vuoto</span><span class="sxs-lookup"><span data-stu-id="3f3d0-134">ASP.NET Core empty</span></span>   | <span data-ttu-id="3f3d0-135">Web</span><span class="sxs-lookup"><span data-stu-id="3f3d0-135">web</span></span>            | <span data-ttu-id="3f3d0-136">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f3d0-136">[C#]</span></span>      |
| <span data-ttu-id="3f3d0-137">App Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f3d0-137">ASP.NET Core web app</span></span> | <span data-ttu-id="3f3d0-138">mvc</span><span class="sxs-lookup"><span data-stu-id="3f3d0-138">mvc</span></span>            | <span data-ttu-id="3f3d0-139">[C#], F#</span><span class="sxs-lookup"><span data-stu-id="3f3d0-139">[C#], F#</span></span>  |
| <span data-ttu-id="3f3d0-140">API Web ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3f3d0-140">ASP.NET Core web api</span></span> | <span data-ttu-id="3f3d0-141">webapi</span><span class="sxs-lookup"><span data-stu-id="3f3d0-141">webapi</span></span>         | <span data-ttu-id="3f3d0-142">[C#]</span><span class="sxs-lookup"><span data-stu-id="3f3d0-142">[C#]</span></span>      |
| <span data-ttu-id="3f3d0-143">Configurazione Nuget</span><span class="sxs-lookup"><span data-stu-id="3f3d0-143">Nuget config</span></span>         | <span data-ttu-id="3f3d0-144">nugetconfig</span><span class="sxs-lookup"><span data-stu-id="3f3d0-144">nugetconfig</span></span>    |           |
| <span data-ttu-id="3f3d0-145">Configurazione Web</span><span class="sxs-lookup"><span data-stu-id="3f3d0-145">Web config</span></span>           | <span data-ttu-id="3f3d0-146">webconfig</span><span class="sxs-lookup"><span data-stu-id="3f3d0-146">webconfig</span></span>      |           |
| <span data-ttu-id="3f3d0-147">File di soluzione</span><span class="sxs-lookup"><span data-stu-id="3f3d0-147">Solution file</span></span>        | <span data-ttu-id="3f3d0-148">sln</span><span class="sxs-lookup"><span data-stu-id="3f3d0-148">sln</span></span>            |           |

## <a name="options"></a><span data-ttu-id="3f3d0-149">Opzioni</span><span class="sxs-lookup"><span data-stu-id="3f3d0-149">Options</span></span>

`-h|--help`

<span data-ttu-id="3f3d0-150">Stampa la Guida per il comando.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-150">Prints out help for the command.</span></span> <span data-ttu-id="3f3d0-151">Può essere richiamato per il comando `dotnet new` stesso o per qualsiasi modello, ad esempio `dotnet new mvc --help`.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-151">It can be invoked for the `dotnet new` command itself or for any template, such as `dotnet new mvc --help`.</span></span>

`-l|--list`

<span data-ttu-id="3f3d0-152">Elenca i modelli contenenti il nome specificato.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-152">Lists templates containing the specified name.</span></span> <span data-ttu-id="3f3d0-153">Se richiamato per il comando `dotnet new`, elenca i possibili modelli disponibili per la directory specificata.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-153">If invoked for the `dotnet new` command, it lists the possible templates available for the given directory.</span></span> <span data-ttu-id="3f3d0-154">Se ad esempio la directory contiene già un progetto, non elenca tutti i modelli di progetto.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-154">For example if the directory already contains a project, it doesn't list all project templates.</span></span>

`-lang|--language {C#|F#}`

<span data-ttu-id="3f3d0-155">Linguaggio del modello da creare.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-155">The language of the template to create.</span></span> <span data-ttu-id="3f3d0-156">Il linguaggio accettato varia a seconda del modello. Vedere i valori predefiniti nella sezione [Argomenti](#arguments).</span><span class="sxs-lookup"><span data-stu-id="3f3d0-156">The language accepted varies by the template (see defaults in the [arguments](#arguments) section).</span></span> <span data-ttu-id="3f3d0-157">Non è valido per alcuni modelli.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-157">Not valid for some templates.</span></span>

`-n|--name <OUTPUT_NAME>`

<span data-ttu-id="3f3d0-158">Nome dell'output creato.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-158">The name for the created output.</span></span> <span data-ttu-id="3f3d0-159">Se non viene specificato alcun nome, viene usato il nome della directory corrente.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-159">If no name is specified, the name of the current directory is used.</span></span>

`-o|--output <OUTPUT_DIRECTORY>`

<span data-ttu-id="3f3d0-160">Percorso in cui posizionare l'output generato.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-160">Location to place the generated output.</span></span> <span data-ttu-id="3f3d0-161">Il valore predefinito è la directory corrente.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-161">The default is the current directory.</span></span>

`-all|--show-all`

<span data-ttu-id="3f3d0-162">Mostra tutti i modelli per un tipo di progetto specifico durante l'esecuzione nel contesto del comando `dotnet new` senza altri elementi.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-162">Shows all templates for a specific type of project when running in the context of the `dotnet new` command alone.</span></span> <span data-ttu-id="3f3d0-163">Durante l'esecuzione nel contesto di un modello specifico, ad esempio `dotnet new web -all`, `-all` viene interpretato come un flag di imposizione della creazione.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-163">When running in the context of a specific template, such as `dotnet new web -all`, `-all` is interpreted as a force creation flag.</span></span> <span data-ttu-id="3f3d0-164">Questo è necessario quando la directory di output contiene già un progetto.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-164">This is required when the output directory already contains a project.</span></span>

## <a name="template-options"></a><span data-ttu-id="3f3d0-165">Opzioni del modello</span><span class="sxs-lookup"><span data-stu-id="3f3d0-165">Template options</span></span>

<span data-ttu-id="3f3d0-166">Per ogni modello di progetto potrebbero essere disponibili opzioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-166">Each project template may have additional options available.</span></span> <span data-ttu-id="3f3d0-167">I modelli principali includono le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3f3d0-167">The core templates have the following options:</span></span>

<span data-ttu-id="3f3d0-168">**console, xunit, mstest, web, webapi**</span><span class="sxs-lookup"><span data-stu-id="3f3d0-168">**console, xunit, mstest, web, webapi**</span></span>

<span data-ttu-id="3f3d0-169">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-169">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3f3d0-170">Valori: `netcoreapp1.0` o `netcoreapp1.1` (impostazione predefinita: `netcoreapp1.0`)</span><span class="sxs-lookup"><span data-stu-id="3f3d0-170">Values: `netcoreapp1.0` or `netcoreapp1.1` (Default: `netcoreapp1.0`)</span></span>

<span data-ttu-id="3f3d0-171">**mvc**</span><span class="sxs-lookup"><span data-stu-id="3f3d0-171">**mvc**</span></span>

<span data-ttu-id="3f3d0-172">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-172">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3f3d0-173">Valori: `netcoreapp1.0` o `netcoreapp1.1` (`Default: netcoreapp1.0`)</span><span class="sxs-lookup"><span data-stu-id="3f3d0-173">Values: `netcoreapp1.0` or `netcoreapp1.1` (`Default: netcoreapp1.0`)</span></span>

<span data-ttu-id="3f3d0-174">`-au|--auth`: tipo di autenticazione da usare.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-174">`-au|--auth` - The type of authentication to use.</span></span> <span data-ttu-id="3f3d0-175">Valori: `None` o `Individual` (impostazione predefinita: `None`)</span><span class="sxs-lookup"><span data-stu-id="3f3d0-175">Values: `None` or `Individual` (Default: `None`)</span></span>

<span data-ttu-id="3f3d0-176">`-uld|--use-local-db`: indica se usare o meno LocalDB invece di SQLite.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-176">`-uld|--use-local-db` - Specifies whether or not to use LocalDB instead of SQLite.</span></span> <span data-ttu-id="3f3d0-177">Valori: `true` o `false` (impostazione predefinita: `false`)</span><span class="sxs-lookup"><span data-stu-id="3f3d0-177">Values: `true` or `false` (Default: `false`)</span></span>

<span data-ttu-id="3f3d0-178">**classlib**</span><span class="sxs-lookup"><span data-stu-id="3f3d0-178">**classlib**</span></span>

<span data-ttu-id="3f3d0-179">`-f|--framework`: specifica il [framework](../../standard/frameworks.md) di destinazione.</span><span class="sxs-lookup"><span data-stu-id="3f3d0-179">`-f|--framework` - Specifies the [framework](../../standard/frameworks.md) to target.</span></span> <span data-ttu-id="3f3d0-180">Valori: `netcoreapp1.0`, `netcoreapp1.1` o da `netstandard1.0` a `netstandard1.6` (impostazione predefinita: `netstandard1.4`)</span><span class="sxs-lookup"><span data-stu-id="3f3d0-180">Values: `netcoreapp1.0`, `netcoreapp1.1`, or `netstandard1.0` to `netstandard1.6` (Default: `netstandard1.4`)</span></span>

## <a name="examples"></a><span data-ttu-id="3f3d0-181">Esempi</span><span class="sxs-lookup"><span data-stu-id="3f3d0-181">Examples</span></span>

<span data-ttu-id="3f3d0-182">Creare un progetto di applicazione console F# nella directory corrente:</span><span class="sxs-lookup"><span data-stu-id="3f3d0-182">Create an F# console application project in the current directory:</span></span>

`dotnet new console -lang f#` 
   
<span data-ttu-id="3f3d0-183">Creare un nuovo progetto di applicazione MVC ASP.NET Core C# nella directory corrente senza autenticazione con destinazione .NET Core 1.0:</span><span class="sxs-lookup"><span data-stu-id="3f3d0-183">Create a new ASP.NET Core C# MVC application project in the current directory with no authentication targeting .NET Core 1.0:</span></span>  

`dotnet new mvc -au None -f netcoreapp1.0`
 
<span data-ttu-id="3f3d0-184">Creare una nuova applicazione xUnit con destinazione .NET Core 1.1:</span><span class="sxs-lookup"><span data-stu-id="3f3d0-184">Create a new xUnit application targeting .NET Core 1.1:</span></span>

`dotnet new xunit --framework netcoreapp1.1`

<span data-ttu-id="3f3d0-185">Elencare tutti i modelli disponibili per MVC:</span><span class="sxs-lookup"><span data-stu-id="3f3d0-185">List all templates available for MVC:</span></span>

`dotnet new mvc -l`

