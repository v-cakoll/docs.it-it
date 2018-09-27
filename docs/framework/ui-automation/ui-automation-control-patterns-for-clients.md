---
title: Pattern di controllo di automazione interfaccia utente per i client
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control patterns for clients
- control patterns, UI Automation clients
ms.assetid: 571561d8-5f49-43a9-a054-87735194e013
author: Xansky
ms.author: mhopkins
ms.openlocfilehash: 6e10b0e38e80bad1f322e32324db862691432b8e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2018
ms.locfileid: "47236235"
---
# <a name="ui-automation-control-patterns-for-clients"></a>Pattern di controllo di automazione interfaccia utente per i client
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questa panoramica vengono presentati i pattern di controllo per i client di automazione interfaccia utente. Sono incluse informazioni su come un client di automazione interfaccia utente può usare i pattern di controllo per accedere alle informazioni relative all' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].  
  
 I pattern di controllo rappresentano un metodo di classificazione ed esposizione della funzionalità di un controllo indipendentemente dal tipo o dall'aspetto del controllo stesso. I client di automazione interfaccia utente possono esaminare un <xref:System.Windows.Automation.AutomationElement> per determinare quali pattern di controllo sono supportati e verificare il comportamento del controllo.  
  
 Per un elenco completo dei pattern di controllo, vedere [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
<a name="uiautomation_getting_control_patterns"></a>   
## <a name="getting-control-patterns"></a>Recupero dei pattern di controllo  
 I client possono ottenere pattern di controllo da <xref:System.Windows.Automation.AutomationElement> con una chiamata a <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> o a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType>.  
  
 I client possono usare il metodo <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> o una singola proprietà `IsPatternAvailable` (ad esempio, <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>) per determinare se un pattern o un gruppo di pattern è supportato in <xref:System.Windows.Automation.AutomationElement>. È tuttavia più efficiente tentare di ottenere il pattern di controllo e verificare la presenza di un riferimento `null` anziché controllare le proprietà supportate e recuperare il pattern di controllo, poiché ciò comporta un numero inferiore di chiamate tra processi.  
  
 Nell'esempio seguente viene illustrato come ottenere un <xref:System.Windows.Automation.TextPattern> pattern di controllo da <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIATextPattern_snip#1037](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#1037)]  
  
<a name="uiautomation_properties_on_control_patterns"></a>   
## <a name="retrieving-properties-on-control-patterns"></a>Recupero delle proprietà per i pattern di controllo  
 I client possono recuperare i valori delle proprietà dei pattern di controllo con una chiamata a <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> o a <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> e con il cast dell'oggetto restituito a un tipo appropriato. Per ulteriori informazioni sul [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] proprietà, vedere [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
 Oltre che con i metodi `GetPropertyValue` , è possibile recuperare i valori delle proprietà tramite le funzioni di accesso [!INCLUDE[TLA#tla_clr](../../../includes/tlasharptla-clr-md.md)] per l'accesso alle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] di un pattern.  
  
<a name="uiautomation_with_variable_patterns"></a>   
## <a name="controls-with-variable-patterns"></a>Controlli con pattern variabili  
 Alcuni tipi di controllo supportano pattern diversi a seconda dello stato del controllo o del modo in cui questo viene usato. Esempi di controlli che possono avere pattern variabili sono le visualizzazioni elenco (anteprime, riquadri, icone, elenchi, dettagli), grafici [!INCLUDE[TLA#tla_xl](../../../includes/tlasharptla-xl-md.md)] (a torta, a righe, a barre, valore della cella con una formula), le aree documento di [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)](Normale, Layout Web, Struttura, Layout di stampa, Anteprima di stampa) e le interfacce personalizzate di [!INCLUDE[TLA#tla_wmp](../../../includes/tlasharptla-wmp-md.md)] .  
  
 I controlli che implementano i tipi di controllo personalizzati possono disporre di qualsiasi set di pattern di controllo necessario per la rappresentazione delle funzionalità dei controlli stessi.  
  
## <a name="see-also"></a>Vedere anche  
 [Pattern di controllo per automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-control-patterns.md)  
 [Pattern di testo per l'automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-text-pattern.md)  
 [Richiamare un controllo usando l'automazione interfaccia utente](../../../docs/framework/ui-automation/invoke-a-control-using-ui-automation.md)  
 [Ottenere lo stato di attivo/non attivo di una casella di controllo usando l'automazione interfaccia utente](../../../docs/framework/ui-automation/get-the-toggle-state-of-a-check-box-using-ui-automation.md)  
 [Mapping dei pattern di controllo per client di automazione interfaccia utente](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md)  
 [TextPattern Insert Text Sample](https://msdn.microsoft.com/library/67353f93-7ee2-42f2-ab76-5c078cf6ca16)  
 [Esempio di selezione e ricerca di TextPattern](https://msdn.microsoft.com/library/0a3bca57-8b72-489d-a57c-da85b7a22c7f)  
 [Esempio di elemento Menu ExpandCollapsePattern e InvokePattern](https://msdn.microsoft.com/library/b7fa141c-e2d1-4da2-a27f-81a7d1172210)
