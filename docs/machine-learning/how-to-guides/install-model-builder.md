---
title: Come installare il generatore di modelli
description: Informazioni su come installare lo strumento del generatore di modelli di ML.NET
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: b0d45ab7807bf84b98c58e85580d5aa04d0c5f7d
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306319"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="1e18a-103">Come installare il generatore di modelli di ML.NET</span><span class="sxs-lookup"><span data-stu-id="1e18a-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="1e18a-104">Di seguito viene descritto come installare il generatore di modelli di ML.NET per aggiungere il Machine Learning alle applicazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="1e18a-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="1e18a-105">Il generatore di modelli è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="1e18a-105">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="1e18a-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="1e18a-106">Pre-requisites</span></span>

- <span data-ttu-id="1e18a-107">Visual Studio 2017 15.9.12 o versione successiva/Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="1e18a-107">Visual Studio 2017 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="1e18a-108">SDK .NET Core 2.1 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="1e18a-108">.NET Core 2.1 or later SDK</span></span>

## <a name="limitations"></a><span data-ttu-id="1e18a-109">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="1e18a-109">Limitations</span></span>

- <span data-ttu-id="1e18a-110">L'estensione del generatore di modelli di ML.NET attualmente funziona solo in Visual Studio in Windows.</span><span class="sxs-lookup"><span data-stu-id="1e18a-110">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="1e18a-111">Limite del set di dati di training di 1 GB</span><span class="sxs-lookup"><span data-stu-id="1e18a-111">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="1e18a-112">SQL Server ha un limite di 100 migliaia di righe per il training</span><span class="sxs-lookup"><span data-stu-id="1e18a-112">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="1e18a-113">Microsoft SQL Server Data Tools per Visual Studio 2017 non è supportato</span><span class="sxs-lookup"><span data-stu-id="1e18a-113">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="1e18a-114">Installazione</span><span class="sxs-lookup"><span data-stu-id="1e18a-114">Install</span></span>

<span data-ttu-id="1e18a-115">Il generatore di modelli di ML.NET può essere installato tramite Visual Studio Marketplace o dall'interno di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1e18a-115">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span> 

### <a name="visual-studio-marketplace"></a><span data-ttu-id="1e18a-116">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="1e18a-116">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="1e18a-117">Scaricare da [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span><span class="sxs-lookup"><span data-stu-id="1e18a-117">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="1e18a-118">Seguire i messaggi visualizzati per eseguire l'installazione nella versione di Visual Studio in uso</span><span class="sxs-lookup"><span data-stu-id="1e18a-118">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="1e18a-119">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="1e18a-119">Visual Studio 2017</span></span>

1. <span data-ttu-id="1e18a-120">Nella barra dei menu selezionare **Strumenti** > **Estensioni e aggiornamenti**</span><span class="sxs-lookup"><span data-stu-id="1e18a-120">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![Finestra di dialogo VS2017 Open Extensions Manager](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="1e18a-122">All'interno del prompt *Estensioni e aggiornamenti* selezionare il nodo *Online*.</span><span class="sxs-lookup"><span data-stu-id="1e18a-122">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="1e18a-123">Nella barra di ricerca cercare *ML.NET Model Builder* e selezionare ML.NET Model Builder (Preview) dai risultati</span><span class="sxs-lookup"><span data-stu-id="1e18a-123">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017 cercare e installare l'estensione del generatore di modelli nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="1e18a-125">Seguire i messaggi visualizzati per completare l'installazione</span><span class="sxs-lookup"><span data-stu-id="1e18a-125">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="1e18a-126">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="1e18a-126">Visual Studio 2019</span></span>

1. <span data-ttu-id="1e18a-127">Nella barra dei menu selezionare **Estensioni** > **Gestisci estensioni**</span><span class="sxs-lookup"><span data-stu-id="1e18a-127">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![Finestra di dialogo VS2019 Open Extensions Manager](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="1e18a-129">All'interno del prompt *Estensioni e aggiornamenti* selezionare il nodo *Online*.</span><span class="sxs-lookup"><span data-stu-id="1e18a-129">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="1e18a-130">Digitare *ML.NET Model Builder* nella barra di ricerca e selezionare ML.NET Model Builder (Preview)</span><span class="sxs-lookup"><span data-stu-id="1e18a-130">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019 cercare e installare l'estensione del generatore di modelli nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="1e18a-132">Seguire i messaggi visualizzati per completare l'installazione</span><span class="sxs-lookup"><span data-stu-id="1e18a-132">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="1e18a-133">Disinstallare</span><span class="sxs-lookup"><span data-stu-id="1e18a-133">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="1e18a-134">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="1e18a-134">Visual Studio 2017</span></span>

1. <span data-ttu-id="1e18a-135">Nella barra dei menu selezionare **Strumenti** > **Estensioni e aggiornamenti**</span><span class="sxs-lookup"><span data-stu-id="1e18a-135">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![Finestra di dialogo Apri Gestione estensioni di VS2017](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="1e18a-137">All'interno del prompt *Estensioni e aggiornamenti* espandere il nodo *Installati* e selezionare *Strumenti*</span><span class="sxs-lookup"><span data-stu-id="1e18a-137">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="1e18a-138">Selezionare ML.NET Model Builder (Preview) dall'elenco degli strumenti e quindi selezionare *Disinstalla*</span><span class="sxs-lookup"><span data-stu-id="1e18a-138">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017 ricerca e Disinstalla estensione del generatore di modelli nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="1e18a-140">Seguire i messaggi visualizzati per completare la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="1e18a-140">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="1e18a-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="1e18a-141">Visual Studio 2019</span></span>

1. <span data-ttu-id="1e18a-142">Nella barra dei menu selezionare **Estensioni** > **Gestisci estensioni**</span><span class="sxs-lookup"><span data-stu-id="1e18a-142">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![Finestra di dialogo Apri Gestione estensioni di VS2019](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="1e18a-144">All'interno del prompt *Estensioni e aggiornamenti* espandere il nodo *Installati* e selezionare *Strumenti*</span><span class="sxs-lookup"><span data-stu-id="1e18a-144">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="1e18a-145">Selezionare ML.NET Model Builder (Preview) dall'elenco degli strumenti e quindi selezionare *Disinstalla*</span><span class="sxs-lookup"><span data-stu-id="1e18a-145">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019 ricerca e Disinstalla estensione del generatore di modelli nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="1e18a-147">Seguire i messaggi visualizzati per completare la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="1e18a-147">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="1e18a-148">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="1e18a-148">Upgrade</span></span>

<span data-ttu-id="1e18a-149">Il processo di aggiornamento è simile al processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="1e18a-149">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="1e18a-150">Scaricare la versione più recente da Visual Studio Marketplace o usare Gestione estensioni in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1e18a-150">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
