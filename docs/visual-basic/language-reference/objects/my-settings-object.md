---
title: Oggetto My. Settings (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: a962f7cce961b1ee6829702a6815ba02c534efb4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840367"
---
# <a name="mysettings-object"></a><span data-ttu-id="598f9-102">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="598f9-102">My.Settings Object</span></span>
<span data-ttu-id="598f9-103">Fornisce proprietà e metodi per l'accesso alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="598f9-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="598f9-104">Note</span><span class="sxs-lookup"><span data-stu-id="598f9-104">Remarks</span></span>  
 <span data-ttu-id="598f9-105">Il `My.Settings` oggetto consente di accedere alle impostazioni dell'applicazione e consente di archiviare e recuperare le impostazioni delle proprietà e altre informazioni per l'applicazione in modo dinamico.</span><span class="sxs-lookup"><span data-stu-id="598f9-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="598f9-106">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="598f9-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="598f9-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="598f9-107">Properties</span></span>  
 <span data-ttu-id="598f9-108">Le proprietà dell'oggetto `My.Settings` offrono accesso alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="598f9-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="598f9-109">Per aggiungere o rimuovere le impostazioni, usare il **Progettazione impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="598f9-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="598f9-110">Ciascuna impostazione dispone di un **Name**, **tipo**, **ambito**, e **valore**, e queste impostazioni determinano come la proprietà di accesso a ogni impostazione viene visualizzato nei `My.Settings` oggetto:</span><span class="sxs-lookup"><span data-stu-id="598f9-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
-   <span data-ttu-id="598f9-111">**Nome** determina il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="598f9-111">**Name** determines the name of the property.</span></span>  
  
-   <span data-ttu-id="598f9-112">**Tipo** determina il tipo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="598f9-112">**Type** determines the type of the property.</span></span>  
  
-   <span data-ttu-id="598f9-113">**Ambito** indica se la proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="598f9-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="598f9-114">Se il valore è **Application**, la proprietà è di sola lettura; se il valore è **utente**, la proprietà è di lettura / scrittura.</span><span class="sxs-lookup"><span data-stu-id="598f9-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
-   <span data-ttu-id="598f9-115">**Valore** è il valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="598f9-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="598f9-116">Metodi</span><span class="sxs-lookup"><span data-stu-id="598f9-116">Methods</span></span>  
  
|<span data-ttu-id="598f9-117">Metodo</span><span class="sxs-lookup"><span data-stu-id="598f9-117">Method</span></span>|<span data-ttu-id="598f9-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="598f9-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="598f9-119">Consente di ricaricare le impostazioni utente da ultimi valori salvati.</span><span class="sxs-lookup"><span data-stu-id="598f9-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="598f9-120">Salva le impostazioni utente correnti.</span><span class="sxs-lookup"><span data-stu-id="598f9-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="598f9-121">Il `My.Settings` oggetto fornisce anche le proprietà avanzate e i metodi, ereditati dal <xref:System.Configuration.ApplicationSettingsBase> classe.</span><span class="sxs-lookup"><span data-stu-id="598f9-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="598f9-122">Attività</span><span class="sxs-lookup"><span data-stu-id="598f9-122">Tasks</span></span>  
 <span data-ttu-id="598f9-123">La tabella seguente elenca alcuni esempi di attività che implicano il `My.Settings` oggetto.</span><span class="sxs-lookup"><span data-stu-id="598f9-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="598f9-124">A</span><span class="sxs-lookup"><span data-stu-id="598f9-124">To</span></span>|<span data-ttu-id="598f9-125">Vedere</span><span class="sxs-lookup"><span data-stu-id="598f9-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="598f9-126">Leggere un'impostazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="598f9-126">Read an application setting</span></span>|[<span data-ttu-id="598f9-127">Procedura: Leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598f9-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="598f9-128">Modificare un'impostazione utente</span><span class="sxs-lookup"><span data-stu-id="598f9-128">Change a user setting</span></span>|[<span data-ttu-id="598f9-129">Procedura: Modificare le impostazioni dell'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598f9-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="598f9-130">Mantenere le impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="598f9-130">Persist user settings</span></span>|[<span data-ttu-id="598f9-131">Procedura: Mantenere le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598f9-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="598f9-132">Creare una griglia delle proprietà per impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="598f9-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="598f9-133">Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598f9-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="598f9-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="598f9-134">Example</span></span>  
 <span data-ttu-id="598f9-135">Nell'esempio riportato di seguito viene mostrato il valore dell'impostazione `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="598f9-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="598f9-136">Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione `Nickname` di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="598f9-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598f9-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="598f9-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="598f9-138">Procedura: Leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598f9-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="598f9-139">Procedura: Modificare le impostazioni dell'utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598f9-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="598f9-140">Procedura: Mantenere le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598f9-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="598f9-141">Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="598f9-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="598f9-142">Gestione delle impostazioni di un'applicazione (.NET)</span><span class="sxs-lookup"><span data-stu-id="598f9-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
