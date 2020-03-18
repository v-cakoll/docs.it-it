---
title: Strumenti .NET Core
description: Come installare, utilizzare, aggiornare e rimuovere gli strumenti di .NET Core. Vengono illustrati gli strumenti globali, gli strumenti del percorso degli strumenti e gli strumenti locali.
author: KathleenDollard
ms.date: 02/12/2020
ms.openlocfilehash: 2f0101c6385c41eda49bcb2458428c1f14552617
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847787"
---
# <a name="how-to-manage-net-core-tools"></a><span data-ttu-id="0146e-104">Come gestire gli strumenti di .NET Core</span><span class="sxs-lookup"><span data-stu-id="0146e-104">How to manage .NET Core tools</span></span>

<span data-ttu-id="0146e-105">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="0146e-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="0146e-106">Uno strumento .NET Core è un pacchetto NuGet speciale che contiene un'applicazione console.</span><span class="sxs-lookup"><span data-stu-id="0146e-106">A .NET Core tool is a special NuGet package that contains a console application.</span></span> <span data-ttu-id="0146e-107">Un utensile può essere installato sul computer nei seguenti modi:</span><span class="sxs-lookup"><span data-stu-id="0146e-107">A tool can be installed on your machine in the following ways:</span></span>

* <span data-ttu-id="0146e-108">Come strumento globale.</span><span class="sxs-lookup"><span data-stu-id="0146e-108">As a global tool.</span></span>

  <span data-ttu-id="0146e-109">I file binari dello strumento vengono installati in una directory predefinita che viene aggiunta alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="0146e-109">The tool binaries are installed in a default directory that is added to the PATH environment variable.</span></span> <span data-ttu-id="0146e-110">È possibile richiamare lo strumento da qualsiasi directory del computer senza specificarne la posizione.</span><span class="sxs-lookup"><span data-stu-id="0146e-110">You can invoke the tool from any directory on the machine without specifying its location.</span></span> <span data-ttu-id="0146e-111">Una versione di uno strumento viene utilizzata per tutte le directory del computer.</span><span class="sxs-lookup"><span data-stu-id="0146e-111">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="0146e-112">Come strumento globale in una posizione personalizzata (noto anche come strumento di percorso degli strumenti).</span><span class="sxs-lookup"><span data-stu-id="0146e-112">As a global tool in a custom location (also known as a tool-path tool).</span></span>

  <span data-ttu-id="0146e-113">I file binari dello strumento vengono installati in un percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="0146e-113">The tool binaries are installed in a location that you specify.</span></span> <span data-ttu-id="0146e-114">È possibile richiamare lo strumento dalla directory di installazione o fornendo alla directory il nome del comando o aggiungendo la directory alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="0146e-114">You can invoke the tool from the installation directory or by providing the directory with the command name or by adding the directory to the PATH environment variable.</span></span> <span data-ttu-id="0146e-115">Una versione di uno strumento viene utilizzata per tutte le directory del computer.</span><span class="sxs-lookup"><span data-stu-id="0146e-115">One version of a tool is used for all directories on the machine.</span></span>

* <span data-ttu-id="0146e-116">Come strumento locale (si applica a .NET Core SDK 3.0 e versioni successive).</span><span class="sxs-lookup"><span data-stu-id="0146e-116">As a local tool (applies to .NET Core SDK 3.0 and later).</span></span>

  <span data-ttu-id="0146e-117">I file binari dello strumento vengono installati in una directory predefinita.</span><span class="sxs-lookup"><span data-stu-id="0146e-117">The tool binaries are installed in a default directory.</span></span> <span data-ttu-id="0146e-118">Richiamare lo strumento dalla directory di installazione o da una delle relative sottodirectory.</span><span class="sxs-lookup"><span data-stu-id="0146e-118">You invoke the tool from the installation directory or any of its subdirectories.</span></span> <span data-ttu-id="0146e-119">Directory diverse possono utilizzare versioni diverse dello stesso strumento.</span><span class="sxs-lookup"><span data-stu-id="0146e-119">Different directories can use different versions of the same tool.</span></span>
  
  <span data-ttu-id="0146e-120">L'interfaccia della riga di comando .NET utilizza i file manifesto per tenere traccia degli strumenti installati come locali in una directory.</span><span class="sxs-lookup"><span data-stu-id="0146e-120">The .NET CLI uses manifest files to keep track of which tools are installed as local to a directory.</span></span> <span data-ttu-id="0146e-121">Quando il file manifesto viene salvato nella directory radice di un repository di codice sorgente, un collaboratore può clonare il repository e richiamare un singolo comando .NET Core CLI che installa tutti gli strumenti elencati nei file manifesto.</span><span class="sxs-lookup"><span data-stu-id="0146e-121">When the manifest file is saved in the root directory of a source code repository, a contributor can clone the repository and invoke a single .NET Core CLI command that installs all of the tools listed in the manifest files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0146e-122">Gli strumenti .NET Core vengono eseguiti con attendibilità totale.</span><span class="sxs-lookup"><span data-stu-id="0146e-122">.NET Core tools run in full trust.</span></span> <span data-ttu-id="0146e-123">Non installare uno strumento .NET Core a meno che non si consideri attendibile l'autore.</span><span class="sxs-lookup"><span data-stu-id="0146e-123">Do not install a .NET Core tool unless you trust the author.</span></span>

## <a name="find-a-tool"></a><span data-ttu-id="0146e-124">Trovare uno strumento</span><span class="sxs-lookup"><span data-stu-id="0146e-124">Find a tool</span></span>

<span data-ttu-id="0146e-125">Attualmente, .NET Core non dispone di una funzionalità di ricerca degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="0146e-125">Currently, .NET Core doesn't have a tool search feature.</span></span> <span data-ttu-id="0146e-126">Ecco alcuni modi per trovare gli strumenti:</span><span class="sxs-lookup"><span data-stu-id="0146e-126">Here are some ways to find tools:</span></span>

* <span data-ttu-id="0146e-127">Vedere l'elenco degli strumenti nel repository GitHub di [natemcmaster/dotnet-tools.](https://github.com/natemcmaster/dotnet-tools)</span><span class="sxs-lookup"><span data-stu-id="0146e-127">See the list of tools in the [natemcmaster/dotnet-tools](https://github.com/natemcmaster/dotnet-tools) GitHub repository.</span></span>
* <span data-ttu-id="0146e-128">Utilizzare [ToolGet](https://www.toolget.net/) per cercare gli strumenti .NET.</span><span class="sxs-lookup"><span data-stu-id="0146e-128">Use [ToolGet](https://www.toolget.net/) to search for .NET tools.</span></span>
* <span data-ttu-id="0146e-129">Vedere il codice sorgente per gli strumenti creati dal team di ASP.NET Core nella [directory Tools del repository dotnet/aspnetcore GitHub](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).</span><span class="sxs-lookup"><span data-stu-id="0146e-129">See the source code for the tools created by the ASP.NET Core team in the [Tools directory of the dotnet/aspnetcore GitHub repository](https://github.com/dotnet/aspnetcore/tree/master/src/Tools).</span></span>
* <span data-ttu-id="0146e-130">Per informazioni sugli strumenti di diagnostica, vedere [Strumenti di diagnostica dotnet di .NET Core](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span><span class="sxs-lookup"><span data-stu-id="0146e-130">Learn about diagnostic tools at [.NET Core dotnet diagnostic tools](../diagnostics/index.md#net-core-dotnet-diagnostic-global-tools).</span></span>
* <span data-ttu-id="0146e-131">Cerca nel sito Web [NuGet.](https://www.nuget.org)</span><span class="sxs-lookup"><span data-stu-id="0146e-131">Search the [NuGet](https://www.nuget.org) website.</span></span> <span data-ttu-id="0146e-132">Tuttavia, il sito NuGet non dispone ancora di una funzionalità che consente di cercare solo i pacchetti di strumenti.</span><span class="sxs-lookup"><span data-stu-id="0146e-132">However, the NuGet site doesn't yet have a feature that lets you search only for tool packages.</span></span>

## <a name="check-the-author-and-statistics"></a><span data-ttu-id="0146e-133">Verificare l'autore e le statistiche</span><span class="sxs-lookup"><span data-stu-id="0146e-133">Check the author and statistics</span></span>

<span data-ttu-id="0146e-134">Poiché gli strumenti .NET Core vengono eseguiti con attendibilità totale e gli strumenti globali vengono aggiunti alla variabile di ambiente PATH, possono essere molto potenti.</span><span class="sxs-lookup"><span data-stu-id="0146e-134">Since .NET Core tools run in full trust, and global tools are added to the PATH environment variable, they can be very powerful.</span></span> <span data-ttu-id="0146e-135">Non scaricare gli strumenti da utenti non attendibili.</span><span class="sxs-lookup"><span data-stu-id="0146e-135">Don't download tools from people you don't trust.</span></span>

<span data-ttu-id="0146e-136">Se lo strumento è ospitato su NuGet, è possibile verificare l'autore e le statistiche eseguendo una ricerca dello strumento.</span><span class="sxs-lookup"><span data-stu-id="0146e-136">If the tool is hosted on NuGet, you can check the author and statistics by searching for the tool.</span></span>

## <a name="install-a-global-tool"></a><span data-ttu-id="0146e-137">Installare uno strumento globale</span><span class="sxs-lookup"><span data-stu-id="0146e-137">Install a global tool</span></span>

<span data-ttu-id="0146e-138">Per installare uno strumento come strumento `-g` `--global` globale, utilizzare l'opzione o di [installazione dello strumento dotnet](dotnet-tool-install.md), come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0146e-138">To install a tool as a global tool, use the `-g` or `--global` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following example:</span></span>

```dotnetcli
dotnet tool install -g dotnetsay
```

<span data-ttu-id="0146e-139">L'output mostra il comando utilizzato per richiamare lo strumento e la versione installata, simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0146e-139">The output shows the command used to invoke the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
```

<span data-ttu-id="0146e-140">Il percorso predefinito per i file binari di uno strumento dipende dal sistema operativo:</span><span class="sxs-lookup"><span data-stu-id="0146e-140">The default location for a tool's binaries depends on the operating system:</span></span>

| <span data-ttu-id="0146e-141">OS</span><span class="sxs-lookup"><span data-stu-id="0146e-141">OS</span></span>          | <span data-ttu-id="0146e-142">Path</span><span class="sxs-lookup"><span data-stu-id="0146e-142">Path</span></span>                          |
|-------------|-------------------------------|
| <span data-ttu-id="0146e-143">Linux/macOS</span><span class="sxs-lookup"><span data-stu-id="0146e-143">Linux/macOS</span></span> | `$HOME/.dotnet/tools`         |
| <span data-ttu-id="0146e-144">Windows</span><span class="sxs-lookup"><span data-stu-id="0146e-144">Windows</span></span>     | `%USERPROFILE%\.dotnet\tools` |

<span data-ttu-id="0146e-145">Questo percorso viene aggiunto al percorso dell'utente quando l'SDK viene eseguito per la prima volta, pertanto gli strumenti globali possono essere richiamati da qualsiasi directory senza specificare il percorso dello strumento.</span><span class="sxs-lookup"><span data-stu-id="0146e-145">This location is added to the user's path when the SDK is first run, so global tools can be invoked from any directory without specifying the tool location.</span></span>

<span data-ttu-id="0146e-146">L'accesso agli strumenti è specifico dell'utente, non globale del computer.</span><span class="sxs-lookup"><span data-stu-id="0146e-146">Tool access is user-specific, not machine global.</span></span> <span data-ttu-id="0146e-147">Uno strumento globale è disponibile solo per l'utente che lo ha installato.</span><span class="sxs-lookup"><span data-stu-id="0146e-147">A global tool is only available to the user that installed the tool.</span></span>

### <a name="install-a-global-tool-in-a-custom-location"></a><span data-ttu-id="0146e-148">Installare uno strumento globale in una posizione personalizzataInstall a global tool in a custom location</span><span class="sxs-lookup"><span data-stu-id="0146e-148">Install a global tool in a custom location</span></span>

<span data-ttu-id="0146e-149">Per installare uno strumento come strumento globale in `--tool-path` un percorso personalizzato, utilizzare l'opzione di installazione dello [strumento dotnet](dotnet-tool-install.md), come illustrato negli esempi seguenti.</span><span class="sxs-lookup"><span data-stu-id="0146e-149">To install a tool as a global tool in a custom location, use the `--tool-path` option of [dotnet tool install](dotnet-tool-install.md), as shown in the following examples.</span></span>

<span data-ttu-id="0146e-150">In Windows:</span><span class="sxs-lookup"><span data-stu-id="0146e-150">On Windows:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path c:\dotnet-tools
```

<span data-ttu-id="0146e-151">Su Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="0146e-151">On Linux or macOS:</span></span>

```dotnetcli
dotnet tool install dotnetsay --tool-path ~/bin
```

<span data-ttu-id="0146e-152">.NET Core SDK non aggiunge automaticamente questo percorso alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="0146e-152">The .NET Core SDK doesn't add this location automatically to the PATH environment variable.</span></span> <span data-ttu-id="0146e-153">Per [richiamare uno strumento del percorso](#invoke-a-tool-path-tool)degli strumenti, è necessario assicurarsi che il comando sia disponibile utilizzando uno dei seguenti metodi:</span><span class="sxs-lookup"><span data-stu-id="0146e-153">To [invoke a tool-path tool](#invoke-a-tool-path-tool), you have to make sure the command is available by using one of the following methods:</span></span>

* <span data-ttu-id="0146e-154">Aggiungere la directory di installazione alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="0146e-154">Add the installation directory to the PATH environment variable.</span></span>
* <span data-ttu-id="0146e-155">Specificare il percorso completo dello strumento quando lo si richiama.</span><span class="sxs-lookup"><span data-stu-id="0146e-155">Specify the full path to the tool when you invoke it.</span></span>
* <span data-ttu-id="0146e-156">Richiamare lo strumento dall'interno della directory di installazione.</span><span class="sxs-lookup"><span data-stu-id="0146e-156">Invoke the tool from within the installation directory.</span></span>

## <a name="install-a-local-tool"></a><span data-ttu-id="0146e-157">Installare uno strumento locale</span><span class="sxs-lookup"><span data-stu-id="0146e-157">Install a local tool</span></span>

<span data-ttu-id="0146e-158">**Si applica a .NET Core 3.0 SDK e versioni successive.**</span><span class="sxs-lookup"><span data-stu-id="0146e-158">**Applies to .NET Core 3.0 SDK and later.**</span></span>

<span data-ttu-id="0146e-159">Per installare uno strumento solo per l'accesso locale (per la directory corrente e le sottodirectory), è necessario aggiungerlo a un file manifesto dello strumento.</span><span class="sxs-lookup"><span data-stu-id="0146e-159">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a tool manifest file.</span></span> <span data-ttu-id="0146e-160">Per creare un file manifesto `dotnet new tool-manifest` dello strumento, eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="0146e-160">To create a tool manifest file, run the `dotnet new tool-manifest` command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="0146e-161">Questo comando crea un file manifesto denominato *dotnet-tools.json* nella directory *.config.*</span><span class="sxs-lookup"><span data-stu-id="0146e-161">This command creates a manifest file named *dotnet-tools.json* under the *.config* directory.</span></span> <span data-ttu-id="0146e-162">Per aggiungere uno strumento locale al file manifesto, utilizzare il comando `--global` `--tool-path` [dotnet tool install](dotnet-tool-install.md) e **omettere** le opzioni e , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0146e-162">To add a local tool to the manifest file, use the [dotnet tool install](dotnet-tool-install.md) command and **omit** the `--global` and `--tool-path` options, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay
```

<span data-ttu-id="0146e-163">L'output del comando mostra in quale file manifesto si trova lo strumento appena installato, simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0146e-163">The command output shows which manifest file the newly installed tool is in, similar to the following example:</span></span>

```console
You can invoke the tool from this directory using the following command:
dotnet tool run dotnetsay
Tool 'dotnetsay' (version '2.1.4') was successfully installed.
Entry is added to the manifest file /home/name/botsay/.config/dotnet-tools.json.
```

<span data-ttu-id="0146e-164">Nell'esempio seguente viene illustrato un file manifesto con due strumenti locali installati:The following example shows a manifest file with two local tools installed:</span><span class="sxs-lookup"><span data-stu-id="0146e-164">The following example shows a manifest file with two local tools installed:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    },
    "dotnetsay": {
      "version": "2.1.3",
      "commands": [
        "dotnetsay"
      ]
    }
  }
}
```

<span data-ttu-id="0146e-165">In genere si aggiunge uno strumento locale alla directory radice del repository.</span><span class="sxs-lookup"><span data-stu-id="0146e-165">You typically add a local tool to the root directory of the repository.</span></span> <span data-ttu-id="0146e-166">Dopo aver archiviato il file manifesto nel repository, gli sviluppatori che estraono il codice dal repository ottengono il file manifesto più recente.</span><span class="sxs-lookup"><span data-stu-id="0146e-166">After you check in the manifest file to the repository, developers who check out code from the repository get the latest manifest file.</span></span> <span data-ttu-id="0146e-167">Per installare tutti gli strumenti elencati nel `dotnet tool restore` file manifesto, eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="0146e-167">To install all of the tools listed in the manifest file, they run the `dotnet tool restore` command:</span></span>

```dotnetcli
dotnet tool restore
```

<span data-ttu-id="0146e-168">L'output indica quali strumenti sono stati ripristinati:</span><span class="sxs-lookup"><span data-stu-id="0146e-168">The output indicates which tools were restored:</span></span>

```console
Tool 'botsay' (version '1.0.0') was restored. Available commands: botsay
Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
Restore was successful.
```

## <a name="install-a-specific-tool-version"></a><span data-ttu-id="0146e-169">Installare una versione specifica dello strumento</span><span class="sxs-lookup"><span data-stu-id="0146e-169">Install a specific tool version</span></span>

<span data-ttu-id="0146e-170">Per installare una versione non definitiva o una versione specifica di `--version` uno strumento, specificare il numero di versione utilizzando l'opzione , come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="0146e-170">To install a pre-release version or a specific version of a tool, specify the version number by using the `--version` option, as shown in the following example:</span></span>

```dotnetcli
dotnet tool install dotnetsay --version 2.1.3
```

## <a name="use-a-tool"></a><span data-ttu-id="0146e-171">Utilizzare uno strumento</span><span class="sxs-lookup"><span data-stu-id="0146e-171">Use a tool</span></span>

<span data-ttu-id="0146e-172">Il comando utilizzato per richiamare uno strumento potrebbe essere diverso dal nome del pacchetto installato.</span><span class="sxs-lookup"><span data-stu-id="0146e-172">The command that you use to invoke a tool may be different from the name of the package that you install.</span></span> <span data-ttu-id="0146e-173">Per visualizzare tutti gli strumenti attualmente installati nel computer per l'utente corrente, utilizzare il comando [dotnet tool list:](dotnet-tool-list.md)</span><span class="sxs-lookup"><span data-stu-id="0146e-173">To display all of the tools currently installed on the machine for the current user, use the [dotnet tool list](dotnet-tool-list.md) command:</span></span>

```dotnetcli
dotnet tool list
```

<span data-ttu-id="0146e-174">L'output mostra la versione e il comando di ogni strumento, simile all'esempio seguente:The output shows each tool's version and command, similar to the following example:</span><span class="sxs-lookup"><span data-stu-id="0146e-174">The output shows each tool's version and command, similar to the following example:</span></span>

```console
Package Id      Version      Commands       Manifest
-------------------------------------------------------------------------------------------
botsay          1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
```

<span data-ttu-id="0146e-175">Come illustrato in questo esempio, l'elenco mostra gli strumenti locali.</span><span class="sxs-lookup"><span data-stu-id="0146e-175">As shown in this example, the list shows local tools.</span></span> <span data-ttu-id="0146e-176">Per visualizzare gli strumenti `--global` globali, utilizzare l'opzione e `--tool-path` per visualizzare gli strumenti del percorso degli strumenti, utilizzare l'opzione .</span><span class="sxs-lookup"><span data-stu-id="0146e-176">To see global tools, use the `--global` option, and to see tool-path tools, use the `--tool-path` option.</span></span>

### <a name="invoke-a-global-tool"></a><span data-ttu-id="0146e-177">Richiamare uno strumento globaleInvoke a global tool</span><span class="sxs-lookup"><span data-stu-id="0146e-177">Invoke a global tool</span></span>

<span data-ttu-id="0146e-178">Per gli strumenti globali, utilizzare il comando strumento da solo.</span><span class="sxs-lookup"><span data-stu-id="0146e-178">For global tools, use the tool command by itself.</span></span> <span data-ttu-id="0146e-179">Ad esempio, se `dotnetsay` il `dotnet-doc`comando è o , questo è ciò che si utilizza per richiamare il comando:</span><span class="sxs-lookup"><span data-stu-id="0146e-179">For example, if the command is `dotnetsay` or `dotnet-doc`, that's what you use to invoke the command:</span></span>

```console
dotnetsay
dotnet-doc
```

<span data-ttu-id="0146e-180">Se il comando inizia `dotnet-`con il prefisso , un `dotnet` modo alternativo per richiamare lo strumento consiste nell'utilizzare il comando e omettere il prefisso del comando dello strumento.</span><span class="sxs-lookup"><span data-stu-id="0146e-180">If the command begins with the prefix `dotnet-`, an alternative way to invoke the tool is to use the `dotnet` command and omit the tool command prefix.</span></span> <span data-ttu-id="0146e-181">Ad esempio, se `dotnet-doc`il comando è , il comando seguente richiama lo strumento:</span><span class="sxs-lookup"><span data-stu-id="0146e-181">For example, if the command is `dotnet-doc`, the following command invokes the tool:</span></span>

```dotnetcli
dotnet doc
```

<span data-ttu-id="0146e-182">Tuttavia, nello scenario seguente non `dotnet` è possibile utilizzare il comando per richiamare uno strumento globale:However, in the following scenario you can't use the command to invoke a global tool:</span><span class="sxs-lookup"><span data-stu-id="0146e-182">However, in the following scenario you can't use the `dotnet` command to invoke a global tool:</span></span>

* <span data-ttu-id="0146e-183">Uno strumento globale e uno locale hanno `dotnet-`lo stesso comando preceduto da .</span><span class="sxs-lookup"><span data-stu-id="0146e-183">A global tool and a local tool have the same command prefixed by `dotnet-`.</span></span>
* <span data-ttu-id="0146e-184">Si desidera richiamare lo strumento globale da una directory compresa nell'ambito dello strumento locale.</span><span class="sxs-lookup"><span data-stu-id="0146e-184">You want to invoke the global tool from a directory that is in scope for the local tool.</span></span>

<span data-ttu-id="0146e-185">In questo `dotnet doc` scenario `dotnet dotnet-doc` e richiamare lo strumento locale.</span><span class="sxs-lookup"><span data-stu-id="0146e-185">In this scenario, `dotnet doc` and `dotnet dotnet-doc` invoke the local tool.</span></span> <span data-ttu-id="0146e-186">Per richiamare lo strumento globale, utilizzare il comando da solo:</span><span class="sxs-lookup"><span data-stu-id="0146e-186">To invoke the global tool, use the command by itself:</span></span>

```dotnetcli
dotnet-doc
```

### <a name="invoke-a-tool-path-tool"></a><span data-ttu-id="0146e-187">Richiamare uno strumento del percorso degli strumenti</span><span class="sxs-lookup"><span data-stu-id="0146e-187">Invoke a tool-path tool</span></span>

<span data-ttu-id="0146e-188">Per richiamare uno strumento globale `tool-path` installato utilizzando l'opzione , assicurarsi che il comando sia disponibile, come spiegato [in precedenza in questo articolo.](#install-a-global-tool-in-a-custom-location)</span><span class="sxs-lookup"><span data-stu-id="0146e-188">To invoke a global tool that is installed by using the `tool-path` option, make sure the command is available, as explained [earlier in this article](#install-a-global-tool-in-a-custom-location).</span></span>

### <a name="invoke-a-local-tool"></a><span data-ttu-id="0146e-189">Richiamare uno strumento localeInvoke a local tool</span><span class="sxs-lookup"><span data-stu-id="0146e-189">Invoke a local tool</span></span>

<span data-ttu-id="0146e-190">Per richiamare uno strumento locale, `dotnet` è necessario utilizzare il comando all'interno della directory di installazione.</span><span class="sxs-lookup"><span data-stu-id="0146e-190">To invoke a local tool, you have to use the `dotnet` command from within the installation directory.</span></span> <span data-ttu-id="0146e-191">È possibile utilizzare il`dotnet tool run <COMMAND_NAME>`formato lungo (`dotnet <COMMAND_NAME>`) o il formato breve ( ), come illustrato negli esempi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0146e-191">You can use the long form (`dotnet tool run <COMMAND_NAME>`) or the short form (`dotnet <COMMAND_NAME>`), as shown in the following examples:</span></span>

```dotnetcli
dotnet tool run dotnetsay
dotnet dotnetsay
```

<span data-ttu-id="0146e-192">Se il comando è `dotnet-`preceduto da , è possibile includere o omettere il prefisso quando si richiama lo strumento.</span><span class="sxs-lookup"><span data-stu-id="0146e-192">If the command is prefixed by `dotnet-`, you can include or omit the prefix when you invoke the tool.</span></span> <span data-ttu-id="0146e-193">Ad esempio, se `dotnet-doc`il comando è , uno degli esempi seguenti richiama lo strumento locale:</span><span class="sxs-lookup"><span data-stu-id="0146e-193">For example, if the command is `dotnet-doc`, any of the following examples invokes the local tool:</span></span>

```dotnetcli
dotnet tool run dotnet-doc
dotnet dotnet-doc
dotnet doc
```

## <a name="update-a-tool"></a><span data-ttu-id="0146e-194">Aggiornare uno strumento</span><span class="sxs-lookup"><span data-stu-id="0146e-194">Update a tool</span></span>

<span data-ttu-id="0146e-195">L'aggiornamento di uno strumento comporta la disinstallazione e la reinstallazione con l'ultima versione stabile.</span><span class="sxs-lookup"><span data-stu-id="0146e-195">Updating a tool involves uninstalling and reinstalling it with the latest stable version.</span></span> <span data-ttu-id="0146e-196">Per aggiornare uno strumento, utilizzare il comando [dotnet tool update](dotnet-tool-update.md) con la stessa opzione utilizzata per installare lo strumento:</span><span class="sxs-lookup"><span data-stu-id="0146e-196">To update a tool, use the [dotnet tool update](dotnet-tool-update.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool update --global <packagename>
dotnet tool update --tool-path <packagename>
dotnet tool update <packagename>
```

<span data-ttu-id="0146e-197">Per uno strumento locale, l'SDK trova il primo file manifesto che contiene l'ID del pacchetto cercando nella directory corrente e nelle directory padre.</span><span class="sxs-lookup"><span data-stu-id="0146e-197">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span> <span data-ttu-id="0146e-198">Se tale ID pacchetto non è presente in alcun file manifesto, l'SDK aggiunge una nuova voce al file manifesto più vicino.</span><span class="sxs-lookup"><span data-stu-id="0146e-198">If there is no such package ID in any manifest file, the SDK adds a new entry to the closest manifest file.</span></span>

## <a name="uninstall-a-tool"></a><span data-ttu-id="0146e-199">Disinstallare uno strumento</span><span class="sxs-lookup"><span data-stu-id="0146e-199">Uninstall a tool</span></span>

<span data-ttu-id="0146e-200">Rimuovere uno strumento utilizzando il comando [dotnet tool uninstall](dotnet-tool-uninstall.md) con la stessa opzione utilizzata per installare lo strumento:</span><span class="sxs-lookup"><span data-stu-id="0146e-200">Remove a tool by using the [dotnet tool uninstall](dotnet-tool-uninstall.md) command with the same option that you used to install the tool:</span></span>

```dotnetcli
dotnet tool uninstall --global <packagename>
dotnet tool uninstall --tool-path<packagename>
dotnet tool uninstall <packagename>
```

<span data-ttu-id="0146e-201">Per uno strumento locale, l'SDK trova il primo file manifesto che contiene l'ID del pacchetto cercando nella directory corrente e nelle directory padre.</span><span class="sxs-lookup"><span data-stu-id="0146e-201">For a local tool, the SDK finds the first manifest file that contains the package ID by looking in the current directory and parent directories.</span></span>

## <a name="get-help-and-troubleshoot"></a><span data-ttu-id="0146e-202">Ottenere assistenza e risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="0146e-202">Get help and troubleshoot</span></span>

<span data-ttu-id="0146e-203">Per ottenere un `dotnet tool` elenco dei comandi disponibili, immettere il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="0146e-203">To get a list of available `dotnet tool` commands, enter the following command:</span></span>

```dotnetcli
dotnet tool --help
```

<span data-ttu-id="0146e-204">Per ottenere istruzioni sull'utilizzo dello strumento, immettere uno dei comandi seguenti o visualizzare il sito Web dello strumento:</span><span class="sxs-lookup"><span data-stu-id="0146e-204">To get tool usage instructions, enter one of the following commands or see the tool's website:</span></span>

```dotnetcli
<command> --help
dotnet <command> --help
```

<span data-ttu-id="0146e-205">Se l'installazione o l'esecuzione di uno strumento non riesce, vedere Risolvere i problemi di [utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0146e-205">If a tool fails to install or run, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0146e-206">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0146e-206">See also</span></span>

- [<span data-ttu-id="0146e-207">Esercitazione: Creare uno strumento .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Create a .NET Core tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="0146e-207">Tutorial: Create a .NET Core tool using the .NET Core CLI</span></span>](global-tools-how-to-create.md)
- [<span data-ttu-id="0146e-208">Esercitazione: Installare e usare uno strumento globale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core global tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="0146e-208">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="0146e-209">Esercitazione: Installare e usare uno strumento locale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core local tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="0146e-209">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
