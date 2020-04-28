---
title: Installare e gestire modelli SDK-.NET Core
description: Informazioni su come installare i modelli .NET Core in Windows, Linux e macOS.
author: thraka
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 0a3c8655d55bf63de1e91337ce3a2ac399b07d0f
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "82200615"
---
# <a name="manage-net-project-and-item-templates"></a><span data-ttu-id="3015d-103">Gestire modelli di progetti e di elementi .NET</span><span class="sxs-lookup"><span data-stu-id="3015d-103">Manage .NET project and item templates</span></span>

<span data-ttu-id="3015d-104">.NET Core fornisce un sistema di modelli che consente agli utenti di installare o disinstallare modelli da NuGet, da un file di pacchetto NuGet o da una directory file system.</span><span class="sxs-lookup"><span data-stu-id="3015d-104">.NET Core provides a template system that enables users to install or uninstall templates from NuGet, a NuGet package file, or a file system directory.</span></span> <span data-ttu-id="3015d-105">Questo articolo descrive come gestire i modelli .NET Core tramite l'interfaccia della riga di comando .NET Core SDK.</span><span class="sxs-lookup"><span data-stu-id="3015d-105">This article describes how to manage .NET Core templates through the .NET Core SDK CLI.</span></span>

<span data-ttu-id="3015d-106">Per ulteriori informazioni sulla creazione di modelli, vedere [esercitazione: creare modelli](../tutorials/cli-templates-create-item-template.md).</span><span class="sxs-lookup"><span data-stu-id="3015d-106">For more information about creating templates, see [Tutorial: Create templates](../tutorials/cli-templates-create-item-template.md).</span></span>

## <a name="install-template"></a><span data-ttu-id="3015d-107">Installa modello</span><span class="sxs-lookup"><span data-stu-id="3015d-107">Install template</span></span>

<span data-ttu-id="3015d-108">I modelli vengono installati tramite il comando [DotNet New](../tools/dotnet-new.md) SDK con `-i` il parametro.</span><span class="sxs-lookup"><span data-stu-id="3015d-108">Templates are installed through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-i` parameter.</span></span> <span data-ttu-id="3015d-109">È possibile specificare l'identificatore del pacchetto NuGet di un modello o una cartella che contiene i file modello.</span><span class="sxs-lookup"><span data-stu-id="3015d-109">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-hosted-package"></a><span data-ttu-id="3015d-110">Pacchetto NuGet ospitato</span><span class="sxs-lookup"><span data-stu-id="3015d-110">NuGet hosted package</span></span>

<span data-ttu-id="3015d-111">I modelli dell'interfaccia della riga di comando .NET vengono caricati in [NuGet](https://www.nuget.org/) per la distribuzione estesa.</span><span class="sxs-lookup"><span data-stu-id="3015d-111">.NET CLI templates are uploaded to [NuGet](https://www.nuget.org/) for wide distribution.</span></span> <span data-ttu-id="3015d-112">I modelli possono anche essere installati da un feed privato.</span><span class="sxs-lookup"><span data-stu-id="3015d-112">Templates can also be installed from a private feed.</span></span> <span data-ttu-id="3015d-113">Anziché caricare un modello in un feed NuGet, i file di modello *nupkg* possono essere distribuiti e installati manualmente, come descritto nella sezione [pacchetto NuGet locale](#local-nuget-package) .</span><span class="sxs-lookup"><span data-stu-id="3015d-113">Instead of uploading a template to a NuGet feed, *nupkg* template files can be distributed and manually installed, as described in the [Local NuGet package](#local-nuget-package) section.</span></span>

<span data-ttu-id="3015d-114">Per ulteriori informazioni sulla configurazione dei feed NuGet, vedere [DotNet NuGet Add Source](../tools/dotnet-nuget-add-source.md).</span><span class="sxs-lookup"><span data-stu-id="3015d-114">For more information about configuring NuGet feeds, see [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).</span></span>

<span data-ttu-id="3015d-115">Per installare un pacchetto di modelli dal feed NuGet predefinito, usare il `dotnet new -i {package-id}` comando:</span><span class="sxs-lookup"><span data-stu-id="3015d-115">To install a template pack from the default NuGet feed, use the `dotnet new -i {package-id}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

<span data-ttu-id="3015d-116">Per installare un pacchetto di modelli dal feed NuGet predefinito con una versione specifica, usare il `dotnet new -i {package-id}::{version}` comando:</span><span class="sxs-lookup"><span data-stu-id="3015d-116">To install a template pack from the default NuGet feed with a specific version, use the `dotnet new -i {package-id}::{version}` command:</span></span>

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a><span data-ttu-id="3015d-117">Pacchetto NuGet locale</span><span class="sxs-lookup"><span data-stu-id="3015d-117">Local NuGet package</span></span>

<span data-ttu-id="3015d-118">Quando viene creato un pacchetto di modelli, viene generato un file *nupkg* .</span><span class="sxs-lookup"><span data-stu-id="3015d-118">When a template pack is created, a *nupkg* file is generated.</span></span> <span data-ttu-id="3015d-119">Se si dispone di un file *nupkg* che contiene modelli, è possibile installarlo `dotnet new -i {path-to-package}` con il comando:</span><span class="sxs-lookup"><span data-stu-id="3015d-119">If you have a *nupkg* file containing templates, you can install it with the `dotnet new -i {path-to-package}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\Some.Templates.1.0.0.nupkg
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/Some.Templates.1.0.0.nupkg
```

::: zone-end

### <a name="folder"></a><span data-ttu-id="3015d-120">Cartella</span><span class="sxs-lookup"><span data-stu-id="3015d-120">Folder</span></span>

<span data-ttu-id="3015d-121">In alternativa all'installazione di un modello da un file *nupkg* , è anche possibile installare modelli da una cartella direttamente con `dotnet new -i {folder-path}` il comando.</span><span class="sxs-lookup"><span data-stu-id="3015d-121">As an alternative to installing template from a *nupkg* file, you can also install templates from a folder directly with the `dotnet new -i {folder-path}` command.</span></span> <span data-ttu-id="3015d-122">La cartella specificata viene considerata come identificatore del pacchetto di modelli per tutti i modelli trovati.</span><span class="sxs-lookup"><span data-stu-id="3015d-122">The folder specified is treated as the template pack identifier for any template found.</span></span> <span data-ttu-id="3015d-123">Viene installato qualsiasi modello trovato nella gerarchia della cartella specificata.</span><span class="sxs-lookup"><span data-stu-id="3015d-123">Any template found in the specified folder's hierarchy is installed.</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\some-folder\
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/some-folder/
```

::: zone-end

<span data-ttu-id="3015d-124">Il `{folder-path}` parametro specificato nel comando diventa l'identificatore del pacchetto di modelli per tutti i modelli trovati.</span><span class="sxs-lookup"><span data-stu-id="3015d-124">The `{folder-path}` specified on the command becomes the template pack identifier for all templates found.</span></span> <span data-ttu-id="3015d-125">Come specificato nella sezione [modelli elenco](#list-templates) , è possibile ottenere un elenco dei modelli installati con il `dotnet new -u` comando.</span><span class="sxs-lookup"><span data-stu-id="3015d-125">As specified in the [List templates](#list-templates) section, you can get a list of templates installed with the `dotnet new -u` command.</span></span> <span data-ttu-id="3015d-126">In questo esempio, l'identificatore del pacchetto di modelli viene visualizzato come cartella usata per l'installazione:</span><span class="sxs-lookup"><span data-stu-id="3015d-126">In this example, the template pack identifier is shown as the folder used for install:</span></span>

::: zone pivot="os-windows"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  /home/username/code/templates
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="uninstall-template"></a><span data-ttu-id="3015d-127">Disinstalla modello</span><span class="sxs-lookup"><span data-stu-id="3015d-127">Uninstall template</span></span>

<span data-ttu-id="3015d-128">I modelli vengono disinstallati tramite il comando [DotNet New](../tools/dotnet-new.md) SDK con `-u` il parametro.</span><span class="sxs-lookup"><span data-stu-id="3015d-128">Templates are uninstalled through the [dotnet new](../tools/dotnet-new.md) SDK command with the `-u` parameter.</span></span> <span data-ttu-id="3015d-129">È possibile specificare l'identificatore del pacchetto NuGet di un modello o una cartella che contiene i file modello.</span><span class="sxs-lookup"><span data-stu-id="3015d-129">You can either provide the NuGet package identifier of a template, or a folder that contains the template files.</span></span>

### <a name="nuget-package"></a><span data-ttu-id="3015d-130">Pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="3015d-130">NuGet package</span></span>

<span data-ttu-id="3015d-131">Dopo l'installazione di un pacchetto di modelli NuGet, da un feed NuGet o da un file *nupkg* , è possibile disinstallarlo facendo riferimento all'identificatore del pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="3015d-131">After a NuGet template pack is installed, either from a NuGet feed or a *nupkg* file, you can uninstall it by referencing the NuGet package identifier.</span></span>

<span data-ttu-id="3015d-132">Per disinstallare un pacchetto di modelli, usare `dotnet new -u {package-id}` il comando:</span><span class="sxs-lookup"><span data-stu-id="3015d-132">To uninstall a template pack, use the `dotnet new -u {package-id}` command:</span></span>

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a><span data-ttu-id="3015d-133">Cartella</span><span class="sxs-lookup"><span data-stu-id="3015d-133">Folder</span></span>

<span data-ttu-id="3015d-134">Quando si installano i modelli tramite un [percorso di cartella](#folder), il percorso della cartella diventa l'identificatore del pacchetto di modelli.</span><span class="sxs-lookup"><span data-stu-id="3015d-134">When templates are installed through a [folder path](#folder), the folder path becomes the template pack identifier.</span></span>

<span data-ttu-id="3015d-135">Per disinstallare un pacchetto di modelli, usare `dotnet new -u {package-folder-path}` il comando:</span><span class="sxs-lookup"><span data-stu-id="3015d-135">To uninstall a template pack, use the `dotnet new -u {package-folder-path}` command:</span></span>

::: zone pivot="os-windows"

```dotnetcli
dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="list-templates"></a><span data-ttu-id="3015d-136">Elenca modelli</span><span class="sxs-lookup"><span data-stu-id="3015d-136">List templates</span></span>

<span data-ttu-id="3015d-137">Utilizzando il comando di disinstallazione standard senza un identificatore del pacchetto, è possibile visualizzare un elenco dei modelli installati insieme al comando che disinstalla ogni modello.</span><span class="sxs-lookup"><span data-stu-id="3015d-137">By using the standard uninstall command without a package identifier, you can see a list of installed templates along with the command that uninstalls each template.</span></span>

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

## <a name="install-templates-from-other-sdks"></a><span data-ttu-id="3015d-138">Installare modelli da altri SDK</span><span class="sxs-lookup"><span data-stu-id="3015d-138">Install templates from other SDKs</span></span>

<span data-ttu-id="3015d-139">Se ogni versione dell'SDK è stata installata in modo sequenziale, ad esempio se è stato installato SDK 2,0, SDK 2,1 e così via, saranno installati tutti i modelli di SDK.</span><span class="sxs-lookup"><span data-stu-id="3015d-139">If you've installed each version of the SDK sequentially, for example you installed SDK 2.0, then SDK 2.1, and so on, you'll have every SDK's templates installed.</span></span> <span data-ttu-id="3015d-140">Tuttavia, se si inizia con una versione più recente dell'SDK, ad esempio 3,1, vengono inclusi solo i modelli per le [versioni LTS (supporto a lungo termine)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) , che al momento della versione SDK 3,1 sono SDK 2,1 e SDK 3,1.</span><span class="sxs-lookup"><span data-stu-id="3015d-140">However, if you start with a later SDK version, like 3.1, only the templates for [LTS (long term support) releases](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) are included, which at the time of the SDK 3.1 release is SDK 2.1 and SDK 3.1.</span></span> <span data-ttu-id="3015d-141">I modelli per qualsiasi altra versione non sono inclusi.</span><span class="sxs-lookup"><span data-stu-id="3015d-141">Templates for any other release aren't included.</span></span>

<span data-ttu-id="3015d-142">I modelli .NET Core sono disponibili in NuGet ed è possibile installarli come qualsiasi altro modello.</span><span class="sxs-lookup"><span data-stu-id="3015d-142">The .NET Core templates are available on NuGet, and you can install them like any other template.</span></span> <span data-ttu-id="3015d-143">Per altre informazioni, vedere [Install NuGet Hosted Package](#nuget-hosted-package).</span><span class="sxs-lookup"><span data-stu-id="3015d-143">For more information, see [Install NuGet hosted package](#nuget-hosted-package).</span></span>

| <span data-ttu-id="3015d-144">SDK</span><span class="sxs-lookup"><span data-stu-id="3015d-144">SDK</span></span>              | <span data-ttu-id="3015d-145">Identificatore del pacchetto NuGet</span><span class="sxs-lookup"><span data-stu-id="3015d-145">NuGet Package Identifier</span></span>                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="3015d-146">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3015d-146">.NET Core 2.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| <span data-ttu-id="3015d-147">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="3015d-147">.NET Core 2.2</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| <span data-ttu-id="3015d-148">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3015d-148">.NET Core 3.0</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| <span data-ttu-id="3015d-149">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="3015d-149">.NET Core 3.1</span></span>    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| <span data-ttu-id="3015d-150">ASP.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="3015d-150">ASP.NET Core 2.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| <span data-ttu-id="3015d-151">ASP.NET Core 2,2</span><span class="sxs-lookup"><span data-stu-id="3015d-151">ASP.NET Core 2.2</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| <span data-ttu-id="3015d-152">ASP.NET Core 3,0</span><span class="sxs-lookup"><span data-stu-id="3015d-152">ASP.NET Core 3.0</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| <span data-ttu-id="3015d-153">ASP.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="3015d-153">ASP.NET Core 3.1</span></span> | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

<span data-ttu-id="3015d-154">Ad esempio, il .NET Core SDK include modelli per un'app console destinata a .NET Core 2,1 e .NET Core 3,1.</span><span class="sxs-lookup"><span data-stu-id="3015d-154">For example, the .NET Core SDK includes templates for a console app targeting .NET Core 2.1 and .NET Core 3.1.</span></span> <span data-ttu-id="3015d-155">Se si vuole specificare come destinazione .NET Core 3,0, è necessario installare i modelli 3,0.</span><span class="sxs-lookup"><span data-stu-id="3015d-155">If you wanted to target .NET Core 3.0, you would need to install the 3.0 templates.</span></span>

01. <span data-ttu-id="3015d-156">Provare a creare un'app destinata a .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="3015d-156">Try creating an app that targets .NET Core 3.0.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="3015d-157">Se viene visualizzato un messaggio di errore, è necessario installare i modelli.</span><span class="sxs-lookup"><span data-stu-id="3015d-157">If you see an error message, you need to install the templates.</span></span>

    > <span data-ttu-id="3015d-158">Non è stato trovato alcun modello installato che corrisponda all'input, che esegue la ricerca online...</span><span class="sxs-lookup"><span data-stu-id="3015d-158">Couldn't find an installed template that matches the input, searching online for one that does...</span></span>

01. <span data-ttu-id="3015d-159">Installare i modelli di progetto .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="3015d-159">Install the .NET Core 3.0 project templates.</span></span>

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. <span data-ttu-id="3015d-160">Provare a creare l'app una seconda volta.</span><span class="sxs-lookup"><span data-stu-id="3015d-160">Try creating the app a second time.</span></span>

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    <span data-ttu-id="3015d-161">Verrà visualizzato un messaggio che indica che il progetto è stato creato.</span><span class="sxs-lookup"><span data-stu-id="3015d-161">And you should see a message indicating the project was created.</span></span>

    > <span data-ttu-id="3015d-162">Creazione del modello "applicazione console" completata.</span><span class="sxs-lookup"><span data-stu-id="3015d-162">The template "Console Application" was created successfully.</span></span>
    >
    > <span data-ttu-id="3015d-163">Elaborazione delle azioni di post-creazione... Esecuzione di ' dotnet restore ' in path-to-Project-file. csproj in corso... Determinazione progetti da ripristinare... Il ripristino è stato completato in 1,05 secondi per path-to-Project-file. csproj.</span><span class="sxs-lookup"><span data-stu-id="3015d-163">Processing post-creation actions... Running 'dotnet restore' on path-to-project-file.csproj... Determining projects to restore... Restore completed in 1.05 sec for path-to-project-file.csproj.</span></span>
    >
    > <span data-ttu-id="3015d-164">Ripristino completato.</span><span class="sxs-lookup"><span data-stu-id="3015d-164">Restore succeeded.</span></span>

## <a name="see-also"></a><span data-ttu-id="3015d-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3015d-165">See also</span></span>

- [<span data-ttu-id="3015d-166">Esercitazione: creare un modello di elemento</span><span class="sxs-lookup"><span data-stu-id="3015d-166">Tutorial: Create an item template</span></span>](../tutorials/cli-templates-create-item-template.md)
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
