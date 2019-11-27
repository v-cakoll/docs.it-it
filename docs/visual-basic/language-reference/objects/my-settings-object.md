---
title: Oggetto My.Settings
ms.date: 07/20/2015
f1_keywords:
- My.MySettingsProperty.Settings
- My.Settings
helpviewer_keywords:
- My.Settings object
ms.assetid: 41f30dc1-202a-4273-b9b7-5728941f996c
ms.openlocfilehash: 9560a51332ea596d4cf2228f1e07c158a0457ece
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350351"
---
# <a name="mysettings-object"></a><span data-ttu-id="8505d-102">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="8505d-102">My.Settings Object</span></span>
<span data-ttu-id="8505d-103">Fornisce le proprietà e i metodi per l'accesso alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8505d-103">Provides properties and methods for accessing the application's settings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8505d-104">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="8505d-104">Remarks</span></span>  
 <span data-ttu-id="8505d-105">L'oggetto `My.Settings` fornisce l'accesso alle impostazioni dell'applicazione e consente di archiviare e recuperare dinamicamente le impostazioni delle proprietà e altre informazioni per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8505d-105">The `My.Settings` object provides access to the application's settings and allows you to dynamically store and retrieve property settings and other information for your application.</span></span> <span data-ttu-id="8505d-106">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="8505d-106">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8505d-107">Proprietà</span><span class="sxs-lookup"><span data-stu-id="8505d-107">Properties</span></span>  
 <span data-ttu-id="8505d-108">Le proprietà dell'oggetto `My.Settings` offrono accesso alle impostazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="8505d-108">The properties of the `My.Settings` object provide access to your application's settings.</span></span> <span data-ttu-id="8505d-109">Per aggiungere o rimuovere le impostazioni, utilizzare la **finestra di progettazione impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="8505d-109">To add or remove settings, use the **Settings Designer**.</span></span>  
  
 <span data-ttu-id="8505d-110">Ogni impostazione ha un **nome**, un **tipo**, un **ambito**e un **valore**e queste impostazioni determinano il modo in cui la proprietà per accedere a ogni impostazione viene visualizzata nell'oggetto `My.Settings`:</span><span class="sxs-lookup"><span data-stu-id="8505d-110">Each setting has a **Name**, **Type**, **Scope**, and **Value**, and these settings determine how the property to access each setting appears in the `My.Settings` object:</span></span>  
  
- <span data-ttu-id="8505d-111">**Nome** determina il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8505d-111">**Name** determines the name of the property.</span></span>  
  
- <span data-ttu-id="8505d-112">Il **tipo** determina il tipo della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8505d-112">**Type** determines the type of the property.</span></span>  
  
- <span data-ttu-id="8505d-113">**Scope** indica se la proprietà è di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="8505d-113">**Scope** indicates if the property is read-only.</span></span> <span data-ttu-id="8505d-114">Se il valore è **Application**, la proprietà è di sola lettura. Se il valore è **User**, la proprietà è di lettura/scrittura.</span><span class="sxs-lookup"><span data-stu-id="8505d-114">If the value is **Application**, the property is read-only; if the value is **User**, the property is read-write.</span></span>  
  
- <span data-ttu-id="8505d-115">**Value** è il valore predefinito della proprietà.</span><span class="sxs-lookup"><span data-stu-id="8505d-115">**Value** is the default value of the property.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8505d-116">Metodi</span><span class="sxs-lookup"><span data-stu-id="8505d-116">Methods</span></span>  
  
|<span data-ttu-id="8505d-117">Metodo</span><span class="sxs-lookup"><span data-stu-id="8505d-117">Method</span></span>|<span data-ttu-id="8505d-118">description</span><span class="sxs-lookup"><span data-stu-id="8505d-118">Description</span></span>|  
|---|---|  
|`Reload`|<span data-ttu-id="8505d-119">Ricarica le impostazioni utente dagli ultimi valori salvati.</span><span class="sxs-lookup"><span data-stu-id="8505d-119">Reloads the user settings from the last saved values.</span></span>|  
|`Save`|<span data-ttu-id="8505d-120">Salva le impostazioni dell'utente corrente.</span><span class="sxs-lookup"><span data-stu-id="8505d-120">Saves the current user settings.</span></span>|  
  
 <span data-ttu-id="8505d-121">L'oggetto `My.Settings` fornisce anche proprietà e metodi avanzati, ereditati dalla classe <xref:System.Configuration.ApplicationSettingsBase>.</span><span class="sxs-lookup"><span data-stu-id="8505d-121">The `My.Settings` object also provides advanced properties and methods, inherited from the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="8505d-122">Attività</span><span class="sxs-lookup"><span data-stu-id="8505d-122">Tasks</span></span>  
 <span data-ttu-id="8505d-123">Nella tabella seguente sono elencati esempi di attività relative all'oggetto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="8505d-123">The following table lists examples of tasks involving the `My.Settings` object.</span></span>  
  
|<span data-ttu-id="8505d-124">A</span><span class="sxs-lookup"><span data-stu-id="8505d-124">To</span></span>|<span data-ttu-id="8505d-125">Vedere</span><span class="sxs-lookup"><span data-stu-id="8505d-125">See</span></span>|  
|---|---|  
|<span data-ttu-id="8505d-126">Leggi un'impostazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="8505d-126">Read an application setting</span></span>|[<span data-ttu-id="8505d-127">Procedura: Leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8505d-127">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)|  
|<span data-ttu-id="8505d-128">Modificare un'impostazione utente</span><span class="sxs-lookup"><span data-stu-id="8505d-128">Change a user setting</span></span>|[<span data-ttu-id="8505d-129">Procedura: Modificare le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8505d-129">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)|  
|<span data-ttu-id="8505d-130">Mantieni impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="8505d-130">Persist user settings</span></span>|[<span data-ttu-id="8505d-131">Procedura: Mantenere le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8505d-131">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)|  
|<span data-ttu-id="8505d-132">Creare una griglia di proprietà per le impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="8505d-132">Create a property grid for user settings</span></span>|[<span data-ttu-id="8505d-133">Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8505d-133">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)|  
  
## <a name="example"></a><span data-ttu-id="8505d-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="8505d-134">Example</span></span>  
 <span data-ttu-id="8505d-135">Nell'esempio riportato di seguito viene mostrato il valore dell'impostazione `Nickname`.</span><span class="sxs-lookup"><span data-stu-id="8505d-135">This example displays the value of the `Nickname` setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#14)]  
  
 <span data-ttu-id="8505d-136">Affinché l'esempio funzioni, l'applicazione deve contenere un'impostazione `Nickname` di tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="8505d-136">For this example to work, your application must have a `Nickname` setting, of type `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8505d-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8505d-137">See also</span></span>

- <xref:System.Configuration.ApplicationSettingsBase>
- [<span data-ttu-id="8505d-138">Procedura: Leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8505d-138">How to: Read Application Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="8505d-139">Procedura: Modificare le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8505d-139">How to: Change User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)
- [<span data-ttu-id="8505d-140">Procedura: Mantenere le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8505d-140">How to: Persist User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="8505d-141">Procedura: Creare griglie di proprietà per impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8505d-141">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="8505d-142">Gestione delle impostazioni di un'applicazione (.NET)</span><span class="sxs-lookup"><span data-stu-id="8505d-142">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
