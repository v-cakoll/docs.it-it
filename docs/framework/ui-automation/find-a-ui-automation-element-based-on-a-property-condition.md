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
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Trovare un elemento di automazione interfaccia utente in base a una proprietà
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.  
  
 Questo argomento contiene codice di esempio che illustra come individuare un elemento all'interno [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] dell'albero in base a una proprietà o a proprietà specifiche.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene specificato un set di condizioni di proprietà che identificano un determinato elemento (o elementi) di interesse nell' <xref:System.Windows.Automation.AutomationElement> albero. Una ricerca di tutti gli elementi corrispondenti viene quindi eseguita con <xref:System.Windows.Automation.AutomationElement.FindAll%2A> il metodo che incorpora una serie di <xref:System.Windows.Automation.AndCondition> operazioni booleane per limitare il numero di elementi corrispondenti.  
  
> [!NOTE]
> Quando si esegue una <xref:System.Windows.Automation.AutomationElement.RootElement%2A>ricerca da, è consigliabile provare a ottenere solo gli elementi figlio diretti. Una ricerca di discendenti può scorrere centinaia o addirittura migliaia di elementi, causando probabilmente un overflow dello stack. Per ottenere un elemento specifico a un livello inferiore, è consigliabile avviare la ricerca dalla finestra dell'applicazione o da un contenitore a un livello inferiore.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempio di voce di menu InvokePattern e ExpandCollapsePattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [Ottenere elementi di automazione interfaccia utente](obtaining-ui-automation-elements.md)
- [Usare la proprietà AutomationID](use-the-automationid-property.md)
