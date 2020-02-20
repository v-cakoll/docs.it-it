---
title: Creare un modello di progetto per dotnet new
description: Informazioni su come creare un modello di progetto per il comando dotnet new.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: f53f4037f832265a35f65bf2e5096c7e5a37bcf1
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503528"
---
# <a name="tutorial-create-a-project-template"></a><span data-ttu-id="c5222-103">Esercitazione: creare un modello di progetto</span><span class="sxs-lookup"><span data-stu-id="c5222-103">Tutorial: Create a project template</span></span>

<span data-ttu-id="c5222-104">Con .NET Core è possibile creare e distribuire modelli per generare progetti, file e persino risorse.</span><span class="sxs-lookup"><span data-stu-id="c5222-104">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="c5222-105">Questa esercitazione è la seconda parte di una serie che illustra come creare, installare e disinstallare i modelli da usare con il comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="c5222-105">This tutorial is part two of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="c5222-106">In questa parte della serie si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="c5222-106">In this part of the series you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="c5222-107">Creare le risorse di un modello di progetto</span><span class="sxs-lookup"><span data-stu-id="c5222-107">Create the resources of a project template</span></span>
> * <span data-ttu-id="c5222-108">Creare la cartella e il file di configurazione del modello</span><span class="sxs-lookup"><span data-stu-id="c5222-108">Create the template config folder and file</span></span>
> * <span data-ttu-id="c5222-109">Installare un modello da un percorso di file</span><span class="sxs-lookup"><span data-stu-id="c5222-109">Install a template from a file path</span></span>
> * <span data-ttu-id="c5222-110">Testare un modello di elemento</span><span class="sxs-lookup"><span data-stu-id="c5222-110">Test an item template</span></span>
> * <span data-ttu-id="c5222-111">Disinstallare un modello di elemento</span><span class="sxs-lookup"><span data-stu-id="c5222-111">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c5222-112">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="c5222-112">Prerequisites</span></span>

* <span data-ttu-id="c5222-113">Completare la [parte 1](cli-templates-create-item-template.md) di questa serie di esercitazioni.</span><span class="sxs-lookup"><span data-stu-id="c5222-113">Complete [part 1](cli-templates-create-item-template.md) of this tutorial series.</span></span>
* <span data-ttu-id="c5222-114">Aprire un terminale e passare alla cartella _working\templates_</span><span class="sxs-lookup"><span data-stu-id="c5222-114">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-a-project-template"></a><span data-ttu-id="c5222-115">Creare un modello di progetto</span><span class="sxs-lookup"><span data-stu-id="c5222-115">Create a project template</span></span>

<span data-ttu-id="c5222-116">I modelli di progetto producono progetti pronti per l'esecuzione che consentono agli utenti di iniziare in modo facile a utilizzare un working set di codice.</span><span class="sxs-lookup"><span data-stu-id="c5222-116">Project templates produce ready-to-run projects that make it easy for users to start with a working set of code.</span></span> <span data-ttu-id="c5222-117">.NET Core include alcuni modelli di progetto, ad esempio un'applicazione console o una libreria di classi.</span><span class="sxs-lookup"><span data-stu-id="c5222-117">.NET Core includes a few project templates such as a console application or a class library.</span></span> <span data-ttu-id="c5222-118">In questo esempio verrà creato un nuovo progetto console che abilita C# 8.0 e produce un punto di ingresso `async main`.</span><span class="sxs-lookup"><span data-stu-id="c5222-118">In this example, you'll create a new console project that enables C# 8.0 and produces an `async main` entry point.</span></span>

<span data-ttu-id="c5222-119">Nel terminale passare alla cartella _working\templates_ e creare una nuova sottocartella denominata _consoleasync_.</span><span class="sxs-lookup"><span data-stu-id="c5222-119">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _consoleasync_.</span></span> <span data-ttu-id="c5222-120">Immettere la sottocartella ed eseguire `dotnet new console` per generare l'applicazione console standard.</span><span class="sxs-lookup"><span data-stu-id="c5222-120">Enter the subfolder and run `dotnet new console` to generate the standard console application.</span></span> <span data-ttu-id="c5222-121">Verranno modificati i file prodotti da questo modello per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="c5222-121">You'll be editing the files produced by this template to create a new template.</span></span>

```console
working
└───templates
    └───consoleasync
            consoleasync.csproj
            Program.cs
```

## <a name="modify-programcs"></a><span data-ttu-id="c5222-122">Modificare Program.cs</span><span class="sxs-lookup"><span data-stu-id="c5222-122">Modify Program.cs</span></span>

<span data-ttu-id="c5222-123">Aprire il file _program.cs_.</span><span class="sxs-lookup"><span data-stu-id="c5222-123">Open up the _program.cs_ file.</span></span> <span data-ttu-id="c5222-124">Il progetto console non usa un punto di ingresso asincrono, quindi è consigliabile aggiungerlo.</span><span class="sxs-lookup"><span data-stu-id="c5222-124">The console project doesn't use an asynchronous entry point, so let's add that.</span></span> <span data-ttu-id="c5222-125">Modificare il codice nel modo seguente e salvare il file.</span><span class="sxs-lookup"><span data-stu-id="c5222-125">Change your code to the following and save the file.</span></span>

```csharp
using System;
using System.Threading.Tasks;

namespace consoleasync
{
    class Program
    {
        static async Task Main(string[] args)
        {
            await Console.Out.WriteAsync("Hello World with C# 8.0!");
        }
    }
}
```

## <a name="modify-consoleasynccsproj"></a><span data-ttu-id="c5222-126">Modificare consoleasync.csproj</span><span class="sxs-lookup"><span data-stu-id="c5222-126">Modify consoleasync.csproj</span></span>

<span data-ttu-id="c5222-127">La versione del linguaggio C# usata dal progetto verrà ora aggiornata alla versione 8.0.</span><span class="sxs-lookup"><span data-stu-id="c5222-127">Let's update the C# language version the project uses to version 8.0.</span></span> <span data-ttu-id="c5222-128">Modificare il file _consoleasync.csproj_ e aggiungere l'impostazione `<LangVersion>` a un nodo `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="c5222-128">Edit the _consoleasync.csproj_ file and add the `<LangVersion>` setting to a `<PropertyGroup>` node.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.2</TargetFramework>

    <LangVersion>8.0</LangVersion>

  </PropertyGroup>
  
</Project>
```

## <a name="build-the-project"></a><span data-ttu-id="c5222-129">Compilare il progetto</span><span class="sxs-lookup"><span data-stu-id="c5222-129">Build the project</span></span>

<span data-ttu-id="c5222-130">Prima di completare un modello di progetto, è necessario testarlo per assicurarsi che venga compilato ed eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="c5222-130">Before you complete a project template, you should test it to make sure it compiles and runs correctly.</span></span>

<span data-ttu-id="c5222-131">Nel terminale eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="c5222-131">In your terminal, run the following command.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="c5222-132">Si ottiene l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="c5222-132">You get the following output.</span></span>

```console
Hello World with C# 8.0!
```

<span data-ttu-id="c5222-133">È possibile eliminare le cartelle _obj_ e _bin_ create usando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="c5222-133">You can delete the _obj_ and _bin_ folders created by using `dotnet run`.</span></span> <span data-ttu-id="c5222-134">L'eliminazione di questi file garantisce che il modello includa solo i file correlati al modello e non tutti i file che risultano da un'azione di compilazione.</span><span class="sxs-lookup"><span data-stu-id="c5222-134">Deleting these files ensures your template only includes the files related to your template and not any files that result of a build action.</span></span>

<span data-ttu-id="c5222-135">Ora che è stato creato il contenuto del modello, è necessario creare la configurazione del modello nella cartella radice del modello.</span><span class="sxs-lookup"><span data-stu-id="c5222-135">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="c5222-136">Crea la configurazione del modello</span><span class="sxs-lookup"><span data-stu-id="c5222-136">Create the template config</span></span>

<span data-ttu-id="c5222-137">I modelli sono riconosciuti in .NET Core grazie a una cartella e a un file di configurazione speciali disponibili nella radice del modello.</span><span class="sxs-lookup"><span data-stu-id="c5222-137">Templates are recognized in .NET Core by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="c5222-138">In questa esercitazione la cartella dei modelli si trova in _working\templates\consoleasync_.</span><span class="sxs-lookup"><span data-stu-id="c5222-138">In this tutorial, your template folder is located at _working\templates\consoleasync_.</span></span>

<span data-ttu-id="c5222-139">Quando si crea un modello, tutti i file e le cartelle nella cartella del modello vengono inclusi come parte del modello, ad eccezione della cartella di configurazione speciale.</span><span class="sxs-lookup"><span data-stu-id="c5222-139">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="c5222-140">Questa cartella di configurazione è denominata _.template.config_.</span><span class="sxs-lookup"><span data-stu-id="c5222-140">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="c5222-141">Per prima cosa, creare una nuova sottocartella denominata _.template.config_ e aprirla.</span><span class="sxs-lookup"><span data-stu-id="c5222-141">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="c5222-142">Creare quindi un nuovo file denominato _template.json_.</span><span class="sxs-lookup"><span data-stu-id="c5222-142">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="c5222-143">La struttura di cartelle dovrebbe essere simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="c5222-143">Your folder structure should look like this.</span></span>

```console
working
└───templates
    └───consoleasync
        └───.template.config
                template.json
```

<span data-ttu-id="c5222-144">Aprire il file _template. JSON_ con l'editor di testo preferito e incollare il codice JSON seguente e salvarlo.</span><span class="sxs-lookup"><span data-stu-id="c5222-144">Open the _template.json_ with your favorite text editor and paste in the following json code and save it.</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Console", "C#8" ],
  "identity": "ExampleTemplate.AsyncProject",
  "name": "Example templates: async project",
  "shortName": "consoleasync",
  "tags": {
    "language": "C#",
    "type": "project"
  }
}
```

<span data-ttu-id="c5222-145">Questo file di configurazione contiene tutte le impostazioni per il modello.</span><span class="sxs-lookup"><span data-stu-id="c5222-145">This config file contains all of the settings for your template.</span></span> <span data-ttu-id="c5222-146">È possibile visualizzare le impostazioni di base, ad esempio `name` e `shortName`, ma anche un valore `tags/type` impostato su `project`.</span><span class="sxs-lookup"><span data-stu-id="c5222-146">You can see the basic settings such as `name` and `shortName` but also there's a `tags/type` value that's set to `project`.</span></span> <span data-ttu-id="c5222-147">Questo valore designa il modello come modello di progetto.</span><span class="sxs-lookup"><span data-stu-id="c5222-147">This designates your template as a project template.</span></span> <span data-ttu-id="c5222-148">Non esiste alcuna restrizione per il tipo di modello che si può creare.</span><span class="sxs-lookup"><span data-stu-id="c5222-148">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="c5222-149">I valori `item` e `project` sono nomi comuni consigliati da .NET Core in modo che gli utenti possano filtrare facilmente il tipo di modello per eventuali ricerche.</span><span class="sxs-lookup"><span data-stu-id="c5222-149">The `item` and `project` values are common names that .NET Core recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="c5222-150">L'elemento `classifications` rappresenta la colonna **tags** visualizzata quando si esegue `dotnet new` e si ottiene un elenco di modelli.</span><span class="sxs-lookup"><span data-stu-id="c5222-150">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="c5222-151">Gli utenti possono anche eseguire ricerche in base ai tag di classificazione.</span><span class="sxs-lookup"><span data-stu-id="c5222-151">Users can also search based on classification tags.</span></span> <span data-ttu-id="c5222-152">Non confondere la proprietà `tags` nel file JSON con l'elenco dei tag `classifications`.</span><span class="sxs-lookup"><span data-stu-id="c5222-152">Don't confuse the `tags` property in the json file with the `classifications` tags list.</span></span> <span data-ttu-id="c5222-153">Si tratta di due cose diverse, sfortunatamente con nomi simili.</span><span class="sxs-lookup"><span data-stu-id="c5222-153">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="c5222-154">Lo schema completo per il file *template.json* è disponibile nell'[archivio degli schemi JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="c5222-154">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="c5222-155">Per altre informazioni sul file *template.json*, vedere il [wiki sulla creazione di modelli dotnet](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="c5222-155">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="c5222-156">Ora che è disponibile un file _.template.config/template.json_ valido, il modello è pronto per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="c5222-156">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="c5222-157">Prima di installare il modello, assicurarsi di eliminare eventuali file e cartelle aggiuntivi che non si vuole includere nel modello, ad esempio le cartelle _bin_ o _obj_.</span><span class="sxs-lookup"><span data-stu-id="c5222-157">Before you install the template, make sure that you delete any extra files folders and files you don't want included in your template, like the _bin_ or _obj_ folders.</span></span> <span data-ttu-id="c5222-158">Nel terminale passare alla cartella _consoleasync_ ed eseguire `dotnet new -i .\` per installare il modello che si trova nella cartella corrente.</span><span class="sxs-lookup"><span data-stu-id="c5222-158">In your terminal, navigate to the _consoleasync_ folder and run `dotnet new -i .\` to install the template located at the current folder.</span></span> <span data-ttu-id="c5222-159">Se si usa un sistema operativo Linux o macOS, usare una barra: `dotnet new -i ./`.</span><span class="sxs-lookup"><span data-stu-id="c5222-159">If you're using a Linux or macOS operating system, use a forward slash: `dotnet new -i ./`.</span></span>

<span data-ttu-id="c5222-160">Questo comando restituisce l'elenco dei modelli installati, che dovrebbe includere quello creato in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="c5222-160">This command outputs the list of templates installed, which should include yours.</span></span>

```dotnetcli
dotnet new -i .\
```

<span data-ttu-id="c5222-161">Si otterrà un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="c5222-161">You get output similar to the following.</span></span>

```console
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Console Application                               console               [C#], F#, VB      Common/Console
Example templates: async project                  consoleasync          [C#]              Common/Console/C#8
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

### <a name="test-the-project-template"></a><span data-ttu-id="c5222-162">Testare il modello di progetto</span><span class="sxs-lookup"><span data-stu-id="c5222-162">Test the project template</span></span>

<span data-ttu-id="c5222-163">Ora che è stato installato un modello di elemento, è opportuno testarlo.</span><span class="sxs-lookup"><span data-stu-id="c5222-163">Now that you have an item template installed, test it.</span></span>

1. <span data-ttu-id="c5222-164">Passare alla cartella _test_</span><span class="sxs-lookup"><span data-stu-id="c5222-164">Navigate to the _test_ folder</span></span>

1. <span data-ttu-id="c5222-165">Creare una nuova applicazione console con il comando seguente che genera un progetto funzionante che è possibile testare facilmente con il comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="c5222-165">Create a new console application with the following command which generates a working project you can easily test with the `dotnet run` command.</span></span>

    ```dotnetcli
    dotnet new consoleasync
    ```

    <span data-ttu-id="c5222-166">Si ottiene l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="c5222-166">You get the following output.</span></span>

    ```console
    The template "Example templates: async project" was created successfully.
    ```

1. <span data-ttu-id="c5222-167">Eseguire il progetto usando il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="c5222-167">Run the project using the following command.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="c5222-168">Si ottiene l'output seguente.</span><span class="sxs-lookup"><span data-stu-id="c5222-168">You get the following output.</span></span>

    ```console
    Hello World with C# 8.0!
    ```

<span data-ttu-id="c5222-169">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="c5222-169">Congratulations!</span></span> <span data-ttu-id="c5222-170">È stato creato e distribuito un modello di progetto con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c5222-170">You created and deployed a project template with .NET Core.</span></span> <span data-ttu-id="c5222-171">Per prepararsi per la parte successiva di questa serie di esercitazioni, è necessario disinstallare il modello creato.</span><span class="sxs-lookup"><span data-stu-id="c5222-171">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="c5222-172">Assicurarsi di eliminare anche tutti i file dalla cartella _test_.</span><span class="sxs-lookup"><span data-stu-id="c5222-172">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="c5222-173">Verrà ripristinato uno stato pulito, pronto per la prossima sezione principale di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="c5222-173">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

### <a name="uninstall-the-template"></a><span data-ttu-id="c5222-174">Disinstallare il modello</span><span class="sxs-lookup"><span data-stu-id="c5222-174">Uninstall the template</span></span>

<span data-ttu-id="c5222-175">Poiché il modello è stato installato usando un percorso di file, è necessario disinstallarlo con il percorso di file **assoluto**.</span><span class="sxs-lookup"><span data-stu-id="c5222-175">Because you installed the template by using a file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="c5222-176">È possibile visualizzare un elenco dei modelli installati eseguendo il comando `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="c5222-176">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="c5222-177">Il modello creato in questo articolo dovrebbe essere l'ultimo dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c5222-177">Your template should be listed last.</span></span> <span data-ttu-id="c5222-178">Usare il percorso indicato per disinstallare il modello con il comando `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>`.</span><span class="sxs-lookup"><span data-stu-id="c5222-178">Use the path listed to uninstall your template with the `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` command.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="c5222-179">Si otterrà un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="c5222-179">You get output similar to the following.</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  C:\working\templates\consoleasync
    Templates:
      Example templates: async project (consoleasync) C#
```

<span data-ttu-id="c5222-180">Per disinstallare un modello, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="c5222-180">To uninstall a template, run the following command.</span></span>

```dotnetcli
dotnet new -u C:\working\templates\consoleasync
```

## <a name="next-steps"></a><span data-ttu-id="c5222-181">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="c5222-181">Next steps</span></span>

<span data-ttu-id="c5222-182">In questa esercitazione è stato creato un modello di progetto.</span><span class="sxs-lookup"><span data-stu-id="c5222-182">In this tutorial, you created a project template.</span></span> <span data-ttu-id="c5222-183">Per informazioni su come creare un pacchetto dei modelli di elementi e di progetto in un file di facile utilizzo, continuare con questa serie di esercitazioni.</span><span class="sxs-lookup"><span data-stu-id="c5222-183">To learn how to package both the item and project templates into an easy-to-use file, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c5222-184">Creare un pacchetto di modelli</span><span class="sxs-lookup"><span data-stu-id="c5222-184">Create a template pack</span></span>](cli-templates-create-template-pack.md)
