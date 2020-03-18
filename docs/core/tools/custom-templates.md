---
title: Modelli personalizzati per dotnet new
description: Informazioni sui modelli personalizzati per qualsiasi tipo di file o progetto .NET.
author: thraka
ms.date: 06/14/2019
ms.openlocfilehash: 8e1ac4ca21a8a90ad0f7c9bd3dd11281eb4a6e02
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "73420874"
---
# <a name="custom-templates-for-dotnet-new"></a><span data-ttu-id="91ff2-103">Modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="91ff2-103">Custom templates for dotnet new</span></span>

<span data-ttu-id="91ff2-104">[.NET Core SDK](https://dotnet.microsoft.com/download) viene distribuito con molti modelli già installati e pronti per l'uso.</span><span class="sxs-lookup"><span data-stu-id="91ff2-104">The [.NET Core SDK](https://dotnet.microsoft.com/download) comes with many templates already installed and ready for you to use.</span></span> <span data-ttu-id="91ff2-105">Il [ `dotnet new` comando](dotnet-new.md) non è solo il modo di utilizzare un modello, ma anche come installare e disinstallare i modelli.</span><span class="sxs-lookup"><span data-stu-id="91ff2-105">The [`dotnet new` command](dotnet-new.md) isn't only the way to use a template, but also how to install and uninstall templates.</span></span> <span data-ttu-id="91ff2-106">A partire da .NET Core 2.0, è possibile creare modelli personalizzati per qualsiasi tipo di progetto, ad esempio un'app, un servizio, uno strumento o una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="91ff2-106">Starting with .NET Core 2.0, you can create your own custom templates for any type of project, such as an app, service, tool, or class library.</span></span> <span data-ttu-id="91ff2-107">È possibile anche creare un modello che restituisce uno o più file indipendenti, ad esempio un file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="91ff2-107">You can even create a template that outputs one or more independent files, such as a configuration file.</span></span>

<span data-ttu-id="91ff2-108">È possibile installare modelli personalizzati da un pacchetto NuGet in qualsiasi feed NuGet, facendo riferimento direttamente a un file *NGet .nupkg* o specificando una directory del file system contenente il modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-108">You can install custom templates from a NuGet package on any NuGet feed, by referencing a NuGet *.nupkg* file directly, or by specifying a file system directory that contains the template.</span></span> <span data-ttu-id="91ff2-109">Il motore del modello offre funzionalità che consentono di sostituire i valori, includere ed escludere file ed eseguire operazioni di elaborazione personalizzate quando si usa il modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-109">The template engine offers features that allow you to replace values, include and exclude files, and execute custom processing operations when your template is used.</span></span>

<span data-ttu-id="91ff2-110">Il motore del modello è open source e il repository del codice online si trova in [dotnet/templating](https://github.com/dotnet/templating/) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="91ff2-110">The template engine is open source, and the online code repository is at [dotnet/templating](https://github.com/dotnet/templating/) on GitHub.</span></span> <span data-ttu-id="91ff2-111">Visitare il repository [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) per gli esempi di modelli.</span><span class="sxs-lookup"><span data-stu-id="91ff2-111">Visit the [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) repo for samples of templates.</span></span> <span data-ttu-id="91ff2-112">Più modelli, inclusi i modelli di terze parti, sono disponibili in [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) (Modelli disponibili per dotnet new) su GitHub.</span><span class="sxs-lookup"><span data-stu-id="91ff2-112">More templates, including templates from third parties, are found at [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new) on GitHub.</span></span> <span data-ttu-id="91ff2-113">Per altre informazioni sulla creazione e l'uso di modelli personalizzati, vedere [Come creare modelli personalizzati per dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) e la [wiki del repository GitHub dotnet/templating](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="91ff2-113">For more information about creating and using custom templates, see [How to create your own templates for dotnet new](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/) and the [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="91ff2-114">Per seguire una procedura dettagliata e creare un modello, vedere l'esercitazione [Creare un modello personalizzato per dotnet new](../tutorials/cli-templates-create-item-template.md).</span><span class="sxs-lookup"><span data-stu-id="91ff2-114">To follow a walkthrough and create a template, see the [Create a custom template for dotnet new](../tutorials/cli-templates-create-item-template.md) tutorial.</span></span>

### <a name="net-default-templates"></a><span data-ttu-id="91ff2-115">Modelli predefiniti .NET</span><span class="sxs-lookup"><span data-stu-id="91ff2-115">.NET default templates</span></span>

<span data-ttu-id="91ff2-116">Quando si installa [.NET Core SDK](https://dotnet.microsoft.com/download), si riceve circa una decina di modelli predefiniti per la creazione di progetti e file, tra cui app console, librerie di classi, progetti unit test, app ASP.NET Core (inclusi i progetti [Angular](https://angular.io/) e [React](https://facebook.github.io/react/)) e file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="91ff2-116">When you install the [.NET Core SDK](https://dotnet.microsoft.com/download), you receive over a dozen built-in templates for creating projects and files, including console apps, class libraries, unit test projects, ASP.NET Core apps (including [Angular](https://angular.io/) and [React](https://facebook.github.io/react/) projects), and configuration files.</span></span> <span data-ttu-id="91ff2-117">Per elencare i modelli predefiniti, eseguire il comando `dotnet new` con l'opzione `-l|--list`:</span><span class="sxs-lookup"><span data-stu-id="91ff2-117">To list the built-in templates, run the `dotnet new` command with the `-l|--list` option:</span></span>

```dotnetcli
dotnet new --list
```

## <a name="configuration"></a><span data-ttu-id="91ff2-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="91ff2-118">Configuration</span></span>

<span data-ttu-id="91ff2-119">Un modello è costituito dai componenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="91ff2-119">A template is composed of the following parts:</span></span>

- <span data-ttu-id="91ff2-120">File e cartelle di origine.</span><span class="sxs-lookup"><span data-stu-id="91ff2-120">Source files and folders.</span></span>
- <span data-ttu-id="91ff2-121">Un file di configurazione (*template.json*).</span><span class="sxs-lookup"><span data-stu-id="91ff2-121">A configuration file (*template.json*).</span></span>

### <a name="source-files-and-folders"></a><span data-ttu-id="91ff2-122">File e cartelle di origine</span><span class="sxs-lookup"><span data-stu-id="91ff2-122">Source files and folders</span></span>

<span data-ttu-id="91ff2-123">I file e le cartelle di origine includono tutti i file e le cartelle che devono essere usati dal motore del modello quando viene eseguito il comando `dotnet new <TEMPLATE>`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-123">The source files and folders include whatever files and folders you want the template engine to use when the `dotnet new <TEMPLATE>` command is run.</span></span> <span data-ttu-id="91ff2-124">Il motore del modello è progettato per usare *progetti eseguibili* come codice sorgente per creare i progetti.</span><span class="sxs-lookup"><span data-stu-id="91ff2-124">The template engine is designed to use *runnable projects* as source code to produce projects.</span></span> <span data-ttu-id="91ff2-125">Ciò comporta diversi vantaggi:</span><span class="sxs-lookup"><span data-stu-id="91ff2-125">This has several benefits:</span></span>

- <span data-ttu-id="91ff2-126">Il motore del modello non richiede di inserire speciali token nel codice sorgente del progetto.</span><span class="sxs-lookup"><span data-stu-id="91ff2-126">The template engine doesn't require you to inject special tokens into your project's source code.</span></span>
- <span data-ttu-id="91ff2-127">I file di codice non sono file speciali o modificati in alcun modo per essere usati con il motore del modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-127">The code files aren't special files or modified in any way to work with the template engine.</span></span> <span data-ttu-id="91ff2-128">Gli strumenti usati in genere quando si usano progetti funzionano quindi anche con il contenuto del modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-128">So, the tools you normally use when working with projects also work with template content.</span></span>
- <span data-ttu-id="91ff2-129">Compilare, eseguire ed effettuare il debug dei progetti di modello, proprio come per qualsiasi altro progetto.</span><span class="sxs-lookup"><span data-stu-id="91ff2-129">You build, run, and debug your template projects just like you do for any of your other projects.</span></span>
- <span data-ttu-id="91ff2-130">È possibile creare rapidamente un modello da un progetto esistente aggiungendo semplicemente un file di configurazione *./.template.config/template.json* al progetto.</span><span class="sxs-lookup"><span data-stu-id="91ff2-130">You can quickly create a template from an existing project just by adding a *./.template.config/template.json* configuration file to the project.</span></span>

<span data-ttu-id="91ff2-131">I file e le cartelle archiviati nel modello non sono limitati ai tipi di progetto .NET formali.</span><span class="sxs-lookup"><span data-stu-id="91ff2-131">Files and folders stored in the template aren't limited to formal .NET project types.</span></span> <span data-ttu-id="91ff2-132">I file e le cartelle di origine possono essere costituiti da qualsiasi contenuto che si vuole creare quando viene usato il modello, anche se il motore del modello genera un solo file di output.</span><span class="sxs-lookup"><span data-stu-id="91ff2-132">Source files and folders may consist of any content that you wish to create when the template is used, even if the template engine produces just one file as its output.</span></span>

<span data-ttu-id="91ff2-133">I file generati dal modello possono essere modificati in base alla logica e alle impostazioni specificate nel file di configurazione *template.json*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-133">Files generated by the template can be modified based on logic and settings you've provided in the *template.json* configuration file.</span></span> <span data-ttu-id="91ff2-134">L'utente può eseguire l'override di queste impostazioni passando opzioni al comando `dotnet new <TEMPLATE>`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-134">The user can override these settings by passing options to the `dotnet new <TEMPLATE>` command.</span></span> <span data-ttu-id="91ff2-135">Un esempio comune di logica personalizzata consiste nel fornire un nome per una classe o una variabile nel file di codice che viene distribuito da un modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-135">A common example of custom logic is providing a name for a class or variable in the code file that's deployed by a template.</span></span>

### <a name="templatejson"></a><span data-ttu-id="91ff2-136">template.json</span><span class="sxs-lookup"><span data-stu-id="91ff2-136">template.json</span></span>

<span data-ttu-id="91ff2-137">Il file *template.json* si trova in una cartella *.template.config* nella directory radice del modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-137">The *template.json* file is placed in a *.template.config* folder in the root directory of the template.</span></span> <span data-ttu-id="91ff2-138">Il file fornisce informazioni di configurazione al motore del modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-138">The file provides configuration information to the template engine.</span></span> <span data-ttu-id="91ff2-139">Per la configurazione minima sono necessari i membri visualizzati nella tabella seguente, sufficiente per creare un modello funzionale.</span><span class="sxs-lookup"><span data-stu-id="91ff2-139">The minimum configuration requires the members shown in the following table, which is sufficient to create a functional template.</span></span>

| <span data-ttu-id="91ff2-140">Membro</span><span class="sxs-lookup"><span data-stu-id="91ff2-140">Member</span></span>            | <span data-ttu-id="91ff2-141">Type</span><span class="sxs-lookup"><span data-stu-id="91ff2-141">Type</span></span>          | <span data-ttu-id="91ff2-142">Descrizione</span><span class="sxs-lookup"><span data-stu-id="91ff2-142">Description</span></span> |
| ----------------- | ------------- | ----------- |
| `$schema`         | <span data-ttu-id="91ff2-143">URI</span><span class="sxs-lookup"><span data-stu-id="91ff2-143">URI</span></span>           | <span data-ttu-id="91ff2-144">Lo schema JSON per il file *template.json*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-144">The JSON schema for the *template.json* file.</span></span> <span data-ttu-id="91ff2-145">Gli editor che supportano gli schemi JSON abilitano le funzionalità di modifica JSON quando viene specificato lo schema.</span><span class="sxs-lookup"><span data-stu-id="91ff2-145">Editors that support JSON schemas enable JSON-editing features when the schema is specified.</span></span> <span data-ttu-id="91ff2-146">Ad esempio, [Visual Studio Code](https://code.visualstudio.com/) richiede questo membro per abilitare IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="91ff2-146">For example, [Visual Studio Code](https://code.visualstudio.com/) requires this member to enable IntelliSense.</span></span> <span data-ttu-id="91ff2-147">Usare un valore di `http://json.schemastore.org/template`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-147">Use a value of `http://json.schemastore.org/template`.</span></span> |
| `author`          | <span data-ttu-id="91ff2-148">string</span><span class="sxs-lookup"><span data-stu-id="91ff2-148">string</span></span>        | <span data-ttu-id="91ff2-149">L'autore del modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-149">The author of the template.</span></span> |
| `classifications` | <span data-ttu-id="91ff2-150">array(string)</span><span class="sxs-lookup"><span data-stu-id="91ff2-150">array(string)</span></span> | <span data-ttu-id="91ff2-151">Zero o più caratteristiche del modello che un utente può usare per individuare il modello durante la ricerca.</span><span class="sxs-lookup"><span data-stu-id="91ff2-151">Zero or more characteristics of the template that a user might use to find the template when searching for it.</span></span> <span data-ttu-id="91ff2-152">Le classificazioni vengono visualizzate anche nella colonna *Tags* quando viene visualizzata in un elenco di modelli generati usando il comando `dotnet new -l|--list`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-152">The classifications also appear in the *Tags* column when it appears in a list of templates produced by using the `dotnet new -l|--list` command.</span></span> |
| `identity`        | <span data-ttu-id="91ff2-153">string</span><span class="sxs-lookup"><span data-stu-id="91ff2-153">string</span></span>        | <span data-ttu-id="91ff2-154">Un nome univoco per questo modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-154">A unique name for this template.</span></span> |
| `name`            | <span data-ttu-id="91ff2-155">string</span><span class="sxs-lookup"><span data-stu-id="91ff2-155">string</span></span>        | <span data-ttu-id="91ff2-156">Il nome per il modello che verrà visualizzato agli utenti.</span><span class="sxs-lookup"><span data-stu-id="91ff2-156">The name for the template that users should see.</span></span> |
| `shortName`       | <span data-ttu-id="91ff2-157">string</span><span class="sxs-lookup"><span data-stu-id="91ff2-157">string</span></span>        | <span data-ttu-id="91ff2-158">Un nome breve predefinito per la selezione del modello che si applica agli ambienti in cui il nome del modello viene specificato dall'utente e non selezionato tramite un'interfaccia utente grafica.</span><span class="sxs-lookup"><span data-stu-id="91ff2-158">A default shorthand name for selecting the template that applies to environments where the template name is specified by the user, not selected via a GUI.</span></span> <span data-ttu-id="91ff2-159">Ad esempio, il nome breve è utile quando si usano i modelli da un prompt dei comandi con i comandi dell'interfaccia della riga di comando.</span><span class="sxs-lookup"><span data-stu-id="91ff2-159">For example, the short name is useful when using templates from a command prompt with CLI commands.</span></span> |

<span data-ttu-id="91ff2-160">Lo schema completo per il file *template.json* è disponibile nell'[archivio degli schemi JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="91ff2-160">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="91ff2-161">Per altre informazioni sul file *template.json*, vedere il [wiki sulla creazione di modelli dotnet](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="91ff2-161">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

#### <a name="example"></a><span data-ttu-id="91ff2-162">Esempio</span><span class="sxs-lookup"><span data-stu-id="91ff2-162">Example</span></span>

<span data-ttu-id="91ff2-163">Qui è ad esempio riportata la cartella di un modello che contiene due file di contenuto: *console.cs* e *readme.txt*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-163">For example, here is a template folder that contains two content files: *console.cs* and *readme.txt*.</span></span> <span data-ttu-id="91ff2-164">Si noti che è presente la cartella obbligatoria denominata *.template.config* che contiene il file *template.json*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-164">Take notice that there is the required folder named *.template.config* that contains the *template.json* file.</span></span>

```text
└───mytemplate
    │   console.cs
    │   readme.txt
    │
    └───.template.config
            template.json
```

<span data-ttu-id="91ff2-165">Il file *template.json* ha un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="91ff2-165">The *template.json* file looks like the following:</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Travis Chau",
  "classifications": [ "Common", "Console" ],
  "identity": "AdatumCorporation.ConsoleTemplate.CSharp",
  "name": "Adatum Corporation Console Application",
  "shortName": "adatumconsole"
}
```

<span data-ttu-id="91ff2-166">La cartella *mytemplate* è un pacchetto di modelli installabile.</span><span class="sxs-lookup"><span data-stu-id="91ff2-166">The *mytemplate* folder is an installable template pack.</span></span> <span data-ttu-id="91ff2-167">Dopo aver installato il pacchetto, è possibile usare `shortName` con il comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-167">Once the pack is installed, the `shortName` can be used with the `dotnet new` command.</span></span> <span data-ttu-id="91ff2-168">`dotnet new adatumconsole`, ad esempio, genera come output i file `console.cs` e `readme.txt` nella cartella corrente.</span><span class="sxs-lookup"><span data-stu-id="91ff2-168">For example, `dotnet new adatumconsole` would output the `console.cs` and `readme.txt` files to the current folder.</span></span>

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a><span data-ttu-id="91ff2-169">Compressione di un modello in un pacchetto NuGet (file nupkg)</span><span class="sxs-lookup"><span data-stu-id="91ff2-169">Packing a template into a NuGet package (nupkg file)</span></span>

<span data-ttu-id="91ff2-170">Un modello personalizzato viene compresso in un pacchetto con il comando [dotnet pack](dotnet-pack.md) e un file con estensione *csproj*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-170">A custom template is packed with the [dotnet pack](dotnet-pack.md) command and a *.csproj* file.</span></span> <span data-ttu-id="91ff2-171">In alternativa, è possibile usare [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) con il comando [nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) e un file con estensione *nuspec*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-171">Alternatively, [NuGet](https://docs.microsoft.com/nuget/tools/nuget-exe-cli-reference) can be used with the [nuget pack](https://docs.microsoft.com/nuget/tools/cli-ref-pack) command along with a *.nuspec* file.</span></span> <span data-ttu-id="91ff2-172">Per l'uso di NuGet, tuttavia, è necessario .NET Framework su Windows e [Mono](https://www.mono-project.com/) su Linux e MacOS.</span><span class="sxs-lookup"><span data-stu-id="91ff2-172">However, NuGet requires the .NET Framework on Windows and [Mono](https://www.mono-project.com/) on Linux and MacOS.</span></span>

<span data-ttu-id="91ff2-173">Il file con estensione *csproj* è leggermente diverso da un file *csproj* di un progetto di codice tradizionale.</span><span class="sxs-lookup"><span data-stu-id="91ff2-173">The *.csproj* file is slightly different from a traditional code-project *.csproj* file.</span></span> <span data-ttu-id="91ff2-174">Si notino le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="91ff2-174">Note the following settings:</span></span>

01. <span data-ttu-id="91ff2-175">È inclusa l'impostazione `<PackageType>` con il valore `Template`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-175">The `<PackageType>` setting is added and set to `Template`.</span></span>
01. <span data-ttu-id="91ff2-176">È inclusa l'impostazione `<PackageVersion>` con un [numero di versione NuGet](/nuget/reference/package-versioning) valido.</span><span class="sxs-lookup"><span data-stu-id="91ff2-176">The `<PackageVersion>` setting is added and set to a valid [NuGet version number](/nuget/reference/package-versioning).</span></span>
01. <span data-ttu-id="91ff2-177">È inclusa l'impostazione `<PackageId>` con un identificatore univoco.</span><span class="sxs-lookup"><span data-stu-id="91ff2-177">The `<PackageId>` setting is added and set to a unique identifier.</span></span> <span data-ttu-id="91ff2-178">Questo identificatore è utile per disinstallare il pacchetto di modelli e viene usato dai feed NuGet per registrare tale pacchetto.</span><span class="sxs-lookup"><span data-stu-id="91ff2-178">This identifier is used to uninstall the template pack and is used by NuGet feeds to register your template pack.</span></span>
01. <span data-ttu-id="91ff2-179">Le impostazioni dei metadati generici devono essere definite: `<Title>`, `<Authors>`, `<Description>` e `<PackageTags>`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-179">Generic metadata settings should be set: `<Title>`, `<Authors>`, `<Description>`, and `<PackageTags>`.</span></span>
01. <span data-ttu-id="91ff2-180">L'impostazione `<TargetFramework>` deve essere definita, anche se non viene usato il file binario generato dal processo del modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-180">The `<TargetFramework>` setting must be set, even though the binary produced by the template process isn't used.</span></span> <span data-ttu-id="91ff2-181">Nell'esempio seguente è definito il valore `netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-181">In the example below it's set to `netstandard2.0`.</span></span>

<span data-ttu-id="91ff2-182">Per un pacchetto di modelli, nel formato NuGet con estensione *nupkg*, è necessario che tutti i modelli siano archiviati nella cartella *content* all'interno del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="91ff2-182">A template pack, in the form of a *.nupkg* NuGet package, requires that all templates be stored in the *content* folder within the package.</span></span> <span data-ttu-id="91ff2-183">Vi sono altre impostazioni da aggiungere a un file con estensione *csproj* per assicurarsi che il file *nupkg* generato possa essere installato come pacchetto di modelli:</span><span class="sxs-lookup"><span data-stu-id="91ff2-183">There are a few more settings to add to a *.csproj* file to ensure that the generated *.nupkg* can be installed as a template pack:</span></span>

01. <span data-ttu-id="91ff2-184">L'impostazione `<IncludeContentInPack>` ha valore `true` in modo da includere qualsiasi file definito come **content** del progetto nel pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="91ff2-184">The `<IncludeContentInPack>` setting is set to `true` to include any file the project sets as **content** in the NuGet package.</span></span>
01. <span data-ttu-id="91ff2-185">L'impostazione `<IncludeBuildOutput>` ha valore `false` in modo da escludere tutti i file binari generati dal compilatore in base al pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="91ff2-185">The `<IncludeBuildOutput>` setting is set to `false` to exclude all binaries generated by the compiler from the NuGet package.</span></span>
01. <span data-ttu-id="91ff2-186">L'impostazione `<ContentTargetFolders>` ha valore `content`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-186">The `<ContentTargetFolders>` setting is set to `content`.</span></span> <span data-ttu-id="91ff2-187">Ciò consente di assicurarsi che i file impostati come **content** vengano archiviati nella cartella *content* del pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="91ff2-187">This makes sure that the files set as **content** are stored in the *content* folder in the NuGet package.</span></span> <span data-ttu-id="91ff2-188">Questa cartella del pacchetto NuGet viene analizzata dal sistema di modelli dotnet.</span><span class="sxs-lookup"><span data-stu-id="91ff2-188">This folder in the NuGet package is parsed by the dotnet template system.</span></span>

<span data-ttu-id="91ff2-189">Un modo semplice per escludere tutti i file del codice dalla compilazione in base al progetto di modello è quello di usare l'elemento `<Compile Remove="**\*" />` nel file di progetto, all'interno di un elemento `<ItemGroup>`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-189">An easy way to exclude all code files from being compiled by your template project is by using the `<Compile Remove="**\*" />` item in your project file, inside an `<ItemGroup>` element.</span></span>

<span data-ttu-id="91ff2-190">Un modo semplice per definire la struttura del pacchetto di modelli è quello di inserire tutti i modelli in singole cartelle e quindi ogni cartella di modello all'interno di una cartella *templates* che si trova nella stessa directory del file con estensione *csproj*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-190">An easy way to structure your template pack is to put all templates in individual folders, and then each template folder inside of a *templates* folder that is located in the same directory as your *.csproj* file.</span></span> <span data-ttu-id="91ff2-191">In questo modo, è possibile usare un singolo elemento di progetto per includere tutti i file e le cartelle in *templates* come **content**.</span><span class="sxs-lookup"><span data-stu-id="91ff2-191">This way, you can use a single project item to include all files and folders in the *templates* as **content**.</span></span> <span data-ttu-id="91ff2-192">All'interno di un elemento `<ItemGroup>` creare un elemento `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-192">Inside of an `<ItemGroup>` element, create a `<Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />` item.</span></span>

<span data-ttu-id="91ff2-193">Di seguito è riportato un esempio di file con estensione *csproj* in cui sono rispettate tutte le linee guida indicate sopra.</span><span class="sxs-lookup"><span data-stu-id="91ff2-193">Here is an example *.csproj* file that follows all of the guidelines above.</span></span> <span data-ttu-id="91ff2-194">Comprime la sottocartella *templates* nella cartella *content* del pacchetto ed esclude qualsiasi file di codice compilato.</span><span class="sxs-lookup"><span data-stu-id="91ff2-194">It packs the *templates* child folder to the *content* package folder and excludes any code file from being compiled.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <PackageType>Template</PackageType>
    <PackageVersion>1.0</PackageVersion>
    <PackageId>AdatumCorporation.Utility.Templates</PackageId>
    <Title>AdatumCorporation Templates</Title>
    <Authors>Me</Authors>
    <Description>Templates to use when creating an application for Adatum Corporation.</Description>
    <PackageTags>dotnet-new;templates;contoso</PackageTags>
    <TargetFramework>netstandard2.0</TargetFramework>

    <IncludeContentInPack>true</IncludeContentInPack>
    <IncludeBuildOutput>false</IncludeBuildOutput>
    <ContentTargetFolders>content</ContentTargetFolders>
  </PropertyGroup>

  <ItemGroup>
    <Content Include="templates\**\*" Exclude="templates\**\bin\**;templates\**\obj\**" />
    <Compile Remove="**\*" />
  </ItemGroup>

</Project>
```

<span data-ttu-id="91ff2-195">L'esempio seguente illustra la struttura di file e cartelle necessaria per usare un file con estensione *csproj* per creare un pacchetto di modelli.</span><span class="sxs-lookup"><span data-stu-id="91ff2-195">The example below demonstrates the file and folder structure of using a *.csproj* to create a template pack.</span></span> <span data-ttu-id="91ff2-196">Il file *MyDotnetTemplates.csproj* e la cartella *templates* si trovano entrambi nella radice di una directory denominata *project_folder*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-196">The *MyDotnetTemplates.csproj* file and *templates* folder are both located at the root of a directory named *project_folder*.</span></span> <span data-ttu-id="91ff2-197">La cartella *templates* contiene due modelli, *mytemplate1* e *mytemplate2*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-197">The *templates* folder contains two templates, *mytemplate1* and *mytemplate2*.</span></span> <span data-ttu-id="91ff2-198">Ogni modello ha file di contenuto e una cartella *.template.config* con un file di configurazione *template.json*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-198">Each template has content files and a *.template.config* folder with a *template.json* config file.</span></span>

```text
project_folder
│   MyDotnetTemplates.csproj
│
└───templates
    ├───mytemplate1
    │   │   console.cs
    │   │   readme.txt
    │   │
    │   └───.template.config
    │           template.json
    │
    └───mytemplate2
        │   otherfile.cs
        │
        └───.template.config
                template.json
```

## <a name="installing-a-template"></a><span data-ttu-id="91ff2-199">Installazione di un modello</span><span class="sxs-lookup"><span data-stu-id="91ff2-199">Installing a template</span></span>

<span data-ttu-id="91ff2-200">Per installare un pacchetto, usare il comando [dotnet new -i|--install](dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="91ff2-200">Use the [dotnet new -i|--install](dotnet-new.md) command to install a package.</span></span>

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="91ff2-201">Per installare un modello da un pacchetto NuGet archiviato in nuget.org</span><span class="sxs-lookup"><span data-stu-id="91ff2-201">To install a template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="91ff2-202">Usare l'identificatore del pacchetto NuGet per installare un pacchetto di modelli.</span><span class="sxs-lookup"><span data-stu-id="91ff2-202">Use the NuGet package identifier to install a template package.</span></span>

```dotnetcli
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a><span data-ttu-id="91ff2-203">Per installare un modello da un file nupkg locale</span><span class="sxs-lookup"><span data-stu-id="91ff2-203">To install a template from a local nupkg file</span></span>

<span data-ttu-id="91ff2-204">Specificare il percorso di un file di pacchetto NuGet con estensione *nupkg*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-204">Provide the path to a *.nupkg* NuGet package file.</span></span>

```dotnetcli
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a><span data-ttu-id="91ff2-205">Per installare un modello da una directory del file system</span><span class="sxs-lookup"><span data-stu-id="91ff2-205">To install a template from a file system directory</span></span>

<span data-ttu-id="91ff2-206">I modelli possono essere installati da una cartella di modello, come *mytemplate1* nell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="91ff2-206">Templates can be installed from a template folder, such as the *mytemplate1* folder from the example above.</span></span> <span data-ttu-id="91ff2-207">Specificare il percorso della cartella *.template.config*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-207">Specify the folder path of the *.template.config* folder.</span></span> <span data-ttu-id="91ff2-208">Il percorso della directory del modello non deve essere assoluto.</span><span class="sxs-lookup"><span data-stu-id="91ff2-208">The path to the template directory does not need to be absolute.</span></span> <span data-ttu-id="91ff2-209">Un percorso assoluto è tuttavia necessario per disinstallare un modello installato da una cartella.</span><span class="sxs-lookup"><span data-stu-id="91ff2-209">However, an absolute path is required to uninstall a template that is installed from a folder.</span></span>

```dotnetcli
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="get-a-list-of-installed-templates"></a><span data-ttu-id="91ff2-210">Ottenere un elenco dei modelli installati</span><span class="sxs-lookup"><span data-stu-id="91ff2-210">Get a list of installed templates</span></span>

<span data-ttu-id="91ff2-211">Il comando uninstall, senza altri parametri, elenca tutti i modelli installati.</span><span class="sxs-lookup"><span data-stu-id="91ff2-211">The uninstall command, without any other parameters, will list all installed templates.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="91ff2-212">Il comando restituisce un output simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="91ff2-212">That command returns something similar to the following output:</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)
  Microsoft.DotNet.Common.ProjectTemplates.3.0
    Templates:
      Class library (classlib) C#
      Class library (classlib) F#
      Class library (classlib) VB
      Console Application (console) C#
      Console Application (console) F#
      Console Application (console) VB
...
```

<span data-ttu-id="91ff2-213">Il primo livello degli elementi dopo `Currently installed items:` è costituito dagli identificatori usati nella disinstallazione di un modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-213">The first level of items after `Currently installed items:` are the identifiers used in uninstalling a template.</span></span> <span data-ttu-id="91ff2-214">Nell'esempio precedente sono elencati `Microsoft.DotNet.Common.ItemTemplates` e `Microsoft.DotNet.Common.ProjectTemplates.3.0`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-214">And in the example above, `Microsoft.DotNet.Common.ItemTemplates` and `Microsoft.DotNet.Common.ProjectTemplates.3.0` are listed.</span></span> <span data-ttu-id="91ff2-215">Se il modello è stato installato usando un percorso del file system, questo identificatore corrisponde al percorso della cartella *.template.config*.</span><span class="sxs-lookup"><span data-stu-id="91ff2-215">If the template was installed by using a file system path, this identifier will the folder path of the *.template.config* folder.</span></span>

## <a name="uninstalling-a-template"></a><span data-ttu-id="91ff2-216">Disinstallazione di un modello</span><span class="sxs-lookup"><span data-stu-id="91ff2-216">Uninstalling a template</span></span>

<span data-ttu-id="91ff2-217">Per disinstallare un pacchetto, usare il comando [dotnet new -u|--uninstall](dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="91ff2-217">Use the [dotnet new -u|--uninstall](dotnet-new.md) command to uninstall a package.</span></span>

<span data-ttu-id="91ff2-218">Se il pacchetto è stato installato tramite un feed NuGet o direttamente da un file con estensione *nupkg*, specificare l'identificatore.</span><span class="sxs-lookup"><span data-stu-id="91ff2-218">If the package was installed by either a NuGet feed or by a *.nupkg* file directly, provide the identifier.</span></span>

```dotnetcli
dotnet new -u <NUGET_PACKAGE_ID>
```

<span data-ttu-id="91ff2-219">Se il pacchetto è stato installato specificando un percorso per la cartella *.template.config*, usare tale percorso **assoluto** per disinstallare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="91ff2-219">If the package was installed by specifying a path to the *.template.config* folder, use that **absolute** path to uninstall the package.</span></span> <span data-ttu-id="91ff2-220">È possibile visualizzare il percorso assoluto del modello nell'output generato dal comando `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="91ff2-220">You can see the absolute path of the template in the output provided by the `dotnet new -u` command.</span></span> <span data-ttu-id="91ff2-221">Per altre informazioni, vedere la sezione precedente [Ottenere un elenco dei modelli installati](#get-a-list-of-installed-templates).</span><span class="sxs-lookup"><span data-stu-id="91ff2-221">For more information, see the [Get a list of installed templates](#get-a-list-of-installed-templates) section above.</span></span>

```dotnetcli
dotnet new -u <ABSOLUTE_FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a><span data-ttu-id="91ff2-222">Creare un progetto usando un modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="91ff2-222">Create a project using a custom template</span></span>

<span data-ttu-id="91ff2-223">Dopo l'installazione di un modello, usare il modello eseguendo il comando `dotnet new <TEMPLATE>` come si farebbe con qualsiasi altro modello pre-installato.</span><span class="sxs-lookup"><span data-stu-id="91ff2-223">After a template is installed, use the template by executing the `dotnet new <TEMPLATE>` command as you would with any other pre-installed template.</span></span> <span data-ttu-id="91ff2-224">È possibile anche specificare [options](dotnet-new.md#options) per il comando `dotnet new`, includendo le opzioni specifiche del modello configurate nelle impostazioni del modello.</span><span class="sxs-lookup"><span data-stu-id="91ff2-224">You can also specify [options](dotnet-new.md#options) to the `dotnet new` command, including template-specific options you configured in the template settings.</span></span> <span data-ttu-id="91ff2-225">Specificare il nome breve del modello direttamente nel comando:</span><span class="sxs-lookup"><span data-stu-id="91ff2-225">Supply the template's short name directly to the command:</span></span>

```dotnetcli
dotnet new <TEMPLATE>
```

## <a name="see-also"></a><span data-ttu-id="91ff2-226">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="91ff2-226">See also</span></span>

- [<span data-ttu-id="91ff2-227">Creare un modello personalizzato per dotnet new (esercitazione)</span><span class="sxs-lookup"><span data-stu-id="91ff2-227">Create a custom template for dotnet new (tutorial)</span></span>](../tutorials/cli-templates-create-item-template.md)
- [<span data-ttu-id="91ff2-228">Wiki del repository GitHub dotnet/templating</span><span class="sxs-lookup"><span data-stu-id="91ff2-228">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)
- [<span data-ttu-id="91ff2-229">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="91ff2-229">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)
- [<span data-ttu-id="91ff2-230">Come creare modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="91ff2-230">How to create your own templates for dotnet new</span></span>](https://devblogs.microsoft.com/dotnet/how-to-create-your-own-templates-for-dotnet-new/)
- <span data-ttu-id="91ff2-231">Lo schema [*template.JSON* nell'archivio di schemi JSON](http://json.schemastore.org/template)</span><span class="sxs-lookup"><span data-stu-id="91ff2-231">[*template.json* schema at the JSON Schema Store](http://json.schemastore.org/template)</span></span>
