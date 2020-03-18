---
title: 'Esercitazione: Installare e usare uno strumento globale .NET CoreTutorial: Install and use a .NET Core global tool'
description: Informazioni su come installare e usare uno strumento .NET come strumento globale.
ms.date: 02/12/2020
ms.openlocfilehash: 9f8378e50fd2544eedbbaaeffb89d67800ec6880
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156738"
---
# <a name="tutorial-install-and-use-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="d6926-103">Esercitazione: Installare e usare uno strumento globale .NET Core usando l'interfaccia della riga di comando di .NET CoreTutorial: Install and use a .NET Core global tool using the .NET Core CLI</span><span class="sxs-lookup"><span data-stu-id="d6926-103">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>

<span data-ttu-id="d6926-104">**Questo articolo si applica a:** ✔️ .NET Core 2.1 SDK e versioni successive</span><span class="sxs-lookup"><span data-stu-id="d6926-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="d6926-105">Questo tutorial ti insegna come installare e utilizzare uno strumento globale.</span><span class="sxs-lookup"><span data-stu-id="d6926-105">This tutorial teaches you how to install and use a global tool.</span></span> <span data-ttu-id="d6926-106">Si utilizza uno strumento creato nella [prima esercitazione di questa serie.](global-tools-how-to-create.md)</span><span class="sxs-lookup"><span data-stu-id="d6926-106">You use a tool that you create in the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6926-107">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="d6926-107">Prerequisites</span></span>

* <span data-ttu-id="d6926-108">Completare la [prima esercitazione di questa serie.](global-tools-how-to-create.md)</span><span class="sxs-lookup"><span data-stu-id="d6926-108">Complete the [first tutorial of this series](global-tools-how-to-create.md).</span></span>

## <a name="use-the-tool-as-a-global-tool"></a><span data-ttu-id="d6926-109">Utilizzare lo strumento come strumento globale</span><span class="sxs-lookup"><span data-stu-id="d6926-109">Use the tool as a global tool</span></span>

1. <span data-ttu-id="d6926-110">Installare lo strumento dal pacchetto eseguendo il comando [dotnet tool install](dotnet-tool-install.md) nella cartella del progetto *microsoft.botsay:*</span><span class="sxs-lookup"><span data-stu-id="d6926-110">Install the tool from the package by running the [dotnet tool install](dotnet-tool-install.md) command in the *microsoft.botsay* project folder:</span></span>

   ```dotnetcli
   dotnet tool install --global --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="d6926-111">Il `--global` parametro indica all'interfaccia della riga di comando di .NET Core per installare i file binari dello strumento in un percorso predefinito che viene aggiunto automaticamente alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="d6926-111">The `--global` parameter tells the .NET Core CLI to install the tool binaries in a default location that is automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="d6926-112">Il `--add-source` parametro indica all'interfaccia della riga di comando di .NET Core di utilizzare temporaneamente la directory *./nupkg* come feed di origine aggiuntivo per i pacchetti NuGet.</span><span class="sxs-lookup"><span data-stu-id="d6926-112">The `--add-source` parameter tells the .NET Core CLI to temporarily use the *./nupkg* directory as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="d6926-113">Hai fornito al tuo pacchetto un nome univoco per assicurarti che si trovi solo nella directory *./nupkg,* non nella Nuget.org sito.</span><span class="sxs-lookup"><span data-stu-id="d6926-113">You gave your package a unique name to make sure that it will only be found in the *./nupkg* directory, not on the Nuget.org site.</span></span>

   <span data-ttu-id="d6926-114">L'output mostra il comando utilizzato per chiamare lo strumento e la versione installata:</span><span class="sxs-lookup"><span data-stu-id="d6926-114">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="d6926-115">Richiamare lo strumento:</span><span class="sxs-lookup"><span data-stu-id="d6926-115">Invoke the tool:</span></span>

   ```console
   botsay hello from the bot
   ```

   > [!NOTE]
   > <span data-ttu-id="d6926-116">Se questo comando non riesce, potrebbe essere necessario aprire un nuovo terminale per aggiornare il percorso.</span><span class="sxs-lookup"><span data-stu-id="d6926-116">If this command fails, you may need to open a new terminal to refresh the PATH.</span></span>

1. <span data-ttu-id="d6926-117">Rimuovere lo strumento eseguendo il comando [dotnet tool uninstall:](dotnet-tool-uninstall.md)</span><span class="sxs-lookup"><span data-stu-id="d6926-117">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   ```dotnetcli
   dotnet tool uninstall -g microsoft.botsay
   ```

## <a name="use-the-tool-as-a-global-tool-installed-in-a-custom-location"></a><span data-ttu-id="d6926-118">Utilizzare lo strumento come strumento globale installato in una posizione personalizzata</span><span class="sxs-lookup"><span data-stu-id="d6926-118">Use the tool as a global tool installed in a custom location</span></span>

1. <span data-ttu-id="d6926-119">Installare lo strumento dal pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d6926-119">Install the tool from the package.</span></span>

   <span data-ttu-id="d6926-120">In Windows:</span><span class="sxs-lookup"><span data-stu-id="d6926-120">On Windows:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path c:\dotnet-tools --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="d6926-121">Su Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="d6926-121">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool install --tool-path ~/bin --add-source ./nupkg microsoft.botsay
   ```

   <span data-ttu-id="d6926-122">Il `--tool-path` parametro indica all'interfaccia della riga di comando di .NET Core per installare i file binari dello strumento nel percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="d6926-122">The `--tool-path` parameter tells the .NET Core CLI to install the tool binaries in the specified location.</span></span> <span data-ttu-id="d6926-123">Se la directory non esiste, viene creata.</span><span class="sxs-lookup"><span data-stu-id="d6926-123">If the directory doesn't exist, it is created.</span></span> <span data-ttu-id="d6926-124">Questa directory non viene aggiunta automaticamente alla variabile di ambiente PATH.</span><span class="sxs-lookup"><span data-stu-id="d6926-124">This directory is not automatically added to the PATH environment variable.</span></span>

   <span data-ttu-id="d6926-125">L'output mostra il comando utilizzato per chiamare lo strumento e la versione installata:</span><span class="sxs-lookup"><span data-stu-id="d6926-125">The output shows the command used to call the tool and the version installed:</span></span>

   ```console
   You can invoke the tool using the following command: botsay
   Tool 'microsoft.botsay' (version '1.0.0') was successfully installed.
   ```

1. <span data-ttu-id="d6926-126">Richiamare lo strumento:</span><span class="sxs-lookup"><span data-stu-id="d6926-126">Invoke the tool:</span></span>

   <span data-ttu-id="d6926-127">In Windows:</span><span class="sxs-lookup"><span data-stu-id="d6926-127">On Windows:</span></span>

   ```console
   c:\dotnet-tools\botsay hello from the bot
   ```

   <span data-ttu-id="d6926-128">Su Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="d6926-128">On Linux or macOS:</span></span>

   ```console
   ~/bin/botsay hello from the bot
   ```

1. <span data-ttu-id="d6926-129">Rimuovere lo strumento eseguendo il comando [dotnet tool uninstall:](dotnet-tool-uninstall.md)</span><span class="sxs-lookup"><span data-stu-id="d6926-129">Remove the tool by running the [dotnet tool uninstall](dotnet-tool-uninstall.md) command:</span></span>

   <span data-ttu-id="d6926-130">In Windows:</span><span class="sxs-lookup"><span data-stu-id="d6926-130">On Windows:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path c:\dotnet-tools microsoft.botsay
   ```

   <span data-ttu-id="d6926-131">Su Linux o macOS:</span><span class="sxs-lookup"><span data-stu-id="d6926-131">On Linux or macOS:</span></span>

   ```dotnetcli
   dotnet tool uninstall --tool-path ~/bin microsoft.botsay
   ```

## <a name="troubleshoot"></a><span data-ttu-id="d6926-132">Risolvere problemi</span><span class="sxs-lookup"><span data-stu-id="d6926-132">Troubleshoot</span></span>

<span data-ttu-id="d6926-133">Se viene visualizzato un messaggio di errore durante l'esercitazione, vedere Risolvere i problemi di [utilizzo degli strumenti .NET Core](troubleshoot-usage-issues.md).</span><span class="sxs-lookup"><span data-stu-id="d6926-133">If you get an error message while following the tutorial, see [Troubleshoot .NET Core tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d6926-134">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d6926-134">Next steps</span></span>

<span data-ttu-id="d6926-135">In questa esercitazione è stato installato e usato uno strumento come strumento globale.</span><span class="sxs-lookup"><span data-stu-id="d6926-135">In this tutorial, you installed and used a tool as a global tool.</span></span> <span data-ttu-id="d6926-136">Per installare e utilizzare lo stesso strumento di uno strumento locale, passare all'esercitazione successiva.</span><span class="sxs-lookup"><span data-stu-id="d6926-136">To install and use the same tool as a local tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d6926-137">Installare e utilizzare strumenti locali</span><span class="sxs-lookup"><span data-stu-id="d6926-137">Install and use local tools</span></span>](local-tools-how-to-use.md)
