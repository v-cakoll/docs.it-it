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
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: da455b10425c9e0b20a644679358dde469ed92e5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400757"
---
# <a name="find-a-ui-automation-element-based-on-a-property-condition"></a>Trovare un elemento di automazione interfaccia utente in base a una proprietà
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento contiene codice di esempio che illustra come individuare un elemento all'interno di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] struttura ad albero in base a una o più proprietà specifiche.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente, un set di condizioni di proprietà specificato che identifica un determinato elemento o gli elementi di interesse nel <xref:System.Windows.Automation.AutomationElement> struttura ad albero. Viene quindi eseguita una ricerca per tutti gli elementi corrispondenti con il <xref:System.Windows.Automation.AutomationElement.FindAll%2A> metodo che incorpora una serie di <xref:System.Windows.Automation.AndCondition> operazioni booleane per limitare il numero di elementi corrispondenti.  
  
> [!NOTE]
>  Durante la ricerca dal <xref:System.Windows.Automation.AutomationElement.RootElement%2A>, è consigliabile provare a ottenere solo elementi figlio diretti. Una ricerca dei discendenti può scorrere centinaia o migliaia di elementi, probabilmente un overflow dello stack. Per ottenere un elemento specifico a un livello inferiore, è consigliabile avviare la ricerca dalla finestra dell'applicazione o da un contenitore a un livello inferiore.  
  
 [!code-csharp[InvokePatternApp#1100](../../../samples/snippets/csharp/VS_Snippets_Wpf/InvokePatternApp/CSharp/InvokePatternApp.cs#1100)]
 [!code-vb[InvokePatternApp#1100](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InvokePatternApp/VisualBasic/Client.vb#1100)]  
  
## <a name="see-also"></a>Vedere anche  
 [Esempio di elemento di Menu ExpandCollapsePattern e InvokePattern](http://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)  
 [Ottenere elementi di automazione interfaccia utente](../../../docs/framework/ui-automation/obtaining-ui-automation-elements.md)  
 [Usare la proprietà AutomationID](../../../docs/framework/ui-automation/use-the-automationid-property.md)
