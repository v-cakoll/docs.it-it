---
title: Come installare il generatore di modelli
description: Informazioni su come installare lo strumento del generatore di modelli di ML.NET
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.custom: mvc, how-to, mlnet-tooling
ms.openlocfilehash: b944d7f6044553251132824e7e4213119e34500e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "78848652"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="e496d-103">Come installare il generatore di modelli di ML.NET</span><span class="sxs-lookup"><span data-stu-id="e496d-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="e496d-104">Di seguito viene descritto come installare il generatore di modelli di ML.NET per aggiungere il Machine Learning alle applicazioni .NET.</span><span class="sxs-lookup"><span data-stu-id="e496d-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="e496d-105">Il generatore di modelli è attualmente in anteprima.</span><span class="sxs-lookup"><span data-stu-id="e496d-105">Model Builder is currently in Preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e496d-106">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="e496d-106">Prerequisites</span></span>

- <span data-ttu-id="e496d-107">Visual Studio 2017 versione 15.9.12 o successiva / Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e496d-107">Visual Studio 2017 version 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="e496d-108">.NET Core 2.1 SDK o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="e496d-108">.NET Core 2.1 SDK or later.</span></span>

> [!NOTE]
> <span data-ttu-id="e496d-109">.NET Core 3.0 SDK non è attualmente supportato.</span><span class="sxs-lookup"><span data-stu-id="e496d-109">.NET Core 3.0 SDK is not currently supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="e496d-110">Limitazioni</span><span class="sxs-lookup"><span data-stu-id="e496d-110">Limitations</span></span>

- <span data-ttu-id="e496d-111">L'estensione del generatore di modelli di ML.NET attualmente funziona solo in Visual Studio in Windows.</span><span class="sxs-lookup"><span data-stu-id="e496d-111">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="e496d-112">Limite del set di dati di training di 1 GB</span><span class="sxs-lookup"><span data-stu-id="e496d-112">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="e496d-113">SQL Server ha un limite di 100 migliaia di righe per il training</span><span class="sxs-lookup"><span data-stu-id="e496d-113">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="e496d-114">Microsoft SQL Server Data Tools per Visual Studio 2017 non è supportato</span><span class="sxs-lookup"><span data-stu-id="e496d-114">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="e496d-115">Installazione</span><span class="sxs-lookup"><span data-stu-id="e496d-115">Install</span></span>

<span data-ttu-id="e496d-116">Il generatore di modelli di ML.NET può essere installato tramite Visual Studio Marketplace o dall'interno di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e496d-116">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span>

### <a name="visual-studio-marketplace"></a><span data-ttu-id="e496d-117">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="e496d-117">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="e496d-118">Scaricare da [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span><span class="sxs-lookup"><span data-stu-id="e496d-118">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="e496d-119">Seguire i messaggi visualizzati per eseguire l'installazione nella versione di Visual Studio in uso</span><span class="sxs-lookup"><span data-stu-id="e496d-119">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="e496d-120">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="e496d-120">Visual Studio 2017</span></span>

1. <span data-ttu-id="e496d-121">Nella barra dei menu, selezionare**Estensioni e aggiornamenti** degli **strumenti** > </span><span class="sxs-lookup"><span data-stu-id="e496d-121">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![Finestra di dialogo Gestione estensioni aperte VS2017](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="e496d-123">All'interno del prompt *Estensioni e aggiornamenti* selezionare il nodo *Online*.</span><span class="sxs-lookup"><span data-stu-id="e496d-123">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="e496d-124">Nella barra di ricerca cercare *ML.NET Model Builder* e selezionare ML.NET Model Builder (Preview) dai risultati</span><span class="sxs-lookup"><span data-stu-id="e496d-124">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![Vs2017 ricerca e installare l'estensione di Model Builder nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="e496d-126">Seguire i messaggi visualizzati per completare l'installazione</span><span class="sxs-lookup"><span data-stu-id="e496d-126">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="e496d-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e496d-127">Visual Studio 2019</span></span>

1. <span data-ttu-id="e496d-128">Nella barra dei menu, seleziona **Gestione estensioni** > **Manage Extensions**</span><span class="sxs-lookup"><span data-stu-id="e496d-128">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![Finestra di dialogo Gestione estensioni aperte VS2019](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="e496d-130">All'interno del prompt *Estensioni e aggiornamenti* selezionare il nodo *Online*.</span><span class="sxs-lookup"><span data-stu-id="e496d-130">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="e496d-131">Digitare *ML.NET Model Builder* nella barra di ricerca e selezionare ML.NET Model Builder (Preview)</span><span class="sxs-lookup"><span data-stu-id="e496d-131">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019 ricerca e installare l'estensione di Model Builder nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="e496d-133">Seguire i messaggi visualizzati per completare l'installazione</span><span class="sxs-lookup"><span data-stu-id="e496d-133">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="e496d-134">Disinstallare</span><span class="sxs-lookup"><span data-stu-id="e496d-134">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="e496d-135">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="e496d-135">Visual Studio 2017</span></span>

1. <span data-ttu-id="e496d-136">Nella barra dei menu, selezionare**Estensioni e aggiornamenti** degli **strumenti** > </span><span class="sxs-lookup"><span data-stu-id="e496d-136">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![Finestra di dialogo Gestione estensioni di apertura VS2017](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="e496d-138">All'interno del prompt *Estensioni e aggiornamenti* espandere il nodo *Installati* e selezionare *Strumenti*</span><span class="sxs-lookup"><span data-stu-id="e496d-138">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="e496d-139">Selezionare ML.NET Model Builder (Preview) dall'elenco degli strumenti e quindi selezionare *Disinstalla*</span><span class="sxs-lookup"><span data-stu-id="e496d-139">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![Estensione di ricerca e disinstallazione di Generatore di modelli VS2017 nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="e496d-141">Seguire i messaggi visualizzati per completare la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="e496d-141">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="e496d-142">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="e496d-142">Visual Studio 2019</span></span>

1. <span data-ttu-id="e496d-143">Nella barra dei menu, seleziona **Gestione estensioni** > **Manage Extensions**</span><span class="sxs-lookup"><span data-stu-id="e496d-143">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![Finestra di dialogo Apri gestione estensioni VS2019](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="e496d-145">All'interno del prompt *Estensioni e aggiornamenti* espandere il nodo *Installati* e selezionare *Strumenti*</span><span class="sxs-lookup"><span data-stu-id="e496d-145">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="e496d-146">Selezionare ML.NET Model Builder (Preview) dall'elenco degli strumenti e quindi selezionare *Disinstalla*</span><span class="sxs-lookup"><span data-stu-id="e496d-146">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![Vs2019 ricerca e disinstallazione dell'estensione di Model Builder nella finestra di dialogo Gestione estensioni](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="e496d-148">Seguire i messaggi visualizzati per completare la disinstallazione.</span><span class="sxs-lookup"><span data-stu-id="e496d-148">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="e496d-149">Aggiornamento</span><span class="sxs-lookup"><span data-stu-id="e496d-149">Upgrade</span></span>

<span data-ttu-id="e496d-150">Il processo di aggiornamento è simile al processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="e496d-150">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="e496d-151">Scaricare la versione più recente da Visual Studio Marketplace o usare Gestione estensioni in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="e496d-151">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
