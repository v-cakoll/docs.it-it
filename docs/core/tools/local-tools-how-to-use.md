---
title: 'Esercitazione: installare e usare gli strumenti locali di .NET Core'
description: Informazioni su come installare e usare uno strumento .NET come strumento locale.
ms.date: 02/12/2020
ms.openlocfilehash: 6de620772cec1e9d1b1f57380b72c0163d68337c
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543866"
---
# <a name="tutorial-install-and-use-a-net-core-local-tool-using-the-net-core-cli"></a><span data-ttu-id="2cf03-103">Esercitazione: installare e usare uno strumento locale di .NET Core usando il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="2cf03-103">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>

<span data-ttu-id="2cf03-104">**Questo articolo si applica a:** ✔️ .net core 3,0 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="2cf03-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="2cf03-105">Questa esercitazione illustra come installare e usare uno strumento locale.</span><span class="sxs-lookup"><span data-stu-id="2cf03-105">This tutorial teaches you how to install and use a local tool.</span></span> <span data-ttu-id="2cf03-106">Usare uno strumento creato nella [prima esercitazione di questa serie](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="2cf03-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2cf03-107">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="2cf03-107">Prerequisites</span></span>

* <span data-ttu-id="2cf03-108">Completare la [prima esercitazione di questa serie](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="2cf03-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>
* <span data-ttu-id="2cf03-109">Installare il runtime di .NET Core 2,1.</span><span class="sxs-lookup"><span data-stu-id="2cf03-109">Install the .NET Core 2.1 runtime.</span></span>

  <span data-ttu-id="2cf03-110">Per questa esercitazione si installa e si usa uno strumento destinato a .NET Core 2,1, quindi è necessario che il Runtime sia installato nel computer.</span><span class="sxs-lookup"><span data-stu-id="2cf03-110">For this tutorial you install and use a tool that targets .NET Core 2.1, so you need to have that runtime installed on your machine.</span></span> <span data-ttu-id="2cf03-111">Per installare il runtime di 2,1, passare alla [pagina di download di .NET Core 2,1](https://dotnet.microsoft.com/download/dotnet-core/2.1) e trovare il collegamento di installazione di runtime nella colonna **Run Apps-Runtime** .</span><span class="sxs-lookup"><span data-stu-id="2cf03-111">To install the 2.1 runtime, go to the [.NET Core 2.1 download page](https://dotnet.microsoft.com/download/dotnet-core/2.1) and find the runtime installation link in the **Run apps - Runtime** column.</span></span>

## <a name="create-a-manifest-file"></a><span data-ttu-id="2cf03-112">Creazione di un file manifesto</span><span class="sxs-lookup"><span data-stu-id="2cf03-112">Create a manifest file</span></span>

<span data-ttu-id="2cf03-113">Per installare uno strumento solo per l'accesso locale (per la directory e le sottodirectory correnti), è necessario aggiungerlo a un file manifesto.</span><span class="sxs-lookup"><span data-stu-id="2cf03-113">To install a tool for local access only (for the current directory and subdirectories), it has to be added to a manifest file.</span></span> 

<span data-ttu-id="2cf03-114">Dalla cartella *botsay-\<nome >* , passare a un livello superiore nella cartella del *repository* :</span><span class="sxs-lookup"><span data-stu-id="2cf03-114">From the *botsay-\<name>* folder, navigate up one level to the *repository* folder:</span></span>

```console
cd ..
```

<span data-ttu-id="2cf03-115">Creare un file manifesto eseguendo il comando [DotNet New](dotnet-new.md) :</span><span class="sxs-lookup"><span data-stu-id="2cf03-115">Create a manifest file by running the [dotnet new](dotnet-new.md) command:</span></span>

```dotnetcli
dotnet new tool-manifest
```

<span data-ttu-id="2cf03-116">L'output indica che la creazione del file è riuscita.</span><span class="sxs-lookup"><span data-stu-id="2cf03-116">The output indicates successful creation of the file.</span></span>

```console
The template "Dotnet local tool manifest file" was created successfully.
```

<span data-ttu-id="2cf03-117">Il file *. config/DotNet-Tools. JSON* non contiene ancora strumenti:</span><span class="sxs-lookup"><span data-stu-id="2cf03-117">The *.config/dotnet-tools.json* file has no tools in it yet:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {}
}
```

<span data-ttu-id="2cf03-118">Gli strumenti elencati in un file manifesto sono disponibili per la directory e le sottodirectory correnti.</span><span class="sxs-lookup"><span data-stu-id="2cf03-118">The tools listed in a manifest file are available to the current directory and subdirectories.</span></span> <span data-ttu-id="2cf03-119">La directory corrente è quella che contiene la directory *. config* con il file manifesto.</span><span class="sxs-lookup"><span data-stu-id="2cf03-119">The current directory is the one that contains the *.config* directory with the manifest file.</span></span>

<span data-ttu-id="2cf03-120">Quando si usa un comando CLI che fa riferimento a uno strumento locale, l'SDK Cerca un file manifesto nella directory corrente e nelle directory padre.</span><span class="sxs-lookup"><span data-stu-id="2cf03-120">When you use a CLI command that refers to a local tool, the SDK searches for a manifest file in the current directory and parent directories.</span></span> <span data-ttu-id="2cf03-121">Se trova un file manifesto, ma il file non include lo strumento a cui si fa riferimento, continua la ricerca nelle directory padre.</span><span class="sxs-lookup"><span data-stu-id="2cf03-121">If it finds a manifest file, but the file doesn't include the referenced tool, it continues the search up through parent directories.</span></span> <span data-ttu-id="2cf03-122">La ricerca termina quando trova lo strumento a cui si fa riferimento o trova un file manifesto con `isRoot` impostato su `true`.</span><span class="sxs-lookup"><span data-stu-id="2cf03-122">The search ends when it finds the referenced tool or it finds a manifest file with `isRoot` set to `true`.</span></span>

## <a name="install-botsay-as-a-local-tool"></a><span data-ttu-id="2cf03-123">Installare botsay come strumento locale</span><span class="sxs-lookup"><span data-stu-id="2cf03-123">Install botsay as a local tool</span></span>

<span data-ttu-id="2cf03-124">Installare lo strumento dal pacchetto creato nella prima esercitazione:</span><span class="sxs-lookup"><span data-stu-id="2cf03-124">Install the tool from the package that you created in the first tutorial:</span></span>

```dotnetcli
dotnet tool install --add-source ./botsay-<name>/nupkg botsay-<name>
```

<span data-ttu-id="2cf03-125">Questo comando aggiunge lo strumento al file manifesto creato nel passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="2cf03-125">This command adds the tool to the manifest file that you created in the preceding step.</span></span> <span data-ttu-id="2cf03-126">L'output del comando Mostra il file manifesto in cui si trova lo strumento appena installato:</span><span class="sxs-lookup"><span data-stu-id="2cf03-126">The command output shows which manifest file the newly installed tool is in:</span></span>

 ```console
 You can invoke the tool from this directory using the following command:
 'dotnet tool run botsay' or 'dotnet botsay'
 Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
 Entry is added to the manifest file /home/name/repository/.config/dotnet-tools.json
 ```

<span data-ttu-id="2cf03-127">Il file *. config/DotNet-Tools. JSON* dispone ora di uno strumento:</span><span class="sxs-lookup"><span data-stu-id="2cf03-127">The *.config/dotnet-tools.json* file now has one tool:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "botsay-<name>": {
      "version": "1.0.0",
      "commands": [
        "botsay"
      ]
    }
  }
}
```

## <a name="use-the-tool"></a><span data-ttu-id="2cf03-128">Usare lo strumento</span><span class="sxs-lookup"><span data-stu-id="2cf03-128">Use the tool</span></span>

<span data-ttu-id="2cf03-129">Richiamare lo strumento eseguendo il comando `dotnet tool run` dalla cartella *repository* :</span><span class="sxs-lookup"><span data-stu-id="2cf03-129">Invoke the tool by running the `dotnet tool run` command from the *repository* folder:</span></span>

```dotnetcli
dotnet tool run botsay hello from the bot
```

## <a name="restore-a-local-tool-installed-by-others"></a><span data-ttu-id="2cf03-130">Ripristinare uno strumento locale installato da altri utenti</span><span class="sxs-lookup"><span data-stu-id="2cf03-130">Restore a local tool installed by others</span></span>

<span data-ttu-id="2cf03-131">Viene in genere installato uno strumento locale nella directory radice del repository.</span><span class="sxs-lookup"><span data-stu-id="2cf03-131">You typically install a local tool in the root directory of the repository.</span></span> <span data-ttu-id="2cf03-132">Dopo l'archiviazione del file manifesto nel repository, altri sviluppatori possono ottenere il file manifesto più recente.</span><span class="sxs-lookup"><span data-stu-id="2cf03-132">After you check in the manifest file to the repository, other developers can get the latest manifest file.</span></span> <span data-ttu-id="2cf03-133">Per installare tutti gli strumenti elencati nel file manifesto, è possibile eseguire un singolo comando `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="2cf03-133">To install all of the tools listed in the manifest file, they can run a single `dotnet tool restore` command.</span></span>

1. <span data-ttu-id="2cf03-134">Aprire il file *config/DotNet-Tools. JSON* e sostituire il contenuto con il codice JSON seguente:</span><span class="sxs-lookup"><span data-stu-id="2cf03-134">Open the *.config/dotnet-tools.json* file, and replace the contents with the following JSON:</span></span>

   ```json
   {
     "version": 1,
     "isRoot": true,
     "tools": {
       "botsay-<name>": {
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

1. <span data-ttu-id="2cf03-135">Sostituire `<name>` con il nome usato per creare il progetto.</span><span class="sxs-lookup"><span data-stu-id="2cf03-135">Replace `<name>` with the name you used to create the project.</span></span>

1. <span data-ttu-id="2cf03-136">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="2cf03-136">Save your changes.</span></span>

   <span data-ttu-id="2cf03-137">Per apportare questa modifica, è possibile ottenere la versione più recente dal repository dopo che un altro utente ha installato il pacchetto `dotnetsay` per la directory del progetto.</span><span class="sxs-lookup"><span data-stu-id="2cf03-137">Making this change is the same as getting the latest version from the repository after someone else installed the package `dotnetsay` for the project directory.</span></span> 

1. <span data-ttu-id="2cf03-138">Eseguire il comando `dotnet tool restore`.</span><span class="sxs-lookup"><span data-stu-id="2cf03-138">Run the `dotnet tool restore` command.</span></span>

   ```dotnetcli
   dotnet tool restore
   ```

   <span data-ttu-id="2cf03-139">Il comando genera un output simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2cf03-139">The command produces output like the following example:</span></span>

   ```console
   Tool 'botsay-<name>' (version '1.0.0') was restored. Available commands: botsay
   Tool 'dotnetsay' (version '2.1.3') was restored. Available commands: dotnetsay
   Restore was successful.
   ```

1. <span data-ttu-id="2cf03-140">Verificare che gli strumenti siano disponibili:</span><span class="sxs-lookup"><span data-stu-id="2cf03-140">Verify that the tools are available:</span></span>

   ```dotnetcli
   dotnet tool list
   ```

   <span data-ttu-id="2cf03-141">L'output è un elenco di pacchetti e comandi, in modo simile all'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="2cf03-141">The output is a list of packages and commands, similar to the following example:</span></span>

   ```console
   Package Id      Version      Commands       Manifest
   -------------------------------------------------------------------------------------------
   botsay-<name>   1.0.0        botsay         /home/name/repository/.config/dotnet-tools.json
   dotnetsay       2.1.3        dotnetsay      /home/name/repository/.config/dotnet-tools.json
   ```

1. <span data-ttu-id="2cf03-142">Testare gli strumenti:</span><span class="sxs-lookup"><span data-stu-id="2cf03-142">Test the tools:</span></span>

   ```dotnetcli
   dotnet tool run dotnetsay hello from dotnetsay
   dotnet tool run botsay hello from botsay
   ```

## <a name="update-a-local-tool"></a><span data-ttu-id="2cf03-143">Aggiornare uno strumento locale</span><span class="sxs-lookup"><span data-stu-id="2cf03-143">Update a local tool</span></span>

<span data-ttu-id="2cf03-144">La versione installata dello strumento locale `dotnetsay` è 2.1.3.</span><span class="sxs-lookup"><span data-stu-id="2cf03-144">The installed version of local tool `dotnetsay` is 2.1.3.</span></span>  <span data-ttu-id="2cf03-145">La versione più recente è 2.1.4.</span><span class="sxs-lookup"><span data-stu-id="2cf03-145">The latest version is 2.1.4.</span></span> <span data-ttu-id="2cf03-146">Usare il comando [DotNet Tool Update](dotnet-tool-update.md) per aggiornare lo strumento alla versione più recente.</span><span class="sxs-lookup"><span data-stu-id="2cf03-146">Use the [dotnet tool update](dotnet-tool-update.md) command to update the tool to the latest version.</span></span>

```dotnetcli
dotnet tool update dotnetsay
```

<span data-ttu-id="2cf03-147">L'output indica il nuovo numero di versione:</span><span class="sxs-lookup"><span data-stu-id="2cf03-147">The output indicates the new version number:</span></span>

```console
Tool 'dotnetsay' was successfully updated from version '2.1.3' to version '2.1.4'
(manifest file /home/name/repository/.config/dotnet-tools.json).
```

<span data-ttu-id="2cf03-148">Il comando Update trova il primo file manifesto che contiene l'ID del pacchetto e lo aggiorna.</span><span class="sxs-lookup"><span data-stu-id="2cf03-148">The update command finds the first manifest file that contains the package ID and updates it.</span></span> <span data-ttu-id="2cf03-149">Se non è presente alcun ID pacchetto in un file manifesto nell'ambito della ricerca, l'SDK aggiunge una nuova voce al file manifesto più vicino.</span><span class="sxs-lookup"><span data-stu-id="2cf03-149">If there is no such package ID in any manifest file that is in the scope of the search, the SDK adds a new entry to the closest manifest file.</span></span> <span data-ttu-id="2cf03-150">L'ambito di ricerca è attivo attraverso le directory padre fino a quando non viene trovato un file manifesto con `isRoot = true`.</span><span class="sxs-lookup"><span data-stu-id="2cf03-150">The search scope is up through parent directories until a manifest file with `isRoot = true` is found.</span></span>

## <a name="remove-local-tools"></a><span data-ttu-id="2cf03-151">Rimuovi strumenti locali</span><span class="sxs-lookup"><span data-stu-id="2cf03-151">Remove local tools</span></span>

<span data-ttu-id="2cf03-152">Rimuovere gli strumenti installati eseguendo il comando [DotNet Tool uninstall](dotnet-tool-uninstall.md) :</span><span class="sxs-lookup"><span data-stu-id="2cf03-152">Remove the installed tools by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

```dotnetcli
dotnet tool uninstall botsay-<name>
```

```dotnetcli
dotnet tool uninstall dotnetsay
```

## <a name="troubleshoot"></a><span data-ttu-id="2cf03-153">Risolvere problemi</span><span class="sxs-lookup"><span data-stu-id="2cf03-153">Troubleshoot</span></span>

<span data-ttu-id="2cf03-154">Se viene visualizzato un messaggio di errore mentre si segue l'esercitazione, vedere [risolvere i problemi di utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="2cf03-154">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2cf03-155">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cf03-155">See also</span></span>

<span data-ttu-id="2cf03-156">Per altre informazioni, vedere [strumenti di .NET Core](global-tools.md)</span><span class="sxs-lookup"><span data-stu-id="2cf03-156">For more information, see [.NET Core tools](global-tools.md)</span></span>
