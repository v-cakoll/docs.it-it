---
title: 'Esercitazione: installare e usare uno strumento globale di .NET Core'
description: Informazioni su come installare e usare uno strumento .NET come strumento globale.
ms.date: 02/12/2020
ms.openlocfilehash: 65047af9d8a7f2fd4c1a07f65af3a6ddbf870c5d
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543873"
---
# <a name="tutorial-install-and-use-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="0ff78-103">Esercitazione: installare e usare uno strumento globale .NET Core usando il interfaccia della riga di comando di .NET Core</span><span class="sxs-lookup"><span data-stu-id="0ff78-103">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>

<span data-ttu-id="0ff78-104">**Questo articolo si applica a:** ✔️ .net core 2,1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="0ff78-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="0ff78-105">Questa esercitazione illustra come installare e usare uno strumento globale.</span><span class="sxs-lookup"><span data-stu-id="0ff78-105">This tutorial teaches you how to install and use a global tool.</span></span> <span data-ttu-id="0ff78-106">Usare uno strumento creato nella [prima esercitazione di questa serie](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="0ff78-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0ff78-107">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="0ff78-107">Prerequisites</span></span>

* <span data-ttu-id="0ff78-108">Completare la [prima esercitazione di questa serie](global-tools-how-to-create.md).</span><span class="sxs-lookup"><span data-stu-id="0ff78-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="use-the-tool-as-a-global-tool"></a><span data-ttu-id="0ff78-109">Usare lo strumento come strumento globale</span><span class="sxs-lookup"><span data-stu-id="0ff78-109">Use the tool as a global tool</span></span>

1. <span data-ttu-id="0ff78-110">Installare lo strumento dal pacchetto eseguendo il comando [DotNet tool install](dotnet-tool-install.md) nella cartella *botsay-\<Name >* Project:</span><span class="sxs-lookup"><span data-stu-id="0ff78-110">Install the tool from the package by running the [dotnet tool install](dotnet-tool-install.md) command in the *botsay-\<name>* project folder:</span></span>

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg botsay-<name>
   ```

   <span data-ttu-id="0ff78-111">Il parametro `--global` indica al interfaccia della riga di comando di .NET Core di installare i file binari dello strumento in un percorso predefinito aggiunto automaticamente alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="0ff78-111">The `--global` parameter tells the .NET Core CLI to install the tool binaries in a default location that is automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="0ff78-112">Il parametro `--add-source` indica al interfaccia della riga di comando di .NET Core di usare temporaneamente la directory *./nupkg* come feed di origine aggiuntivo per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="0ff78-112">The `--add-source` parameter tells the .NET Core CLI to temporarily use the *./nupkg* directory as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="0ff78-113">È stato assegnato un nome univoco al pacchetto per assicurarsi che venga trovato solo nella directory *./nupkg* , non nel sito NuGet.org.</span><span class="sxs-lookup"><span data-stu-id="0ff78-113">You gave your package a unique name to make sure that it will only be found in the *./nupkg* directory, not on the Nuget.org site.</span></span> 

   <span data-ttu-id="0ff78-114">L'output Mostra il comando utilizzato per chiamare lo strumento e la versione installata:</span><span class="sxs-lookup"><span data-stu-id="0ff78-114">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="0ff78-115">Richiamare lo strumento:</span><span class="sxs-lookup"><span data-stu-id="0ff78-115">Invoke the tool:</span></span>

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > <span data-ttu-id="0ff78-116">Se questo comando non riesce, potrebbe essere necessario aprire un nuovo terminale per aggiornare il percorso.</span><span class="sxs-lookup"><span data-stu-id="0ff78-116">If this command fails, you may need to open a new terminal to refresh the PATH.</span></span>

1. <span data-ttu-id="0ff78-117">Rimuovere lo strumento eseguendo il comando [DotNet Tool uninstall](dotnet-tool-uninstall.md) :</span><span class="sxs-lookup"><span data-stu-id="0ff78-117">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   ```dotnetcli
   dotnet tool uninstall -g botsay-<name>
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a><span data-ttu-id="0ff78-118">Usare lo strumento come strumento globale installato in un percorso personalizzato</span><span class="sxs-lookup"><span data-stu-id="0ff78-118">Use the tool as a global tool installed in a custom location</span></span>

1. <span data-ttu-id="0ff78-119">Installare lo strumento dal pacchetto.</span><span class="sxs-lookup"><span data-stu-id="0ff78-119">Install the tool from the package.</span></span>

   <span data-ttu-id="0ff78-120">In Windows:</span><span class="sxs-lookup"><span data-stu-id="0ff78-120">On Windows:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg botsay-<name>
   ```

   <span data-ttu-id="0ff78-121">In Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="0ff78-121">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg botsay-<name>
   ```

   <span data-ttu-id="0ff78-122">Il parametro `--tool-path` indica al interfaccia della riga di comando di .NET Core di installare i file binari degli strumenti nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="0ff78-122">The `--tool-path` parameter tells the .NET Core CLI to install the tool binaries in the specified location.</span></span> <span data-ttu-id="0ff78-123">Se la directory non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="0ff78-123">If the directory doesn't exist, it is created.</span></span> <span data-ttu-id="0ff78-124">Questa directory non viene aggiunta automaticamente alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="0ff78-124">This directory is not automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="0ff78-125">L'output Mostra il comando utilizzato per chiamare lo strumento e la versione installata:</span><span class="sxs-lookup"><span data-stu-id="0ff78-125">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'botsay-<name>' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="0ff78-126">Richiamare lo strumento:</span><span class="sxs-lookup"><span data-stu-id="0ff78-126">Invoke the tool:</span></span>

   <span data-ttu-id="0ff78-127">In Windows:</span><span class="sxs-lookup"><span data-stu-id="0ff78-127">On Windows:</span></span>

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   <span data-ttu-id="0ff78-128">In Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="0ff78-128">On Linux or macOS:</span></span>

   ```console
   ~/bin/botsay hello from the bot
   ```

1. <span data-ttu-id="0ff78-129">Rimuovere lo strumento eseguendo il comando [DotNet Tool uninstall](dotnet-tool-uninstall.md) :</span><span class="sxs-lookup"><span data-stu-id="0ff78-129">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   <span data-ttu-id="0ff78-130">In Windows:</span><span class="sxs-lookup"><span data-stu-id="0ff78-130">On Windows:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools botsay --add-source ./nupkg botsay-<name>
   ```

   <span data-ttu-id="0ff78-131">In Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="0ff78-131">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin botsay-<name>
   ```

## <a name="troubleshoot"></a><span data-ttu-id="0ff78-132">Risolvere problemi</span><span class="sxs-lookup"><span data-stu-id="0ff78-132">Troubleshoot</span></span>

<span data-ttu-id="0ff78-133">Se viene visualizzato un messaggio di errore mentre si segue l'esercitazione, vedere [risolvere i problemi di utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="0ff78-133">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="0ff78-134">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="0ff78-134">Next steps</span></span>

<span data-ttu-id="0ff78-135">In questa esercitazione è stato installato e utilizzato uno strumento come strumento globale.</span><span class="sxs-lookup"><span data-stu-id="0ff78-135">In this tutorial, you installed and used a tool as a global tool.</span></span> <span data-ttu-id="0ff78-136">Per installare e usare lo stesso strumento di uno strumento locale, passare all'esercitazione successiva.</span><span class="sxs-lookup"><span data-stu-id="0ff78-136">To install and use the same tool as a local tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0ff78-137">Installare e usare gli strumenti locali</span><span class="sxs-lookup"><span data-stu-id="0ff78-137">Install and use local tools</span></span>](local-tools-how-to-use.md)
