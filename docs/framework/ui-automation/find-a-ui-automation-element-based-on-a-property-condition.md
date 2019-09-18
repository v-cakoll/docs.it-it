---
title: Trovare un elemento di automazione interfaccia utente in base a una proprietà
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- elements, finding by property conditions
- UI Automation, finding elements by property conditions
ms.assetid: 3acaee5a-6ce8-4c3e-81c8-67e59eb74477
ms.openlocfilehash: 536a71532f02782f9e84bb2bd086af212a77c0da
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043661"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a><span data-ttu-id="d64e8-102">Trovare un elemento di automazione interfaccia utente in base a una proprietà</span><span class="sxs-lookup"><span data-stu-id="d64e8-102">Find a UI Automation Element Based on a Property Condition</span></span>
> [!NOTE]
> <span data-ttu-id="d64e8-103">Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>.</span><span class="sxs-lookup"><span data-stu-id="d64e8-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="d64e8-104">Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="d64e8-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="d64e8-105">Questo argomento contiene codice di esempio che illustra come individuare un elemento all'interno [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] dell'albero in base a una proprietà o a proprietà specifiche.</span><span class="sxs-lookup"><span data-stu-id="d64e8-105">This topic contains example code that shows how to locate an element within the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree based on a specific property or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d64e8-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d64e8-106">Example</span></span>  
 <span data-ttu-id="d64e8-107">Nell'esempio seguente viene specificato un set di condizioni di proprietà che identificano un determinato elemento (o elementi) di interesse nell' <xref:System.Windows.Automation.AutomationElement> albero.</span><span class="sxs-lookup"><span data-stu-id="d64e8-107">In the following example, a set of property conditions are specified that identify a certain element (or elements) of interest in the <xref:System.Windows.Automation.AutomationElement> tree.</span></span> <span data-ttu-id="d64e8-108">Una ricerca di tutti gli elementi corrispondenti viene quindi eseguita con <xref:System.Windows.Automation.AutomationElement.FindAll%2A> il metodo che incorpora una serie di <xref:System.Windows.Automation.AndCondition> operazioni booleane per limitare il numero di elementi corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="d64e8-108">A search for all matching elements is then performed with the <xref:System.Windows.Automation.AutomationElement.FindAll%2A> method that incorporates a series of <xref:System.Windows.Automation.AndCondition> boolean operations to limit the number of matching elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d64e8-109">Quando si esegue una <xref:System.Windows.Automation.AutomationElement.RootElement%2A>ricerca da, è consigliabile provare a ottenere solo gli elementi figlio diretti.</span><span class="sxs-lookup"><span data-stu-id="d64e8-109">When searching from the <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, you should try to obtain only direct children.</span></span> <span data-ttu-id="d64e8-110">Una ricerca di discendenti può scorrere centinaia o addirittura migliaia di elementi, causando probabilmente un overflow dello stack.</span><span class="sxs-lookup"><span data-stu-id="d64e8-110">A search for descendants might iterate through hundreds or even thousands of elements, possibly resulting in a stack overflow.</span></span> <span data-ttu-id="d64e8-111">Per ottenere un elemento specifico a un livello inferiore, è consigliabile avviare la ricerca dalla finestra dell'applicazione o da un contenitore a un livello inferiore.</span><span class="sxs-lookup"><span data-stu-id="d64e8-111">If you are attempting to obtain a specific element at a lower level, you should start your search from the application window or from a container at a lower level.</span></span>  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a><span data-ttu-id="d64e8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d64e8-112">See also</span></span>

- <span data-ttu-id="d64e8-113">[Esempio di voce di menu InvokePattern e ExpandCollapsePattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d64e8-113">[InvokePattern and ExpandCollapsePattern Menu Item Sample](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))</span></span>
- [<span data-ttu-id="d64e8-114">Ottenere elementi di automazione interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="d64e8-114">Obtaining UI Automation Elements</span></span>](obtaining-ui-automation-elements.md)
- [<span data-ttu-id="d64e8-115">Usare la proprietà AutomationID</span><span class="sxs-lookup"><span data-stu-id="d64e8-115">Use the AutomationID Property</span></span>](use-the-automationid-property.md)
