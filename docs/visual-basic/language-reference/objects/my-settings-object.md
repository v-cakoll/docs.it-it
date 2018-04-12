---
title: Oggetto My.Settings
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2f744460f8ea6c6c7f5c8c5e1658bd357e910def
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="mysettings-object"></a><span data-ttu-id="b60e7-102">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="b60e7-102">My.Settings Object</span></span>
<span data-ttu-id="b60e7-103">Fornisce proprietà e metodi per accedere alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b60e7-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b60e7-104">Note</span><span class="sxs-lookup"><span data-stu-id="b60e7-104">Remarks</span></span>  
 <span data-ttu-id="b60e7-105">Il `My.Settings` oggetto fornisce accesso alle impostazioni dell'applicazione e consente di archiviare e recuperare le impostazioni delle proprietà e altre informazioni per l'applicazione in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="b60e7-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="b60e7-106">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="b60e7-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b60e7-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="b60e7-107">Properties</span></span>  
 <span data-ttu-id="b60e7-108">Le proprietà dell'oggetto `My.Settings` offrono accesso alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b60e7-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="b60e7-109">Per aggiungere o rimuovere le impostazioni, utilizzare il **Progettazione impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="b60e7-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="b60e7-110">Ogni impostazione abbia un **nome**, **tipo**, **ambito**, e **valore**, e queste impostazioni determinano come la proprietà di accesso a ogni impostazione è presente il `My.Settings` oggetto:</span><span class="sxs-lookup"><span data-stu-id="b60e7-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="b60e7-111">**Nome** determina il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b60e7-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="b60e7-112">**Tipo** determina il tipo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b60e7-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="b60e7-113">**Ambito** indica se la proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b60e7-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="b60e7-114">Se il valore è **applicazione**, la proprietà è di sola lettura; se il valore è **utente**, la proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="b60e7-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="b60e7-115">**Valore** è il valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="b60e7-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b60e7-116">Metodi</span><span class="sxs-lookup"><span data-stu-id="b60e7-116">Methods</span></span>  
  
|<span data-ttu-id="b60e7-117">Metodo</span><span class="sxs-lookup"><span data-stu-id="b60e7-117">Method</span></span>|<span data-ttu-id="b60e7-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b60e7-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="b60e7-119">Consente di ricaricare le impostazioni utente da ultimi valori salvati.</span><span class="sxs-lookup"><span data-stu-id="b60e7-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="b60e7-120">Salva le impostazioni utente correnti.</span><span class="sxs-lookup"><span data-stu-id="b60e7-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="b60e7-121">Il `My.Settings` oggetto fornisce inoltre le proprietà avanzate ed ereditati dalla <xref:System.Configuration.ApplicationSettingsBase> classe.</span><span class="sxs-lookup"><span data-stu-id="b60e7-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="b60e7-122">Attività</span><span class="sxs-lookup"><span data-stu-id="b60e7-122">Tasks</span></span>  
 <span data-ttu-id="b60e7-123">Nella tabella seguente sono elencati esempi di attività che coinvolgono la `My.Settings` oggetto.</span><span class="sxs-lookup"><span data-stu-id="b60e7-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="b60e7-124">Per</span><span class="sxs-lookup"><span data-stu-id="b60e7-124">To</span></span>|<span data-ttu-id="b60e7-125">Vedere</span><span class="sxs-lookup"><span data-stu-id="b60e7-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="b60e7-126">Leggere un'impostazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="b60e7-126">Read an application setting</span></span>|[<span data-ttu-id="b60e7-127">Procedura: Leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b60e7-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="b60e7-128">Modificare un'impostazione utente</span><span class="sxs-lookup"><span data-stu-id="b60e7-128">Change a user setting</span></span>|[<span data-ttu-id="b60e7-129">Procedura: Modificare le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b60e7-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="b60e7-130">Mantenere le impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="b60e7-130">Persist user settings</span></span>|[<span data-ttu-id="b60e7-131">Procedura: Mantenere le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b60e7-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="b60e7-132">Creare una griglia delle proprietà per le impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="b60e7-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="b60e7-133">Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b60e7-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="b60e7-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="b60e7-134">Example</span></span>  
 <span data-ttu-id="b60e7-135">Nell'esempio riportato di seguito viene mostrato il valore dell'impostazione `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="b60e7-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]  
  
 <span data-ttu-id="b60e7-136">Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione `Nickname` di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="b60e7-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60e7-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b60e7-137">See Also</span></span>  
 <xref:System.Configuration.ApplicationSettingsBase>  
 [<span data-ttu-id="b60e7-138">Procedura: Leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b60e7-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [<span data-ttu-id="b60e7-139">Procedura: Modificare le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b60e7-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [<span data-ttu-id="b60e7-140">Procedura: Mantenere le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b60e7-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="b60e7-141">Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b60e7-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)  
 [<span data-ttu-id="b60e7-142">Gestione delle impostazioni di un'applicazione (.NET)</span><span class="sxs-lookup"><span data-stu-id="b60e7-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
