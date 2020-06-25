---
title: 'Procedura: creare una nuova impostazione in fase di progettazione'
description: Informazioni su come creare una nuova impostazione di Windows Forms in fase di progettazione usando la finestra di progettazione delle impostazioni in Visual Studio.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: ce37b42191999e29de2f2f7f7e7abfa0ec3f4d47
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325849"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="49297-103">Procedura: creare una nuova impostazione in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="49297-103">How To: Create a new setting at design time</span></span>

<span data-ttu-id="49297-104">È possibile creare una nuova impostazione in fase di progettazione usando la finestra di progettazione delle impostazioni in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="49297-104">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="49297-105">Progettazione impostazioni è un'interfaccia di tipo Grid che consente di creare nuove impostazioni e specificare le proprietà per tali impostazioni.</span><span class="sxs-lookup"><span data-stu-id="49297-105">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="49297-106">Per le nuove impostazioni, è necessario specificare il nome, il valore, il tipo e l'ambito.</span><span class="sxs-lookup"><span data-stu-id="49297-106">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="49297-107">Una volta creata, l'impostazione è accessibile nel codice.</span><span class="sxs-lookup"><span data-stu-id="49297-107">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="49297-108">Creare una nuova impostazione in fase di progettazione in C\#</span><span class="sxs-lookup"><span data-stu-id="49297-108">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="49297-109">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="49297-109">Open Visual Studio.</span></span>

2. <span data-ttu-id="49297-110">In **Esplora soluzioni**espandere il nodo **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="49297-110">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="49297-111">Fare doppio clic sul file. Settings in cui si desidera aggiungere una nuova impostazione.</span><span class="sxs-lookup"><span data-stu-id="49297-111">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="49297-112">Il nome predefinito di questo file è Settings. Settings.</span><span class="sxs-lookup"><span data-stu-id="49297-112">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="49297-113">Nella finestra di progettazione delle impostazioni impostare il **nome**, il **valore**, il **tipo**e l' **ambito** per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="49297-113">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="49297-114">Ogni riga rappresenta una singola impostazione.</span><span class="sxs-lookup"><span data-stu-id="49297-114">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="49297-115">Crea una nuova impostazione in fase di progettazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="49297-115">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="49297-116">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="49297-116">Open Visual Studio.</span></span>

2. <span data-ttu-id="49297-117">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo del progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="49297-117">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="49297-118">Nella pagina **Proprietà** selezionare la scheda **Impostazioni** .</span><span class="sxs-lookup"><span data-stu-id="49297-118">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="49297-119">Nella finestra di progettazione delle impostazioni impostare il **nome**, il **valore**, il **tipo**e l' **ambito** per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="49297-119">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="49297-120">Ogni riga rappresenta una singola impostazione.</span><span class="sxs-lookup"><span data-stu-id="49297-120">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="49297-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="49297-121">See also</span></span>

- [<span data-ttu-id="49297-122">Utilizzo delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="49297-122">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="49297-123">Panoramica delle impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="49297-123">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="49297-124">Procedura: modificare il valore di un'impostazione esistente in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="49297-124">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
