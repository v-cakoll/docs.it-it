---
title: 'Procedura: creare una nuova impostazione in fase di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04b86579f45c5a357f8759bf36ae41f7a5c6e98b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-new-setting-at-design-time"></a><span data-ttu-id="75ef0-102">Procedura: creare una nuova impostazione in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="75ef0-102">How To: Create a New Setting at Design Time</span></span>
<span data-ttu-id="75ef0-103">È possibile creare una nuova impostazione in fase di progettazione tramite Progettazione impostazioni.</span><span class="sxs-lookup"><span data-stu-id="75ef0-103">You can create a new setting at design time by using the Settings designer.</span></span> <span data-ttu-id="75ef0-104">Progettazione impostazioni è un'interfaccia di stile di griglia che consente di creare nuove impostazioni e specificare le proprietà per tali impostazioni.</span><span class="sxs-lookup"><span data-stu-id="75ef0-104">The Settings designer is a grid-style interface that allows you to create new settings and specify properties for those settings.</span></span> <span data-ttu-id="75ef0-105">È necessario specificare nome, valore, tipo e ambito per le nuove impostazioni.</span><span class="sxs-lookup"><span data-stu-id="75ef0-105">You must specify Name, Value, Type and Scope for your new settings.</span></span> <span data-ttu-id="75ef0-106">Dopo aver creata un'impostazione, è accessibile nel codice.</span><span class="sxs-lookup"><span data-stu-id="75ef0-106">Once a setting is created, it is accessible in code.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a><span data-ttu-id="75ef0-107">Per creare una nuova impostazione in fase di progettazione in c#</span><span class="sxs-lookup"><span data-stu-id="75ef0-107">To create a new setting at design time in C#</span></span>  
  
1.  <span data-ttu-id="75ef0-108">In **Esplora**, espandere il **proprietà** nodo del progetto.</span><span class="sxs-lookup"><span data-stu-id="75ef0-108">In **Solution Explorer**, expand the **Properties** node of your project.</span></span>  
  
2.  <span data-ttu-id="75ef0-109">Doppio clic sul file. Settings in cui si desidera aggiungere una nuova impostazione.</span><span class="sxs-lookup"><span data-stu-id="75ef0-109">Double-click the .settings file in which you want to add a new setting.</span></span> <span data-ttu-id="75ef0-110">Il nome predefinito per questo file è Settings.</span><span class="sxs-lookup"><span data-stu-id="75ef0-110">The default name for this file is Settings.settings.</span></span>  
  
3.  <span data-ttu-id="75ef0-111">Nella finestra di progettazione impostazioni, impostare il nome, valore, tipo e ambito per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="75ef0-111">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="75ef0-112">Ogni riga rappresenta una singola impostazione.</span><span class="sxs-lookup"><span data-stu-id="75ef0-112">Each row represents a single setting.</span></span>  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a><span data-ttu-id="75ef0-113">Per creare una nuova impostazione in fase di progettazione in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="75ef0-113">To create a new setting at design time in Visual Basic</span></span>  
  
1.  <span data-ttu-id="75ef0-114">In **Esplora**, fare doppio clic su un nodo di progetto e scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="75ef0-114">In **Solution Explorer**, right-click your project node and choose **Properties**.</span></span>  
  
2.  <span data-ttu-id="75ef0-115">Nel **proprietà** pagina, selezionare il **impostazioni** scheda.</span><span class="sxs-lookup"><span data-stu-id="75ef0-115">In the **Properties** page, select the **Settings** tab.</span></span>  
  
3.  <span data-ttu-id="75ef0-116">Nella finestra di progettazione impostazioni, impostare il nome, valore, tipo e ambito per l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="75ef0-116">In the Settings designer, set the Name, Value, Type, and Scope for your setting.</span></span> <span data-ttu-id="75ef0-117">Ogni riga rappresenta una singola impostazione.</span><span class="sxs-lookup"><span data-stu-id="75ef0-117">Each row represents a single setting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75ef0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="75ef0-118">See Also</span></span>  
 [<span data-ttu-id="75ef0-119">Uso delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="75ef0-119">Using Application Settings and User Settings</span></span>](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [<span data-ttu-id="75ef0-120">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="75ef0-120">Application Settings Overview</span></span>](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [<span data-ttu-id="75ef0-121">Procedura: Modificare il valore di un'impostazione esistente in fase di progettazione</span><span class="sxs-lookup"><span data-stu-id="75ef0-121">How To: Change the Value of an Existing Setting at Design Time</span></span>](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)
