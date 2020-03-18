---
title: Creare un modello di elemento per dotnet new - Interfaccia della riga di comando di .NET Core
description: Informazioni su come creare un modello di elemento per il comando dotnet new. I modelli di elemento possono contenere un numero qualsiasi di file.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 5f4038e863d9bb59df470d3516c08fd2ad29c078
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503552"
---
# <a name="tutorial-create-an-item-template"></a><span data-ttu-id="a4345-104">Esercitazione: Creare un modello di elementoTutorial: Create an item template</span><span class="sxs-lookup"><span data-stu-id="a4345-104">Tutorial: Create an item template</span></span>

<span data-ttu-id="a4345-105">Con .NET Core è possibile creare e distribuire modelli per generare progetti, file e persino risorse.</span><span class="sxs-lookup"><span data-stu-id="a4345-105">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="a4345-106">Questa esercitazione è la prima parte di una serie che illustra come creare, installare e disinstallare i modelli da usare con il comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="a4345-106">This tutorial is part one of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="a4345-107">In questa parte della serie si apprenderà come:</span><span class="sxs-lookup"><span data-stu-id="a4345-107">In this part of the series, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="a4345-108">Creare una classe per un modello di elemento</span><span class="sxs-lookup"><span data-stu-id="a4345-108">Create a class for an item template</span></span>
> * <span data-ttu-id="a4345-109">Creare la cartella e il file di configurazione del modello</span><span class="sxs-lookup"><span data-stu-id="a4345-109">Create the template config folder and file</span></span>
> * <span data-ttu-id="a4345-110">Installare un modello da un percorso di file</span><span class="sxs-lookup"><span data-stu-id="a4345-110">Install a template from a file path</span></span>
> * <span data-ttu-id="a4345-111">Testare un modello di elemento</span><span class="sxs-lookup"><span data-stu-id="a4345-111">Test an item template</span></span>
> * <span data-ttu-id="a4345-112">Disinstallare un modello di elemento</span><span class="sxs-lookup"><span data-stu-id="a4345-112">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a4345-113">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="a4345-113">Prerequisites</span></span>

* <span data-ttu-id="a4345-114">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="a4345-114">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
* <span data-ttu-id="a4345-115">Leggere l'articolo di riferimento [Modelli personalizzati per dotnet new](../tools/custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="a4345-115">Read the reference article [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

  <span data-ttu-id="a4345-116">L'articolo di riferimento presenta i concetti di base sui modelli e il modo in cui vengono creati.</span><span class="sxs-lookup"><span data-stu-id="a4345-116">The reference article explains the basics about templates and how they're put together.</span></span> <span data-ttu-id="a4345-117">Alcune di queste informazioni verranno ripetute qui.</span><span class="sxs-lookup"><span data-stu-id="a4345-117">Some of this information will be reiterated here.</span></span>

* <span data-ttu-id="a4345-118">Aprire un terminale e passare alla cartella _working\templates_.</span><span class="sxs-lookup"><span data-stu-id="a4345-118">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-the-required-folders"></a><span data-ttu-id="a4345-119">Creare le cartelle necessarie</span><span class="sxs-lookup"><span data-stu-id="a4345-119">Create the required folders</span></span>

<span data-ttu-id="a4345-120">Questa serie usa una "cartella di lavoro" in cui è contenuta l'origine del modello e una "cartella di test" usata per testare i modelli.</span><span class="sxs-lookup"><span data-stu-id="a4345-120">This series uses a "working folder" where your template source is contained and a "testing folder" used to test your templates.</span></span> <span data-ttu-id="a4345-121">La cartella di lavoro e la cartella di test devono trovarsi nella stessa cartella padre.</span><span class="sxs-lookup"><span data-stu-id="a4345-121">The working folder and testing folder should be under the same parent folder.</span></span>

<span data-ttu-id="a4345-122">Prima di tutto creare la cartella padre. Il nome non è rilevante.</span><span class="sxs-lookup"><span data-stu-id="a4345-122">First, create the parent folder, the name does not matter.</span></span> <span data-ttu-id="a4345-123">Creare quindi una sottocartella denominata _working_.</span><span class="sxs-lookup"><span data-stu-id="a4345-123">Then, create a subfolder named _working_.</span></span> <span data-ttu-id="a4345-124">All'interno della cartella _working_ creare una sottocartella denominata _templates_.</span><span class="sxs-lookup"><span data-stu-id="a4345-124">Inside of the _working_ folder, create a subfolder named _templates_.</span></span>

<span data-ttu-id="a4345-125">Creare poi una cartella nella cartella padre denominata _test_.</span><span class="sxs-lookup"><span data-stu-id="a4345-125">Next, create a folder under the parent folder named _test_.</span></span> <span data-ttu-id="a4345-126">La struttura delle cartelle dovrebbe essere simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="a4345-126">The folder structure should look like the following.</span></span>

```console
parent_folder
├───test
└───working
    └───templates
```

## <a name="create-an-item-template"></a><span data-ttu-id="a4345-127">Creare un modello di elemento</span><span class="sxs-lookup"><span data-stu-id="a4345-127">Create an item template</span></span>

<span data-ttu-id="a4345-128">Un modello di elemento è un tipo specifico di modello che contiene uno o più file.</span><span class="sxs-lookup"><span data-stu-id="a4345-128">An item template is a specific type of template that contains one or more files.</span></span> <span data-ttu-id="a4345-129">Questi tipi di modelli sono utili quando si vogliono generare elementi come un file di configurazione, di codice o di soluzione.</span><span class="sxs-lookup"><span data-stu-id="a4345-129">These types of templates are useful when you want to generate something like a config, code, or solution file.</span></span> <span data-ttu-id="a4345-130">In questo esempio verrà creata una classe che aggiunge un metodo di estensione al tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="a4345-130">In this example, you'll create a class that adds an extension method to the string type.</span></span>

<span data-ttu-id="a4345-131">Nel terminale passare alla cartella _working\templates_ e creare una nuova sottocartella denominata _extensions_.</span><span class="sxs-lookup"><span data-stu-id="a4345-131">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _extensions_.</span></span> <span data-ttu-id="a4345-132">Accedere alla cartella.</span><span class="sxs-lookup"><span data-stu-id="a4345-132">Enter the folder.</span></span>

```console
working
└───templates
    └───extensions
```

<span data-ttu-id="a4345-133">Creare un nuovo file denominato _CommonExtensions.cs_ e aprirlo con l'editor di testo preferito.</span><span class="sxs-lookup"><span data-stu-id="a4345-133">Create a new file named _CommonExtensions.cs_ and open it with your favorite text editor.</span></span> <span data-ttu-id="a4345-134">Questa classe fornirà un metodo di estensione denominato `Reverse` che inverte il contenuto di una stringa.</span><span class="sxs-lookup"><span data-stu-id="a4345-134">This class will provide an extension method named `Reverse` that reverses the contents of a string.</span></span> <span data-ttu-id="a4345-135">Incollare il codice seguente e salvare il file:</span><span class="sxs-lookup"><span data-stu-id="a4345-135">Paste in the following code and save the file:</span></span>

```csharp
using System;

namespace System
{
    public static class StringExtensions
    {
        public static string Reverse(this string value)
        {
            var tempArray = value.ToCharArray();
            Array.Reverse(tempArray);
            return new string(tempArray);
        }
    }
}
```

<span data-ttu-id="a4345-136">Ora che è stato creato il contenuto del modello, è necessario creare la configurazione del modello nella cartella radice del modello.</span><span class="sxs-lookup"><span data-stu-id="a4345-136">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="a4345-137">Crea la configurazione del modello</span><span class="sxs-lookup"><span data-stu-id="a4345-137">Create the template config</span></span>

<span data-ttu-id="a4345-138">I modelli sono riconosciuti in .NET Core grazie a una cartella e a un file di configurazione speciali disponibili nella radice del modello.</span><span class="sxs-lookup"><span data-stu-id="a4345-138">Templates are recognized in .NET Core by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="a4345-139">In questa esercitazione la cartella dei modelli si trova in _working\templates\extensions_.</span><span class="sxs-lookup"><span data-stu-id="a4345-139">In this tutorial, your template folder is located at _working\templates\extensions_.</span></span>

<span data-ttu-id="a4345-140">Quando si crea un modello, tutti i file e le cartelle nella cartella del modello vengono inclusi come parte del modello, ad eccezione della cartella di configurazione speciale.</span><span class="sxs-lookup"><span data-stu-id="a4345-140">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="a4345-141">Questa cartella di configurazione è denominata _.template.config_.</span><span class="sxs-lookup"><span data-stu-id="a4345-141">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="a4345-142">Per prima cosa, creare una nuova sottocartella denominata _.template.config_ e aprirla.</span><span class="sxs-lookup"><span data-stu-id="a4345-142">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="a4345-143">Creare quindi un nuovo file denominato _template.json_.</span><span class="sxs-lookup"><span data-stu-id="a4345-143">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="a4345-144">La struttura di cartelle dovrebbe essere simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="a4345-144">Your folder structure should look like this:</span></span>

```console
working
└───templates
    └───extensions
        └───.template.config
                template.json
```

<span data-ttu-id="a4345-145">Aprire il _file template.json_ con l'editor di testo preferito e incollare il codice JSON seguente e salvarlo.</span><span class="sxs-lookup"><span data-stu-id="a4345-145">Open the _template.json_ with your favorite text editor and paste in the following JSON code and save it.</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Code" ],
  "identity": "ExampleTemplate.StringExtensions",
  "name": "Example templates: string extensions",
  "shortName": "stringext",
  "tags": {
    "language": "C#",
    "type": "item"
  }
}
```

<span data-ttu-id="a4345-146">Questo file di configurazione contiene tutte le impostazioni per il modello.</span><span class="sxs-lookup"><span data-stu-id="a4345-146">This config file contains all the settings for your template.</span></span> <span data-ttu-id="a4345-147">È possibile visualizzare le impostazioni di base, ad esempio `name` e `shortName`, ma anche un valore `tags/type` impostato su `item`.</span><span class="sxs-lookup"><span data-stu-id="a4345-147">You can see the basic settings, such as `name` and `shortName`, but there's also a `tags/type` value that is set to `item`.</span></span> <span data-ttu-id="a4345-148">In questo modo il modello viene categorizzato come modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="a4345-148">This categorizes your template as an item template.</span></span> <span data-ttu-id="a4345-149">Non esiste alcuna restrizione per il tipo di modello che si può creare.</span><span class="sxs-lookup"><span data-stu-id="a4345-149">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="a4345-150">I valori `item` e `project` sono nomi comuni consigliati da .NET Core in modo che gli utenti possano filtrare facilmente il tipo di modello per eventuali ricerche.</span><span class="sxs-lookup"><span data-stu-id="a4345-150">The `item` and `project` values are common names that .NET Core recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="a4345-151">L'elemento `classifications` rappresenta la colonna **tags** visualizzata quando si esegue `dotnet new` e si ottiene un elenco di modelli.</span><span class="sxs-lookup"><span data-stu-id="a4345-151">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="a4345-152">Gli utenti possono anche eseguire ricerche in base ai tag di classificazione.</span><span class="sxs-lookup"><span data-stu-id="a4345-152">Users can also search based on classification tags.</span></span> <span data-ttu-id="a4345-153">Non confondere la proprietà `tags` nel file \*.json con l'elenco dei tag `classifications`.</span><span class="sxs-lookup"><span data-stu-id="a4345-153">Don't confuse the `tags` property in the \*.json file with the `classifications` tags list.</span></span> <span data-ttu-id="a4345-154">Si tratta di due cose diverse, sfortunatamente con nomi simili.</span><span class="sxs-lookup"><span data-stu-id="a4345-154">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="a4345-155">Lo schema completo per il file *template.json* è disponibile nell'[archivio degli schemi JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="a4345-155">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="a4345-156">Per altre informazioni sul file *template.json*, vedere il [wiki sulla creazione di modelli dotnet](https://github.com/dotnet/templating/wiki).</span><span class="sxs-lookup"><span data-stu-id="a4345-156">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="a4345-157">Ora che è disponibile un file _.template.config/template.json_ valido, il modello è pronto per l'installazione.</span><span class="sxs-lookup"><span data-stu-id="a4345-157">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="a4345-158">Nel terminale passare alla cartella _extensions_ ed eseguire il comando seguente per installare il modello che si trova nella cartella corrente:</span><span class="sxs-lookup"><span data-stu-id="a4345-158">In your terminal, navigate to the  _extensions_ folder and run the following command to install the template located at the current folder:</span></span>

* <span data-ttu-id="a4345-159">**Su Windows**:`dotnet new -i .\`</span><span class="sxs-lookup"><span data-stu-id="a4345-159">**On Windows**: `dotnet new -i .\`</span></span>
* <span data-ttu-id="a4345-160">**Su Linux o macOS**:`dotnet new -i ./`</span><span class="sxs-lookup"><span data-stu-id="a4345-160">**On Linux or macOS**: `dotnet new -i ./`</span></span>

<span data-ttu-id="a4345-161">Questo comando restituisce l'elenco dei modelli installati, che dovrebbe includere quello creato in questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="a4345-161">This command outputs the list of templates installed, which should include yours.</span></span>

```console
C:\working\templates\extensions> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

## <a name="test-the-item-template"></a><span data-ttu-id="a4345-162">Testare il modello di elemento</span><span class="sxs-lookup"><span data-stu-id="a4345-162">Test the item template</span></span>

<span data-ttu-id="a4345-163">Ora che è stato installato un modello di elemento, è opportuno testarlo.</span><span class="sxs-lookup"><span data-stu-id="a4345-163">Now that you have an item template installed, test it.</span></span> <span data-ttu-id="a4345-164">Passare alla cartella _test/_ e creare una nuova applicazione console con `dotnet new console`.</span><span class="sxs-lookup"><span data-stu-id="a4345-164">Navigate to the _test/_ folder and create a new console application with `dotnet new console`.</span></span> <span data-ttu-id="a4345-165">Viene generato un progetto funzionante che è possibile testare facilmente con il comando `dotnet run`.</span><span class="sxs-lookup"><span data-stu-id="a4345-165">This generates a working project you can easily test with the `dotnet run` command.</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="a4345-166">Si ottiene un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="a4345-166">You get output similar to the following.</span></span>

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\test\test.csproj...
  Restore completed in 54.82 ms for C:\test\test.csproj.

Restore succeeded.
```

<span data-ttu-id="a4345-167">Eseguire il progetto con.</span><span class="sxs-lookup"><span data-stu-id="a4345-167">Run the project with.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="a4345-168">Viene visualizzato il seguente output.</span><span class="sxs-lookup"><span data-stu-id="a4345-168">You get the following output.</span></span>

```console
Hello World!
```

<span data-ttu-id="a4345-169">Eseguire quindi `dotnet new stringext` per generare il file _CommonExtensions.cs_ dal modello.</span><span class="sxs-lookup"><span data-stu-id="a4345-169">Next, run `dotnet new stringext` to generate the _CommonExtensions.cs_ from the template.</span></span>

```dotnetcli
dotnet new stringext
```

<span data-ttu-id="a4345-170">Viene visualizzato il seguente output.</span><span class="sxs-lookup"><span data-stu-id="a4345-170">You get the following output.</span></span>

```console
The template "Example templates: string extensions" was created successfully.
```

<span data-ttu-id="a4345-171">Modificare il codice in _Program.cs_ per invertire la stringa `"Hello World"` con il metodo di estensione fornito dal modello.</span><span class="sxs-lookup"><span data-stu-id="a4345-171">Change the code in _Program.cs_ to reverse the `"Hello World"` string with the extension method provided by the template.</span></span>

```csharp
Console.WriteLine("Hello World!".Reverse());
```

<span data-ttu-id="a4345-172">Eseguire di nuovo il programma per verificare che il risultato sia invertito.</span><span class="sxs-lookup"><span data-stu-id="a4345-172">Run the program again and you'll see that the result is reversed.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="a4345-173">Viene visualizzato il seguente output.</span><span class="sxs-lookup"><span data-stu-id="a4345-173">You get the following output.</span></span>

```console
!dlroW olleH
```

<span data-ttu-id="a4345-174">Congratulazioni!</span><span class="sxs-lookup"><span data-stu-id="a4345-174">Congratulations!</span></span> <span data-ttu-id="a4345-175">È stato creato e distribuito un modello di elemento con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a4345-175">You created and deployed an item template with .NET Core.</span></span> <span data-ttu-id="a4345-176">Per prepararsi per la parte successiva di questa serie di esercitazioni, è necessario disinstallare il modello creato.</span><span class="sxs-lookup"><span data-stu-id="a4345-176">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="a4345-177">Assicurarsi di eliminare anche tutti i file dalla cartella _test_.</span><span class="sxs-lookup"><span data-stu-id="a4345-177">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="a4345-178">Verrà ripristinato uno stato pulito, pronto per la prossima sezione principale di questa esercitazione.</span><span class="sxs-lookup"><span data-stu-id="a4345-178">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

## <a name="uninstall-the-template"></a><span data-ttu-id="a4345-179">Disinstallare il modello</span><span class="sxs-lookup"><span data-stu-id="a4345-179">Uninstall the template</span></span>

<span data-ttu-id="a4345-180">Poiché il modello è stato installato usando un percorso di file, è necessario disinstallarlo con il percorso di file **assoluto**.</span><span class="sxs-lookup"><span data-stu-id="a4345-180">Because you installed the template by file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="a4345-181">È possibile visualizzare un elenco dei modelli installati eseguendo il comando `dotnet new -u`.</span><span class="sxs-lookup"><span data-stu-id="a4345-181">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="a4345-182">Il modello creato in questo articolo dovrebbe essere l'ultimo dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="a4345-182">Your template should be listed last.</span></span> <span data-ttu-id="a4345-183">Usare il percorso indicato per disinstallare il modello con il comando `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>`.</span><span class="sxs-lookup"><span data-stu-id="a4345-183">Use the path listed to uninstall your template with the `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` command.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="a4345-184">Si ottiene un output simile al seguente.</span><span class="sxs-lookup"><span data-stu-id="a4345-184">You get output similar to the following.</span></span>

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
  C:\working\templates\extensions
    Templates:
      Example templates: string extensions (stringext) C#
```

<span data-ttu-id="a4345-185">Per disinstallare un modello, eseguire il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="a4345-185">To uninstall a template, run the following command.</span></span>

```dotnetcli
dotnet new -u C:\working\templates\extensions
```

## <a name="next-steps"></a><span data-ttu-id="a4345-186">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a4345-186">Next steps</span></span>

<span data-ttu-id="a4345-187">In questa esercitazione è stato creato un modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="a4345-187">In this tutorial, you created an item template.</span></span> <span data-ttu-id="a4345-188">Per scoprire come creare un modello di progetto, continuare con questa serie di esercitazioni.</span><span class="sxs-lookup"><span data-stu-id="a4345-188">To learn how to create a project template, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="a4345-189">Creare un modello di progetto</span><span class="sxs-lookup"><span data-stu-id="a4345-189">Create a project template</span></span>](cli-templates-create-project-template.md)
