---
title: 'Procedura: Creare una nuova impostazione in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: 35a7cd8cc1daaf76a25977751ddc9ec0709e5947
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037898"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="63fd3-102">Procedura: Crea una nuova impostazione in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="63fd3-102">How To: Create a new setting at design time</span></span>

<span data-ttu-id="63fd3-103">È possibile creare una nuova impostazione in fase di progettazione usando la finestra di progettazione delle impostazioni in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="63fd3-103">You can create a new setting at design time by using the Settings designer in Visual Studio.</span></span> <span data-ttu-id="63fd3-104">Progettazione impostazioni è un'interfaccia di tipo Grid che consente di creare nuove impostazioni e specificare le proprietà per tali impostazioni.</span><span class="sxs-lookup"><span data-stu-id="63fd3-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="63fd3-105">Per le nuove impostazioni, è necessario specificare il nome, il valore, il tipo e l'ambito.</span><span class="sxs-lookup"><span data-stu-id="63fd3-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="63fd3-106">Una volta creata, l'impostazione è accessibile nel codice.</span><span class="sxs-lookup"><span data-stu-id="63fd3-106">Once a setting is created, it is accessible in code.</span></span>

## <a name="create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="63fd3-107">Creare una nuova impostazione in fase di progettazione in C\#</span><span class="sxs-lookup"><span data-stu-id="63fd3-107">Create a new setting at design time in C\#</span></span>

1. <span data-ttu-id="63fd3-108">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="63fd3-108">Open Visual Studio.</span></span>

2. <span data-ttu-id="63fd3-109">In **Esplora soluzioni**espandere il nodo **Proprietà** del progetto.</span><span class="sxs-lookup"><span data-stu-id="63fd3-109">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>

3. <span data-ttu-id="63fd3-110">Fare doppio clic sul file. Settings in cui si desidera aggiungere una nuova impostazione.</span><span class="sxs-lookup"><span data-stu-id="63fd3-110">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="63fd3-111">Il nome predefinito di questo file è Settings. Settings.</span><span class="sxs-lookup"><span data-stu-id="63fd3-111">The default name for this file is Settings.settings.</span></span>

4. <span data-ttu-id="63fd3-112">Nella finestra di progettazione delle impostazioni impostare il **nome**, il **valore**, il **tipo**e l' **ambito** per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="63fd3-112">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="63fd3-113">Ogni riga rappresenta una singola impostazione.</span><span class="sxs-lookup"><span data-stu-id="63fd3-113">Each row represents a single setting.</span></span>

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="63fd3-114">Crea una nuova impostazione in fase di progettazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="63fd3-114">Create a new setting at design time in Visual Basic</span></span>

1. <span data-ttu-id="63fd3-115">Aprire Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="63fd3-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="63fd3-116">In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nodo del progetto e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="63fd3-116">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>

3. <span data-ttu-id="63fd3-117">Nella pagina **Proprietà** selezionare la scheda **Impostazioni** .</span><span class="sxs-lookup"><span data-stu-id="63fd3-117">In the **Properties** page, select the **Settings** tab.</span></span>

4. <span data-ttu-id="63fd3-118">Nella finestra di progettazione delle impostazioni impostare il **nome**, il **valore**, il **tipo**e l' **ambito** per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="63fd3-118">In the Settings designer, set the **Name**, **Value**, **Type**, and **Scope** for your setting.</span></span> <span data-ttu-id="63fd3-119">Ogni riga rappresenta una singola impostazione.</span><span class="sxs-lookup"><span data-stu-id="63fd3-119">Each row represents a single setting.</span></span>

## <a name="see-also"></a><span data-ttu-id="63fd3-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63fd3-120">See also</span></span>

- [<span data-ttu-id="63fd3-121">Uso delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="63fd3-121">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="63fd3-122">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="63fd3-122">Application Settings Overview</span></span>](application-settings-overview.md)
- [<span data-ttu-id="63fd3-123">Procedura: Modificare il valore di un'impostazione esistente in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="63fd3-123">How To: Change the Value of an Existing Setting at Design Time</span></span>](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
