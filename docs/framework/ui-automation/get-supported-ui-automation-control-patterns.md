---
title: Ottenere pattern di controllo supportati per automazione interfaccia utente
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- control patterns, getting
- UI Automation, getting control patterns
- getting, control patterns
ms.assetid: 006c54c9-50bf-48d9-a855-9d62eb95603a
ms.openlocfilehash: 7b194d9430f27fb85723a91f5786ed11a60bfa85
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040987"
---
# <a name="get-supported-ui-automation-control-patterns"></a>Ottenere pattern di controllo supportati per automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.  
  
 In questo argomento viene illustrato come recuperare oggetti del pattern di controllo dagli elementi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].  
  
### <a name="obtain-all-control-patterns"></a>Ottenere tutti i pattern di controllo  
  
1. Ottenere <xref:System.Windows.Automation.AutomationElement> contenente i pattern di controllo interessati.  
  
2. Chiamare <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> per ottenere tutti i pattern di controllo dall'elemento.  
  
> [!CAUTION]
> È consigliabile che un client non usi <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A>. Le prestazioni possono venire influenzate in modo significativo poiché questo metodo chiama <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> internamente per ogni pattern di controllo esistente. Se possibile, un client deve chiamare <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> per i principali pattern di interesse.  
  
### <a name="obtain-a-specific-control-pattern"></a>Ottenere un pattern di controllo specifico  
  
1. Ottenere <xref:System.Windows.Automation.AutomationElement> contenente i pattern di controllo interessati.  
  
2. Chiamare <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> o <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> per eseguire query per un pattern specifico. Questi metodi sono simili, ma se il pattern non viene trovato, <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> genera un'eccezione e <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> restituisce `false`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene recuperato un <xref:System.Windows.Automation.AutomationElement> per una voce di elenco e viene ottenuto un <xref:System.Windows.Automation.SelectionItemPattern> da tale elemento.  
  
 [!code-csharp[UIAClient_snip#103](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#103)]
 [!code-vb[UIAClient_snip#103](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#103)]  
  
## <a name="see-also"></a>Vedere anche

- [Pattern di controllo di automazione interfaccia utente per i client](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
