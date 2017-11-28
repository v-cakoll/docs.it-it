---
title: "Procedura: creare griglie di proprietà per impostazioni utente in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], creating property grids for user settings
- user settings [Visual Basic], creating property grids
- property grids [Visual Basic], creating for user settings
- property grids
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 81a79945dfc0b1501134bc1b0197c18093a5dfae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-property-grids-for-user-settings-in-visual-basic"></a><span data-ttu-id="dc48c-102">Procedura: creare griglie di proprietà per impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc48c-102">How to: Create Property Grids for User Settings in Visual Basic</span></span>
<span data-ttu-id="dc48c-103">È possibile creare una griglia di proprietà delle impostazioni utente popolando un controllo <xref:System.Windows.Forms.PropertyGrid> con le proprietà dell'impostazione utente dell'oggetto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="dc48c-103">You can create a property grid for user settings by populating a <xref:System.Windows.Forms.PropertyGrid> control with the user setting properties of the `My.Settings` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc48c-104">Affinché l'esempio funzioni, per l'applicazione devono essere state configurate le impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="dc48c-104">In order for this example to work, your application must have its user settings configured.</span></span> <span data-ttu-id="dc48c-105">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="dc48c-105">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="dc48c-106">L'oggetto `My.Settings` espone ogni impostazione come una proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc48c-106">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="dc48c-107">Il nome della proprietà corrisponde allo stesso nome dell'impostazione e il tipo di proprietà al tipo di impostazione.</span><span class="sxs-lookup"><span data-stu-id="dc48c-107">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="dc48c-108">L'**ambito** dell'impostazione determina se la proprietà è di sola lettura. La proprietà di un'impostazione dell'ambito dell'**applicazione** è di sola lettura, mentre la proprietà dell'ambito dell'**utente**-è di lettura e scrittura.</span><span class="sxs-lookup"><span data-stu-id="dc48c-108">The setting's **Scope** determines if the property is read-only; the property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="dc48c-109">Per altre informazioni, vedere [Oggetto My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="dc48c-109">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc48c-110">Non è possibile modificare o salvare i valori delle impostazioni dell'ambito dell'applicazione in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="dc48c-110">You cannot change or save the values of application-scope settings at run time.</span></span> <span data-ttu-id="dc48c-111">È possibile modificare le impostazioni dell'ambito dell'applicazione quando si crea l'applicazione tramite **Creazione progetti** o modificando il file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="dc48c-111">Application-scope settings can be changed only when creating the application (through the **Project Designer**) or by editing the application's configuration file.</span></span> <span data-ttu-id="dc48c-112">Per altre informazioni, vedere [Gestione delle impostazioni di un'applicazione (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="dc48c-112">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
 <span data-ttu-id="dc48c-113">In questo esempio viene usato un controllo <xref:System.Windows.Forms.PropertyGrid> per accedere alle proprietà dell'impostazione utente dell'oggetto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="dc48c-113">This example uses a <xref:System.Windows.Forms.PropertyGrid> control to access the user-setting properties of the `My.Settings` object.</span></span> <span data-ttu-id="dc48c-114">Per impostazione predefinita, <xref:System.Windows.Forms.PropertyGrid> mostra tutte le proprietà dell'oggetto `My.Settings`.</span><span class="sxs-lookup"><span data-stu-id="dc48c-114">By default, the <xref:System.Windows.Forms.PropertyGrid> shows all the properties of the `My.Settings` object.</span></span> <span data-ttu-id="dc48c-115">Tuttavia, le proprietà dell'impostazione utente hanno l'attributo <xref:System.Configuration.UserScopedSettingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="dc48c-115">However, the user-setting properties have the <xref:System.Configuration.UserScopedSettingAttribute> attribute.</span></span> <span data-ttu-id="dc48c-116">In questo esempio la proprietà <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> di <xref:System.Windows.Forms.PropertyGrid> viene impostata su <xref:System.Configuration.UserScopedSettingAttribute> per visualizzare solo le proprietà dell'impostazione utente.</span><span class="sxs-lookup"><span data-stu-id="dc48c-116">This example sets the <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> property of the <xref:System.Windows.Forms.PropertyGrid> to <xref:System.Configuration.UserScopedSettingAttribute> to display only the user-setting properties.</span></span>  
  
### <a name="to-add-a-user-setting-property-grid"></a><span data-ttu-id="dc48c-117">Per aggiungere una griglia delle proprietà dell'impostazione utente</span><span class="sxs-lookup"><span data-stu-id="dc48c-117">To add a user setting property grid</span></span>  
  
1.  <span data-ttu-id="dc48c-118">Aggiungere il controllo **PropertyGrid** dalla **casella degli strumenti** all'area di progettazione dell'applicazione, presupponendo che questo campo sia `Form1`.</span><span class="sxs-lookup"><span data-stu-id="dc48c-118">Add the **PropertyGrid** control from the **Toolbox** to the design surface for your application, assumed here to be `Form1`.</span></span>  
  
     <span data-ttu-id="dc48c-119">Il nome predefinito del controllo PropertyGrid è `PropertyGrid1`.</span><span class="sxs-lookup"><span data-stu-id="dc48c-119">The default name of the property-grid control is `PropertyGrid1`.</span></span>  
  
2.  <span data-ttu-id="dc48c-120">Fare doppio clic sull'area di progettazione del `Form1` per aprire il codice per il gestore eventi che carica il form.</span><span class="sxs-lookup"><span data-stu-id="dc48c-120">Double-click the design surface for `Form1` to open the code for the form-load event handler.</span></span>  
  
3.  <span data-ttu-id="dc48c-121">Impostare l'oggetto `My.Settings` come oggetto selezionato per la griglia delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="dc48c-121">Set the `My.Settings` object as the selected object for the property grid.</span></span>  
  
     [!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]  
  
4.  <span data-ttu-id="dc48c-122">Configurare la griglia delle proprietà affinché mostri solo le impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="dc48c-122">Configure the property grid to show only the user settings.</span></span>  
  
     [!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="dc48c-123">Per visualizzare solo le impostazioni dell'ambito applicazione, usare l'attributo <xref:System.Configuration.ApplicationScopedSettingAttribute> anziché <xref:System.Configuration.UserScopedSettingAttribute>.</span><span class="sxs-lookup"><span data-stu-id="dc48c-123">To show only the application-scope settings, use the <xref:System.Configuration.ApplicationScopedSettingAttribute> attribute instead of  <xref:System.Configuration.UserScopedSettingAttribute>.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="dc48c-124">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="dc48c-124">Robust Programming</span></span>  
 <span data-ttu-id="dc48c-125">Alla chiusura dell'applicazione vengono salvate le impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="dc48c-125">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="dc48c-126">Per salvare immediatamente le impostazioni, chiamare il metodo `My.Settings.Save`.</span><span class="sxs-lookup"><span data-stu-id="dc48c-126">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="dc48c-127">Per altre informazioni, vedere [Procedura: Mantenere le impostazioni dell'utente in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="dc48c-127">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc48c-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dc48c-128">See Also</span></span>  
 [<span data-ttu-id="dc48c-129">Oggetto My.Settings</span><span class="sxs-lookup"><span data-stu-id="dc48c-129">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [<span data-ttu-id="dc48c-130">Procedura: Leggere le impostazioni dell'applicazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc48c-130">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)  
 [<span data-ttu-id="dc48c-131">Procedura: Modificare le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc48c-131">How to: Change User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)  
 [<span data-ttu-id="dc48c-132">Procedura: Mantenere le impostazioni utente in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc48c-132">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)  
 [<span data-ttu-id="dc48c-133">Gestione delle impostazioni di un'applicazione (.NET)</span><span class="sxs-lookup"><span data-stu-id="dc48c-133">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
