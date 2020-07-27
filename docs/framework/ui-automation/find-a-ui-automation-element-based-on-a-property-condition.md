---
title: Trovare un elemento di automazione interfaccia utente in base a una proprietà
description: Trovare un elemento di automazione interfaccia utente in base a una condizione di proprietà. Individuare un elemento all'interno dell'albero di automazione interfaccia utente in base a una proprietà o a proprietà specifiche.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 5e5fa4fde9049bd87b2722fa9b7d084d96ff6f42
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168430"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="d08ff-104">Trovare un elemento di automazione interfaccia utente in base a una proprietà</span><span class="sxs-lookup"><span data-stu-id="d08ff-104">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
> <span data-ttu-id="d08ff-105">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="d08ff-105">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d08ff-106">Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="d08ff-106">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>  
  
 <span data-ttu-id="d08ff-107">Questo argomento contiene codice di esempio che illustra come individuare un elemento all'interno dell' [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] albero in base a una proprietà o a proprietà specifiche.</span><span class="sxs-lookup"><span data-stu-id="d08ff-107">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d08ff-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="d08ff-108">Example</span></span>  
 <span data-ttu-id="d08ff-109">Nell'esempio seguente viene specificato un set di condizioni di proprietà che identificano un determinato elemento (o elementi) di interesse nell' <xref:System.Windows.Automation.AutomationElement> albero.</span><span class="sxs-lookup"><span data-stu-id="d08ff-109">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="d08ff-110">Una ricerca di tutti gli elementi corrispondenti viene quindi eseguita con il <xref:System.Windows.Automation.AutomationElement.FindAll%2A> metodo che incorpora una serie di <xref:System.Windows.Automation.AndCondition> operazioni booleane per limitare il numero di elementi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="d08ff-110">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d08ff-111">Quando si esegue una ricerca da <xref:System.Windows.Automation.AutomationElement.RootElement%2A> , è consigliabile provare a ottenere solo gli elementi figlio diretti.</span><span class="sxs-lookup"><span data-stu-id="d08ff-111">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="d08ff-112">Una ricerca di discendenti può scorrere centinaia o addirittura migliaia di elementi, causando probabilmente un overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="d08ff-112">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="d08ff-113">Per ottenere un elemento specifico a un livello inferiore, è consigliabile avviare la ricerca dalla finestra dell'applicazione o da un contenitore a un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="d08ff-113">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="d08ff-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d08ff-114">See also</span></span>

- <span data-ttu-id="d08ff-115">[Esempio di voce di menu InvokePattern e ExpandCollapsePattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d08ff-115">[InvokePattern and ExpandCollapsePattern Menu Item Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="d08ff-116">Ottenere elementi di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d08ff-116">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
- [<span data-ttu-id="d08ff-117">Utilizzare la proprietà AutomationID</span><span class="sxs-lookup"><span data-stu-id="d08ff-117">Use the AutomationID Property</span></span>](use-the-automationid-property.md)
