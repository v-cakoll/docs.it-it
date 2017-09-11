---
title: Oggetto My. Settings | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
dev_langs:
- VB
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4d6ee6d2d54c0e3a4af3b7cdec5f81166ce3ddce
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="mysettings-object"></a><span data-ttu-id="97c33-102">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="97c33-102">My.Settings Object</span></span>
<span data-ttu-id="97c33-103">Fornisce proprietà e metodi per accedere alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="97c33-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97c33-104">Note</span><span class="sxs-lookup"><span data-stu-id="97c33-104">Remarks</span></span>  
 <span data-ttu-id="97c33-105">Il `My.Settings` oggetto fornisce accesso alle impostazioni dell'applicazione e consente di archiviare e recuperare le impostazioni delle proprietà e altre informazioni per l'applicazione in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="97c33-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="97c33-106">Per ulteriori informazioni, vedere [impostazioni applicazione di gestione (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="97c33-106">For more information, see [Managing Application Settings (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="97c33-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="97c33-107">Properties</span></span>  
 <span data-ttu-id="97c33-108">Le proprietà del `My.Settings` oggetto forniscono accesso alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="97c33-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="97c33-109">Per aggiungere o rimuovere le impostazioni, utilizzare il **Progettazione impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="97c33-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="97c33-110">Ogni impostazione ha un **nome**, **tipo**, **ambito**, e **valore**, e queste impostazioni determinano come la proprietà di accesso a ogni impostazione viene visualizzata nel `My.Settings` oggetto:</span><span class="sxs-lookup"><span data-stu-id="97c33-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="97c33-111">**Nome** determina il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="97c33-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="97c33-112">**Tipo** determina il tipo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="97c33-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="97c33-113">**Ambito** indica se la proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="97c33-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="97c33-114">Se il valore è **applicazione**, la proprietà è di sola lettura; se il valore è **utente**, la proprietà è di lettura-scrittura.</span><span class="sxs-lookup"><span data-stu-id="97c33-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="97c33-115">**Valore** è il valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="97c33-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="97c33-116">Metodi</span><span class="sxs-lookup"><span data-stu-id="97c33-116">Methods</span></span>  
  
|<span data-ttu-id="97c33-117">Metodo</span><span class="sxs-lookup"><span data-stu-id="97c33-117">Method</span></span>|<span data-ttu-id="97c33-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="97c33-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="97c33-119">Consente di ricaricare le impostazioni utente da ultimi valori salvati.</span><span class="sxs-lookup"><span data-stu-id="97c33-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="97c33-120">Salva le impostazioni utente correnti.</span><span class="sxs-lookup"><span data-stu-id="97c33-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="97c33-121">Il `My.Settings` oggetto fornisce inoltre le proprietà avanzate ed ereditati dalla <xref:System.Configuration.ApplicationSettingsBase>classe.</xref:System.Configuration.ApplicationSettingsBase></span><span class="sxs-lookup"><span data-stu-id="97c33-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="97c33-122">Attività</span><span class="sxs-lookup"><span data-stu-id="97c33-122">Tasks</span></span>  
 <span data-ttu-id="97c33-123">Nella tabella seguente sono elencati esempi di attività che coinvolgono il `My.Settings` oggetto.</span><span class="sxs-lookup"><span data-stu-id="97c33-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="97c33-124">Per</span><span class="sxs-lookup"><span data-stu-id="97c33-124">To</span></span>|<span data-ttu-id="97c33-125">Vedere</span><span class="sxs-lookup"><span data-stu-id="97c33-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="97c33-126">Leggere un'impostazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="97c33-126">Read an application setting</span></span>|[<span data-ttu-id="97c33-127">Procedura: leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="97c33-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="97c33-128">Modificare un'impostazione utente</span><span class="sxs-lookup"><span data-stu-id="97c33-128">Change a user setting</span></span>|[<span data-ttu-id="97c33-129">Procedura: modificare le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="97c33-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="97c33-130">Mantenere le impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="97c33-130">Persist user settings</span></span>|[<span data-ttu-id="97c33-131">Procedura: mantenere le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="97c33-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="97c33-132">Creare una griglia delle proprietà per le impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="97c33-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="97c33-133">Procedura: creare griglie di proprietà per le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="97c33-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="97c33-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="97c33-134">Example</span></span>  
 <span data-ttu-id="97c33-135">Questo esempio viene visualizzato il valore di `Nickname` impostazione.</span><span class="sxs-lookup"><span data-stu-id="97c33-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 <span data-ttu-id="97c33-136">[!code-vb[VbVbalrMyResources&#14;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="97c33-136">[!code-vb[VbVbalrMyResources#14](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-settings-object_1.vb)]</span></span>  
  
 <span data-ttu-id="97c33-137">Per eseguire questo esempio, l'applicazione deve contenere un `Nickname` impostazione di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="97c33-137">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97c33-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="97c33-138">See Also</span></span>  
 <span data-ttu-id="97c33-139"><xref:System.Configuration.ApplicationSettingsBase></xref:System.Configuration.ApplicationSettingsBase></span><span class="sxs-lookup"><span data-stu-id="97c33-139"><xref:System.Configuration.ApplicationSettingsBase></span></span>   
<span data-ttu-id="97c33-140"> [Procedura: leggere le impostazioni dell'applicazione in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span><span class="sxs-lookup"><span data-stu-id="97c33-140"> [How to: Read Application Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md) </span></span>  
<span data-ttu-id="97c33-141"> [Procedura: modificare le impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="97c33-141"> [How to: Change User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md) </span></span>  
<span data-ttu-id="97c33-142"> [Procedura: mantenere le impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="97c33-142"> [How to: Persist User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md) </span></span>  
<span data-ttu-id="97c33-143"> [Procedura: creare griglie di proprietà per le impostazioni utente in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span><span class="sxs-lookup"><span data-stu-id="97c33-143"> [How to: Create Property Grids for User Settings in Visual Basic](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md) </span></span>  
<span data-ttu-id="97c33-144"> [Gestione delle impostazioni di un'applicazione (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)</span><span class="sxs-lookup"><span data-stu-id="97c33-144"> [Managing Application Settings (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-settings-dotnet)</span></span>
