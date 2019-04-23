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
ms.openlocfilehash: a5e775c69a4dd520d8148bfc790cc00428d9d15e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175513"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Trovare un elemento di automazione interfaccia utente in base a una proprietà
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento contiene codice di esempio che illustra come individuare un elemento all'interno di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] albero basato su una proprietà specifica o proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, un set di condizioni di proprietà vengono specificati che identificano un determinato elemento o gli elementi di interesse nel <xref:System.Windows.Automation.AutomationElement> struttura ad albero. Viene quindi eseguita una ricerca per tutti gli elementi corrispondenti con il <xref:System.Windows.Automation.AutomationElement.FindAll%2A> metodo che include una serie di <xref:System.Windows.Automation.AndCondition> operazioni booleane per limitare il numero di elementi corrispondenti.  
  
> [!NOTE]
>  Durante la ricerca dal <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, è consigliabile provare a ottenere solo elementi figlio diretti. Una ricerca dei discendenti può scorrere centinaia o anche migliaia di elementi, determinando un overflow dello stack. Per ottenere un elemento specifico a un livello inferiore, è consigliabile avviare la ricerca dalla finestra dell'applicazione o da un contenitore a un livello inferiore.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempio di elemento Menu ExpandCollapsePattern e InvokePattern](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771636(v=vs.90))
- [Ottenere elementi di automazione interfaccia utente](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)
- [Usare la proprietà AutomationID](../../../docs/framework/ui-automation/use-the-automationid-property.md)
