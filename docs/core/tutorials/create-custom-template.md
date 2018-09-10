---
title: Creare un modello personalizzato per dotnet new
description: Informazioni su come creare un modello personalizzato per il comando dotnet new in questa gradevole esercitazione.
author: guardrex
ms.author: mairaw
ms.date: 08/12/2017
ms.openlocfilehash: 2377d894bcbf54a9c96eae1093d891080e6d11c5
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43516653"
---
# <a name="create-a-custom-template-for-dotnet-new"></a><span data-ttu-id="e6c9d-103">Creare un modello personalizzato per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e6c9d-103">Create a custom template for dotnet new</span></span>

<span data-ttu-id="e6c9d-104">In questa esercitazione verrà illustrato come:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-104">This tutorial shows you how to:</span></span>

- <span data-ttu-id="e6c9d-105">Creare un modello di base da un progetto esistente o un nuovo progetto app console.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-105">Create a basic template from an existing project or a new console app project.</span></span>
- <span data-ttu-id="e6c9d-106">Comprimere il modello per la distribuzione su nuget.org o da l file di una variabile locale *nupkg*.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-106">Pack the template for distribution at nuget.org or from a local *nupkg* file.</span></span>
- <span data-ttu-id="e6c9d-107">Installare il modello da nuget.org, un file locale *nupkg* o nel file system locale.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-107">Install the template from nuget.org, a local *nupkg* file, or the local file system.</span></span>
- <span data-ttu-id="e6c9d-108">Disinstallare il modello.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-108">Uninstall the template.</span></span>

<span data-ttu-id="e6c9d-109">Se si preferisce continuare l'esercitazione con un esempio completo, scaricare la [il modello del progetto di esempio](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-109">If you prefer to proceed through the tutorial with a complete sample, download the [sample project template](https://github.com/dotnet/dotnet-template-samples/tree/master/16-nuget-package).</span></span> <span data-ttu-id="e6c9d-110">Il modello di esempio è configurato per la distribuzione di NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-110">The sample template is configured for NuGet distribution.</span></span>

<span data-ttu-id="e6c9d-111">Se si desidera utilizzare l'esempio scaricato con la distribuzione di file system, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-111">If you wish to use the downloaded sample with file system distribution, do the following:</span></span>

- <span data-ttu-id="e6c9d-112">Spostare il contenuto della cartella *content* dell'esempio di un livello verso l’alto nella cartella *GarciaSoftware.ConsoleTemplate.CSharp*.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-112">Move the contents of the *content* folder of the sample up one level into the *GarciaSoftware.ConsoleTemplate.CSharp* folder.</span></span>
- <span data-ttu-id="e6c9d-113">Eliminare la cartella *content* vuota.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-113">Delete the empty *content* folder.</span></span>
- <span data-ttu-id="e6c9d-114">Eliminare il file *.nuspec*.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-114">Delete the *nuspec* file.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6c9d-115">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="e6c9d-115">Prerequisites</span></span>

- <span data-ttu-id="e6c9d-116">Installare [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-116">Install the [.NET Core 2.0 SDK](https://www.microsoft.com/net/core) or later versions.</span></span>
- <span data-ttu-id="e6c9d-117">Leggere l’argomento di riferimento [Modelli personalizzati per dotnet new](../tools/custom-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-117">Read the reference topic [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

## <a name="create-a-template-from-a-project"></a><span data-ttu-id="e6c9d-118">Creare un modello da un progetto</span><span class="sxs-lookup"><span data-stu-id="e6c9d-118">Create a template from a project</span></span>

<span data-ttu-id="e6c9d-119">Usare un progetto esistente di cui è stata verificata la corretta compilazione ed esecuzione oppure creare un nuovo progetto di app console in una cartella nel disco rigido.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-119">Use an existing project that you've confirmed compiles and runs, or create a new console app project in a folder on your hard drive.</span></span> <span data-ttu-id="e6c9d-120">In questa esercitazione si presuppone che il nome della cartella del progetto sia *GarciaSoftware.ConsoleTemplate.CSharp*, in *Documents/Templates* nel profilo utente.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-120">This tutorial assumes that the name of the project folder is *GarciaSoftware.ConsoleTemplate.CSharp* stored at *Documents\Templates* in the user's profile.</span></span> <span data-ttu-id="e6c9d-121">Il nome del modello di progetto dell'esercitazione è nel formato  *\<nome società>.\< Tipo di modello>. \<Linguaggio di programmazione>*, tuttavia è possibile attribuire al progetto e al modello il nome desiderato.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-121">The tutorial project template name is in the format *\<Company Name>.\<Template Type>.\<Programming Language>*, but you're free to name your project and template anything you wish.</span></span>

1. <span data-ttu-id="e6c9d-122">Aggiungere una cartella radice del progetto denominato *.template.config*.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-122">Add a folder to the root of the project named *.template.config*.</span></span>
1. <span data-ttu-id="e6c9d-123">All'interno della cartella *.template.config*, creare un file di configurazione del modello *template.json*.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-123">Inside the *.template.config* folder, create a *template.json* file to configure your template.</span></span> <span data-ttu-id="e6c9d-124">Per altre informazioni e la definizione del membro per il file *template.json*, vedere l’argomento [Modelli personalizzati per dotnet new](../tools/custom-templates.md#templatejson) e lo schema [ *template.json* nell'archivio di Schema JSON](http://json.schemastore.org/template).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-124">For more information and member definitions for the *template.json* file, see the [Custom templates for dotnet new](../tools/custom-templates.md#templatejson) topic and the [*template.json* schema at the JSON Schema Store](http://json.schemastore.org/template).</span></span>

```json
{
    "$schema": "http://json.schemastore.org/template",
    "author": "Catalina Garcia",
    "classifications": [ "Common", "Console" ],
    "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
    "name": "Garcia Software Console Application",
    "shortName": "garciaconsole"
}
```

<span data-ttu-id="e6c9d-125">Il modello è finito.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-125">The template is finished.</span></span> <span data-ttu-id="e6c9d-126">A questo punto, sono disponibili due opzioni per la distribuzione del modello.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-126">At this point, you have two options for template distribution.</span></span> <span data-ttu-id="e6c9d-127">Per continuare questa esercitazione, scegliere uno dei due percorsi:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-127">To continue this tutorial, choose one path or the other:</span></span>

1. <span data-ttu-id="e6c9d-128">[Distribuzione NuGet](#use-nuget-distribution): installare il modello da NuGet o dal file locale *nupkg* utilizzare il modello installato.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-128">[NuGet distribution](#use-nuget-distribution): install the template from NuGet or from the local *nupkg* file, and use the installed template.</span></span>
2. <span data-ttu-id="e6c9d-129">[Distribuzione file system](#use-file-system-distribution).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-129">[File system distribution](#use-file-system-distribution).</span></span>

## <a name="use-nuget-distribution"></a><span data-ttu-id="e6c9d-130">Utilizzare distribuuzione NuGet</span><span class="sxs-lookup"><span data-stu-id="e6c9d-130">Use NuGet Distribution</span></span>

### <a name="pack-the-template-into-a-nuget-package"></a><span data-ttu-id="e6c9d-131">Comprimere il modello in un pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="e6c9d-131">Pack the template into a NuGet package</span></span>

1. <span data-ttu-id="e6c9d-132">Creare una cartella per il pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-132">Create a folder for the NuGet package.</span></span> <span data-ttu-id="e6c9d-133">Per l'esercitazione, il nome usato per la cartella è *GarciaSoftware.ConsoleTemplate.CSharp* e la cartella viene creata all'interno della cartella *Documents\NuGetTemplates* nel profilo utente.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-133">For the tutorial, the folder name *GarciaSoftware.ConsoleTemplate.CSharp* is used, and the folder is created inside a *Documents\NuGetTemplates* folder in the user's profile.</span></span> <span data-ttu-id="e6c9d-134">Creare una cartella denominata *content* all'interno della cartella del nuovo modello per contenere i file di progetto.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-134">Create a folder named *content* inside of the new template folder to hold the project files.</span></span>
1. <span data-ttu-id="e6c9d-135">Copiare il contenuto della cartella del progetto, insieme al relativo file *.template.config/template.json*nella cartella *content* creata.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-135">Copy the contents of your project folder, together with its *.template.config/template.json* file, into the *content* folder you created.</span></span>
1. <span data-ttu-id="e6c9d-136">Accanto alla cartella *content*, aggiungere un file [*nuspec*](/nuget/create-packages/creating-a-package).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-136">Next to the *content* folder, add a [*nuspec* file](/nuget/create-packages/creating-a-package).</span></span> <span data-ttu-id="e6c9d-137">Il file nuspec un file manifesto XML che descrive il contenuto di un pacchetto e guida il processo di creazione del pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-137">The nuspec file is an XML manifest file that describes a package's contents and drives the process of creating the NuGet package.</span></span>

   ![Struttura della directory contenente il layout del pacchetto NuGet](./media/create-custom-template/nugetdirectorylayout.png)

1. <span data-ttu-id="e6c9d-139">All'interno di un elemento  **\<packageTypes>** nel file *nuspec*, includere un elemento  **\<packageType>** con un valore dell'attributo `name` di `Template`.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-139">Inside of a **\<packageTypes>** element in the *nuspec* file, include a **\<packageType>** element with a `name` attribute value of `Template`.</span></span> <span data-ttu-id="e6c9d-140">La cartella *content* e il file *nuspec* devono trovarsi nella stessa directory.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-140">Both the *content* folder and the *nuspec* file should reside in the same directory.</span></span> <span data-ttu-id="e6c9d-141">La tabella mostra gli elementi del file *nuspec* minimi necessari per produrre un modello come pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-141">The table shows the minimum *nuspec* file elements required to produce a template as a NuGet package.</span></span>

   | <span data-ttu-id="e6c9d-142">Elemento</span><span class="sxs-lookup"><span data-stu-id="e6c9d-142">Element</span></span>            | <span data-ttu-id="e6c9d-143">Tipo</span><span class="sxs-lookup"><span data-stu-id="e6c9d-143">Type</span></span>   | <span data-ttu-id="e6c9d-144">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e6c9d-144">Description</span></span> |
   | ------------------ | ------ | ----------- |
   | <span data-ttu-id="e6c9d-145">**\<authors>**</span><span class="sxs-lookup"><span data-stu-id="e6c9d-145">**\<authors>**</span></span>     | <span data-ttu-id="e6c9d-146">stringa</span><span class="sxs-lookup"><span data-stu-id="e6c9d-146">string</span></span> | <span data-ttu-id="e6c9d-147">Elenco con valori delimitati da virgola di autori di pacchetti, corrispondenti ai nomi di profili in nuget.org. Gli autori, visualizzati nella raccolta NuGet in nuget.org, vengono usati per creare riferimenti incrociati ai pacchetti dello stesso autore.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-147">A comma-separated list of packages authors, matching the profile names on nuget.org. Authors are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span> |
   | <span data-ttu-id="e6c9d-148">**\<description>**</span><span class="sxs-lookup"><span data-stu-id="e6c9d-148">**\<description>**</span></span> | <span data-ttu-id="e6c9d-149">stringa</span><span class="sxs-lookup"><span data-stu-id="e6c9d-149">string</span></span> | <span data-ttu-id="e6c9d-150">Descrizione lunga del pacchetto per la visualizzazione dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-150">A long description of the package for UI display.</span></span> |
   | <span data-ttu-id="e6c9d-151">**\<id>**</span><span class="sxs-lookup"><span data-stu-id="e6c9d-151">**\<id>**</span></span>          | <span data-ttu-id="e6c9d-152">stringa</span><span class="sxs-lookup"><span data-stu-id="e6c9d-152">string</span></span> | <span data-ttu-id="e6c9d-153">L'identificatore del pacchetto senza distinzione tra maiuscole e minuscole che deve essere univoco in nuget.org o qualsiasi raccolta in cui risiederà il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-153">The case-insensitive package identifier, which must be unique across nuget.org or whatever gallery the package will reside in.</span></span> <span data-ttu-id="e6c9d-154">L'ID non può contenere spazi o caratteri non validi per un URL e in genere segue le regole dello spazio dei nomi .NET.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-154">IDs may not contain spaces or characters that are not valid for a URL and generally follow .NET namespace rules.</span></span> <span data-ttu-id="e6c9d-155">Vedere [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) (Scelta di un identificatore univoco del pacchetto e impostazione del numero di versione) per il materiale sussidiario.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-155">See [Choosing a unique package identifier and setting the version number](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number) for guidance.</span></span> |
   | <span data-ttu-id="e6c9d-156">**\<packageType>**</span><span class="sxs-lookup"><span data-stu-id="e6c9d-156">**\<packageType>**</span></span> | <span data-ttu-id="e6c9d-157">stringa</span><span class="sxs-lookup"><span data-stu-id="e6c9d-157">string</span></span> | <span data-ttu-id="e6c9d-158">Inserire l'elemento all'interno di un elemento  **\<packageTypes >** tra elementi  **\<metadata >**.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-158">Place this element inside a **\<packageTypes>** element among the **\<metadata>** elements.</span></span> <span data-ttu-id="e6c9d-159">Impostare l'attributo `name` dell'elemento **\<packageType>** su `Template`.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-159">Set the `name` attribute of the **\<packageType>** element to `Template`.</span></span> |
   | <span data-ttu-id="e6c9d-160">**\<version>**</span><span class="sxs-lookup"><span data-stu-id="e6c9d-160">**\<version>**</span></span>     | <span data-ttu-id="e6c9d-161">stringa</span><span class="sxs-lookup"><span data-stu-id="e6c9d-161">string</span></span> | <span data-ttu-id="e6c9d-162">La versione del pacchetto secondo il criterio major.minor.patch.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-162">The version of the package, following the major.minor.patch pattern.</span></span> <span data-ttu-id="e6c9d-163">I numeri di versione possono includere un suffisso di versione non definitiva, come descritto in [Versioni non definitive](/nuget/create-packages/prerelease-packages#semantic-versioning).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-163">Version numbers may include a pre-release suffix as described in [Pre-release versions](/nuget/create-packages/prerelease-packages#semantic-versioning).</span></span> |

   <span data-ttu-id="e6c9d-164">Vedere il [riferimento a .nuspec](/nuget/schema/nuspec) per lo schema completo del file *nuspec*.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-164">See the [.nuspec reference](/nuget/schema/nuspec) for the complete *nuspec* file schema.</span></span>

   <span data-ttu-id="e6c9d-165">Il *nuspec* file per l'esercitazione è denominata *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* e contiene il contenuto seguente:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-165">The *nuspec* file for the tutorial is named *GarciaSoftware.ConsoleTemplate.CSharp.nuspec* and contains the following content:</span></span>

   ```xml
   <?xml version="1.0" encoding="utf-8"?>
   <package xmlns="http://schemas.microsoft.com/packaging/2012/06/nuspec.xsd">
     <metadata>
       <id>GarciaSoftware.ConsoleTemplate.CSharp</id>
       <version>1.0.0</version>
       <description>
         Creates the Garcia Software console app.
       </description>
       <authors>Catalina Garcia</authors>
       <packageTypes>
         <packageType name="Template" />
       </packageTypes>
     </metadata>
   </package>
   ```

1. <span data-ttu-id="e6c9d-166">[Creare il pacchetto](/nuget/create-packages/creating-a-package#creating-the-package) usando il comando `nuget pack <PATH_TO_NUSPEC_FILE>`.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-166">[Create the package](/nuget/create-packages/creating-a-package#creating-the-package) using the `nuget pack <PATH_TO_NUSPEC_FILE>` command.</span></span> <span data-ttu-id="e6c9d-167">Il comando seguente presuppone che la cartella che contiene gli asset di NuGet si trovi nel percorso *C:\Users\\\<UTENTE>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-167">The following command assumes that the folder that holds the NuGet assets is at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*.</span></span> <span data-ttu-id="e6c9d-168">Tuttavia quando la cartella è collocata nel sistema, il comando `nuget pack` accetta il percorso del file *nuspec*:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-168">But wherever you place the folder on your system, the `nuget pack` command accepts the path to the *nuspec* file:</span></span>

   ```console
   nuget pack C:\Users\<USER>\Documents\NuGetTemplates\GarciaSoftware.ConsoleTemplate.CSharp\GarciaSoftware.ConsoleTemplate.CSharp.nuspec
   ```

### <a name="publishing-the-package-to-nugetorg"></a><span data-ttu-id="e6c9d-169">Pubblicazione del pacchetto su nuget.org</span><span class="sxs-lookup"><span data-stu-id="e6c9d-169">Publishing the package to nuget.org</span></span>

<span data-ttu-id="e6c9d-170">Per pubblicare un pacchetto NuGet, seguire le istruzioni dell’argomento [Creazione e pubblicazione di un pacchetto](/nuget/quickstart/create-and-publish-a-package#publish-the-package).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-170">To publish a NuGet package, follow the instructions in the [Create and publish a package](/nuget/quickstart/create-and-publish-a-package#publish-the-package) topic.</span></span> <span data-ttu-id="e6c9d-171">Tuttavia, si consiglia di non pubblicare il modello dell'esercitazione su NuGet poiché non è mai possibile eliminarlo una volta pubblicato, ma solo rimuoverlo dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-171">However, we recommend that you don't publish the tutorial template to NuGet as it can never be deleted once published, only delisted.</span></span> <span data-ttu-id="e6c9d-172">Dopo aver creato il pacchetto NuGet sotto forma di file *nupkg*, è consigliabile seguire le istruzioni seguenti per installare il modello direttamente dal file locale *nupkg*.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-172">Now that you have the NuGet package in the form of a *nupkg* file, we suggest that you follow the instructions below to install the template directly from the local *nupkg* file.</span></span>

### <a name="install-the-template-from-a-nuget-package"></a><span data-ttu-id="e6c9d-173">Installare il modello da un pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="e6c9d-173">Install the template from a NuGet package</span></span>

#### <a name="install-the-template-from-the-local-nupkg-file"></a><span data-ttu-id="e6c9d-174">Installare il modello da un file locale *nupkg*</span><span class="sxs-lookup"><span data-stu-id="e6c9d-174">Install the template from the local *nupkg* file</span></span>

<span data-ttu-id="e6c9d-175">Per installare il modello dal file *nupkg* che è stato creato, utilizzare il comando `dotnet new` con l’opzione `-i|--install` e specificare il percorso del file *nupkg*:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-175">To install the template from the *nupkg* file that you produced, use the `dotnet new` command with the `-i|--install` option and provide the path to the *nupkg* file:</span></span>

```console
dotnet new -i C:\Users\<USER>\GarciaSoftware.ConsoleTemplate.CSharp.1.0.0.nupkg
```

#### <a name="install-the-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="e6c9d-176">Installare il modello da un pacchetto NuGet archiviato in nuget.org</span><span class="sxs-lookup"><span data-stu-id="e6c9d-176">Install the template from a NuGet package stored at nuget.org</span></span>

<span data-ttu-id="e6c9d-177">Se si desidera installare un modello da un pacchetto NuGet archiviato su nuget.org, utilizzare il comando `dotnet new` con l’opzione `-i|--install` e specificare il nome del pacchetto NuGet:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-177">If you wish to install a template from a NuGet package stored at nuget.org, use the `dotnet new` command with the `-i|--install` option and supply the name of the NuGet package:</span></span>

```console
dotnet new -i GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="e6c9d-178">L'esempio ha solo scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-178">The example is for demonstration purposes only.</span></span> <span data-ttu-id="e6c9d-179">Non è presente un `GarciaSoftware.ConsoleTemplate.CSharp` pacchetto NuGet su nuget.org, e non è consigliabile di pubblicare e utilizzare modelli di test da NuGet.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-179">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org, and we don't recommend that you publish and consume test templates from NuGet.</span></span> <span data-ttu-id="e6c9d-180">Se si esegue il comando, non viene installato alcun modello.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-180">If you run the command, no template is installed.</span></span> <span data-ttu-id="e6c9d-181">Tuttavia, è possibile installare un modello che non è stato pubblicato su nuget.org facendo riferimento al file *nupkg* direttamente nel file system locale, come illustrato nella sezione precedente [Installare il modello dal file nupkg locale](#install-the-template-from-the-local-nupkg-file).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-181">However, you can install a template that hasn't been published to nuget.org by referencing the *nupkg* file directly on your local file system as shown in the previous section [Install the template from the local nupkg file](#install-the-template-from-the-local-nupkg-file).</span></span>

<span data-ttu-id="e6c9d-182">Se si desidera un esempio della procedura di installazione di un modello da un pacchetto in nuget.org in tempo reale, è possibile utilizzare il [modello NUnit 3 per dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-182">If you'd like a live example of how to install a template from a package at nuget.org, you can use the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/).</span></span> <span data-ttu-id="e6c9d-183">Questo modello configura un progetto per utilizzare il testing unità NUnit.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-183">This template sets up a project to use NUnit unit testing.</span></span> <span data-ttu-id="e6c9d-184">Usare il comando seguente per installarlo:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-184">Use the following command to install it:</span></span>

```console
dotnet new -i NUnit3.DotNetNew.Template
```

<span data-ttu-id="e6c9d-185">Quando si elencano i modelli con `dotnet new -l`, viene visualizzato il *progetto di test NUnit 3* con un nome breve di *nunit* nell'elenco dei modelli.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-185">When you list the templates with `dotnet new -l`, you see the *NUnit 3 Test Project* with a short name of *nunit* in the template list.</span></span> <span data-ttu-id="e6c9d-186">Si è pronti a utilizzare il modello nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-186">You're ready to use the template in the next section.</span></span>

![Finestra della console che mostra il modello NUnit elencato con altri modelli installati](./media/create-custom-template/nunit1.png)

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="e6c9d-188">Creare un progetto da un modello</span><span class="sxs-lookup"><span data-stu-id="e6c9d-188">Create a project from the template</span></span>

<span data-ttu-id="e6c9d-189">Dopo aver installato il modello da NuGet, utilizzare il modello eseguendo il comando `dotnet new <TEMPLATE>` dalla directory in cui si desidera collocare il motore del modello di output (a meno che non si utilizzi l’opzione `-o|--output` per specificare una directory specifica).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-189">After the template is installed from NuGet, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="e6c9d-190">Per altre informazioni, vedere [`dotnet new` Opzioni](~/docs/core/tools/dotnet-new.md#options).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-190">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="e6c9d-191">Specificare il nome breve del modello direttamente nel comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-191">Supply the template's short name directly to the `dotnet new` command.</span></span> <span data-ttu-id="e6c9d-192">Per creare un progetto dal modello NUnit, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-192">To create a project from the NUnit template, run the following command:</span></span>

```console
dotnet new nunit
```

<span data-ttu-id="e6c9d-193">La console mostra che il progetto viene creato e che vengono ripristinati i pacchetti del progetto.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-193">The console shows that the project is created and that the project's packages are restored.</span></span> <span data-ttu-id="e6c9d-194">Dopo l’esecuzione del comando, il progetto è pronto per l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-194">After the command is run, the project is ready for use.</span></span>

![Finestra della console che mostra l'output del comando dotnet new mentre crea il progetto NUnit e ripristina le dipendenze di progetto](./media/create-custom-template/nunit2.png)

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a><span data-ttu-id="e6c9d-196">Per disinstallare un modello da un pacchetto NuGet archiviato in nuget.org</span><span class="sxs-lookup"><span data-stu-id="e6c9d-196">To uninstall a template from a NuGet package stored at nuget.org</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="e6c9d-197">L'esempio ha solo scopo dimostrativo.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-197">The example is for demonstration purposes only.</span></span> <span data-ttu-id="e6c9d-198">Non è presente un `GarciaSoftware.ConsoleTemplate.CSharp` pacchetto NuGet in nuget.org o installato con .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-198">There isn't a `GarciaSoftware.ConsoleTemplate.CSharp` NuGet package at nuget.org or installed with the .NET Core SDK.</span></span> <span data-ttu-id="e6c9d-199">Se si esegue il comando, nessun pacchetto o modello viene disinstallato e si riceve l'eccezione seguente:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-199">If you run the command, no package/template is uninstalled and you receive the following exception:</span></span>
>
> > <span data-ttu-id="e6c9d-200">Impossibile trovare un elemento da disinstallare denominato 'GarciaSoftware.ConsoleTemplate.CSharp'.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-200">Could not find something to uninstall called 'GarciaSoftware.ConsoleTemplate.CSharp'.</span></span>

<span data-ttu-id="e6c9d-201">Se è stato installato il modello [NUnit 3 per dotnet new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) e si desidera disinstallare l'estensione, usare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-201">If you installed the [NUnit 3 template for dotnet-new](https://www.nuget.org/packages/NUnit3.DotNetNew.Template/) and wish to uninstall it, use the following command:</span></span>

```console
dotnet new -u NUnit3.DotNetNew.Template
```

### <a name="uninstall-the-template-from-a-local-nupkg-file"></a><span data-ttu-id="e6c9d-202">Disnstallare il modello dal file locale nupkg</span><span class="sxs-lookup"><span data-stu-id="e6c9d-202">Uninstall the template from a local nupkg file</span></span>

<span data-ttu-id="e6c9d-203">Quando si desidera disinstallare il modello, non tentare di usare il percorso al file *nupkg*.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-203">When you wish to uninstall the template, don't attempt to use the path to the *nupkg* file.</span></span> <span data-ttu-id="e6c9d-204">*Il tentativo di disinstallare un modello usando `dotnet new -u <PATH_TO_NUPKG_FILE>` ha esito negativo.*</span><span class="sxs-lookup"><span data-stu-id="e6c9d-204">*Attempting to uninstall a template using `dotnet new -u <PATH_TO_NUPKG_FILE>` fails.*</span></span> <span data-ttu-id="e6c9d-205">Fare riferimento al pacchetto in base al relativo `id`:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-205">Reference the package by its `id`:</span></span>

```console
dotnet new -u GarciaSoftware.ConsoleTemplate.CSharp.1.0.0
```

## <a name="use-file-system-distribution"></a><span data-ttu-id="e6c9d-206">Utilizzare la distribuzione file system</span><span class="sxs-lookup"><span data-stu-id="e6c9d-206">Use file system distribution</span></span>

<span data-ttu-id="e6c9d-207">Per distribuire il modello, collocare la cartella del modello di progetto in una posizione accessibile agli utenti della rete.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-207">To distribute the template, place the project template folder in a location accessible to users on your network.</span></span> <span data-ttu-id="e6c9d-208">Utilizzare il comando `dotnet new` con l’opzione `-i|--install` e specificare il percorso alla cartella del modello (la cartella di progetto contenente il progetto e la cartella *.template.config*).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-208">Use the `dotnet new` command with the `-i|--install` option and specify the path to the template folder (the project folder containing the project and the *.template.config* folder).</span></span>

<span data-ttu-id="e6c9d-209">L'esercitazione presuppone che il modello di progetto sia archiviato nella cartella *Documents/Templates* del profilo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-209">The tutorial assumes the project template is stored in the *Documents/Templates* folder of the user's profile.</span></span> <span data-ttu-id="e6c9d-210">Da quel percorso, è necessario installare il modello con il comando seguente sostituendo \<USER > con il nome del profilo dell'utente:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-210">From that location, install the template with the following command replacing \<USER> with the user's profile name:</span></span>

```console
dotnet new -i C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

### <a name="create-a-project-from-the-template"></a><span data-ttu-id="e6c9d-211">Creare un progetto da un modello</span><span class="sxs-lookup"><span data-stu-id="e6c9d-211">Create a project from the template</span></span>

<span data-ttu-id="e6c9d-212">Dopo aver installato il modello dal file system, utilizzare il modello eseguendo il comando `dotnet new <TEMPLATE>` dalla directory in cui si desidera collocare il motore del modello di output (a meno che non si utilizzi l’opzione `-o|--output` per specificare una directory specifica).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-212">After the template is installed from the file system, use the template by executing the `dotnet new <TEMPLATE>` command from the directory where you want to the template engine's output placed (unless you're using the `-o|--output` option to specify a specific directory).</span></span> <span data-ttu-id="e6c9d-213">Per altre informazioni, vedere [`dotnet new` Opzioni](~/docs/core/tools/dotnet-new.md#options).</span><span class="sxs-lookup"><span data-stu-id="e6c9d-213">For more information, see [`dotnet new` Options](~/docs/core/tools/dotnet-new.md#options).</span></span> <span data-ttu-id="e6c9d-214">Specificare il nome breve del modello direttamente nel comando `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-214">Supply the template's short name directly to the `dotnet new` command.</span></span>

<span data-ttu-id="e6c9d-215">Da una nuova cartella di progetto creata in *C:\Users\\\<UTENTE>\Documents\Projects\MyConsoleApp* creare un progetto dal modello `garciaconsole`:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-215">From a new project folder created at *C:\Users\\\<USER>\Documents\Projects\MyConsoleApp*, create a project from the `garciaconsole` template:</span></span>

```console
dotnet new garciaconsole
```

### <a name="uninstall-the-template"></a><span data-ttu-id="e6c9d-216">Disinstallare il modello</span><span class="sxs-lookup"><span data-stu-id="e6c9d-216">Uninstall the template</span></span>

<span data-ttu-id="e6c9d-217">Se il modello è stato creato nel file system locale in *C:\Users\\\<UTENTE>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, disinstallarlo con l'opzione `-u|--uninstall` e il percorso della cartella di modello:</span><span class="sxs-lookup"><span data-stu-id="e6c9d-217">If you created the template on your local file system at *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp*, uninstall it with the `-u|--uninstall` switch and the path to the template folder:</span></span>

```console
dotnet new -u C:\Users\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp
```

> [!NOTE]
> <span data-ttu-id="e6c9d-218">Per disinstallare il modello dal file system locale, è necessario specificare il percorso completo.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-218">To uninstall the template from your local file system, you need to fully qualify the path.</span></span> <span data-ttu-id="e6c9d-219">Ad esempio, *C:\Users\\\<UTENTE>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* è corretto, ma *./GarciaSoftware.ConsoleTemplate.CSharp* dalla cartella contenitore non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-219">For example, *C:\Users\\\<USER>\Documents\Templates\GarciaSoftware.ConsoleTemplate.CSharp* will work, but *./GarciaSoftware.ConsoleTemplate.CSharp* from the containing folder will not.</span></span>
> <span data-ttu-id="e6c9d-220">Inoltre, non includere la barra finale di terminazione della directory nel percorso del modello.</span><span class="sxs-lookup"><span data-stu-id="e6c9d-220">Additionally, do not include a final terminating directory slash on your template path.</span></span>

## <a name="see-also"></a><span data-ttu-id="e6c9d-221">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6c9d-221">See also</span></span>

* [<span data-ttu-id="e6c9d-222">Wiki del repository GitHub dotnet/templating</span><span class="sxs-lookup"><span data-stu-id="e6c9d-222">dotnet/templating GitHub repo Wiki</span></span>](https://github.com/dotnet/templating/wiki)  
* [<span data-ttu-id="e6c9d-223">Repository GitHub dotnet/dotnet-template-samples</span><span class="sxs-lookup"><span data-stu-id="e6c9d-223">dotnet/dotnet-template-samples GitHub repo</span></span>](https://github.com/dotnet/dotnet-template-samples)  
* [<span data-ttu-id="e6c9d-224">Come creare modelli personalizzati per dotnet new</span><span class="sxs-lookup"><span data-stu-id="e6c9d-224">How to create your own templates for dotnet new</span></span>](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)
* <span data-ttu-id="e6c9d-225">Lo schema [*template.JSON* nell'archivio di schemi JSON](http://json.schemastore.org/template)</span><span class="sxs-lookup"><span data-stu-id="e6c9d-225">[*template.json* schema at the JSON Schema Store](http://json.schemastore.org/template)</span></span>  
