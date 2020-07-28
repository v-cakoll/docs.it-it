---
title: Pattern di controllo di automazione interfaccia utente per i client
description: Leggi una panoramica sui pattern di controllo per i client di automazione interfaccia utente. Usare i pattern di controllo per accedere alle informazioni sull'interfaccia utente (UI).
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, control patterns for clients
- control patterns, UI Automation clients
ms.assetid: 571561d8-5f49-43a9-a054-87735194e013
ms.openlocfilehash: f2def328228a30ace6d0edc0661d6e79f237d6f4
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163877"
---
# <a name="ui-automation-control-patterns-for-clients"></a>Pattern di controllo di automazione interfaccia utente per i client
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questa panoramica vengono presentati i pattern di controllo per i client di automazione interfaccia utente. Sono incluse informazioni su come un client di automazione interfaccia utente può usare i pattern di controllo per accedere alle informazioni relative all' [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)].  
  
 I pattern di controllo rappresentano un metodo di classificazione ed esposizione della funzionalità di un controllo indipendentemente dal tipo o dall'aspetto del controllo stesso. I client di automazione interfaccia utente possono esaminare un <xref:System.Windows.Automation.AutomationElement> per determinare quali pattern di controllo sono supportati e verificare il comportamento del controllo.  
  
 Per un elenco completo dei pattern di controllo, vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
<a name="uiautomation_getting_control_patterns"></a>
## <a name="getting-control-patterns"></a>Recupero dei pattern di controllo  
 I client possono ottenere pattern di controllo da <xref:System.Windows.Automation.AutomationElement> con una chiamata a <xref:System.Windows.Automation.AutomationElement.GetCachedPattern%2A?displayProperty=nameWithType> o a <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A?displayProperty=nameWithType>.  
  
 I client possono usare il metodo <xref:System.Windows.Automation.AutomationElement.GetSupportedPatterns%2A> o una singola proprietà `IsPatternAvailable` (ad esempio, <xref:System.Windows.Automation.AutomationElement.IsTextPatternAvailableProperty>) per determinare se un pattern o un gruppo di pattern è supportato in <xref:System.Windows.Automation.AutomationElement>. È tuttavia più efficiente tentare di ottenere il pattern di controllo e verificare la presenza di un riferimento `null` anziché controllare le proprietà supportate e recuperare il pattern di controllo, poiché ciò comporta un numero inferiore di chiamate tra processi.  
  
 Nell'esempio seguente viene illustrato come ottenere un <xref:System.Windows.Automation.TextPattern> pattern di controllo da <xref:System.Windows.Automation.AutomationElement>.  
  
 [!code-csharp[UIATextPattern_snip#1037](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIATextPattern_snip/CSharp/SearchWindow.cs#1037)]  
  
<a name="uiautomation_properties_on_control_patterns"></a>
## <a name="retrieving-properties-on-control-patterns"></a>Recupero delle proprietà per i pattern di controllo  
 I client possono recuperare i valori delle proprietà dei pattern di controllo con una chiamata a <xref:System.Windows.Automation.AutomationElement.GetCachedPropertyValue%2A?displayProperty=nameWithType> o a <xref:System.Windows.Automation.AutomationElement.GetCurrentPropertyValue%2A?displayProperty=nameWithType> e con il cast dell'oggetto restituito a un tipo appropriato. Per altre informazioni sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] proprietà, vedere [proprietà di automazione interfaccia utente per i client](ui-automation-properties-for-clients.md).  
  
 Oltre ai `GetPropertyValue` metodi, i valori delle proprietà possono essere recuperati tramite le funzioni di accesso Common Language Runtime (CLR) per accedere alle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] proprietà di un modello.  
  
<a name="uiautomation_with_variable_patterns"></a>
## <a name="controls-with-variable-patterns"></a>Controlli con pattern variabili  
 Alcuni tipi di controllo supportano pattern diversi a seconda dello stato del controllo o del modo in cui questo viene usato. Esempi di controlli che possono avere pattern variabili sono le visualizzazioni elenco (anteprime, riquadri, icone, elenchi, dettagli), i grafici di Microsoft Excel (a torta, a linee, a barre, il valore della cella con una formula), l'area documento di Microsoft Word (normale, layout Web, struttura, layout di stampa, anteprima di stampa) e le interfacce Media Player Microsoft Windows.  
  
 I controlli che implementano i tipi di controllo personalizzati possono disporre di qualsiasi set di pattern di controllo necessario per la rappresentazione delle funzionalità dei controlli stessi.  
  
## <a name="see-also"></a>Vedere anche

- [Pattern di controllo per automazione interfaccia utente](ui-automation-control-patterns.md)
- [Pattern di testo per l'automazione interfaccia utente](ui-automation-text-pattern.md)
- [Richiamare un controllo utilizzando automazione interfaccia utente](invoke-a-control-using-ui-automation.md)
- [Ottenere lo stato di attivazione/disattivazione di una casella di controllo utilizzando l'automazione interfaccia utente](get-the-toggle-state-of-a-check-box-using-ui-automation.md)
- [Mapping dei pattern di controllo per i client di automazione interfaccia utente](control-pattern-mapping-for-ui-automation-clients.md)
- [Esempio di testo di inserimento TextPattern](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText)
- [Esempio di ricerca e selezione di TextPattern](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/FindText)
- [Esempio InvokePattern, ExpandCollapsePattern e TogglePattern](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InvokePattern)
