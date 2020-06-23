---
title: Eventi di automazione interfaccia utente per i client
description: Informazioni su come gli eventi di automazione interfaccia utente Microsoft vengono usati dai client di automazione interfaccia utente in .NET. Automazione interfaccia utente consente ai client di sottoscrivere gli eventi di interesse.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
ms.openlocfilehash: 84568cf228a30535ec603cdad5bddbfd5697be0a
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903740"
---
# <a name="ui-automation-events-for-clients"></a>Eventi di automazione interfaccia utente per i client
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 Questo argomento descrive come gli eventi di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] vengono usati dai client di automazione interfaccia utente.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] consente ai client di sottoscrivere gli eventi di interesse. Questa funzionalità migliora le prestazioni eliminando la necessità di esaminare continuamente tutti gli elementi dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] nel sistema per verificare se sono state apportate modifiche alle informazioni, la struttura o lo stato.  
  
 Una maggiore efficienza è ottenuta anche grazie alla possibilità di restare in ascolto di eventi solo in un ambito definito. Un client, ad esempio, può restare in ascolto di eventi di modifica dello stato attivo per tutti gli elementi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] dell'albero o solo per un elemento e i relativi discendenti.  
  
> [!NOTE]
> Non presupporre che tutti i possibili eventi vengano generati da un provider di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]. Non tutte le modifiche alle proprietà, ad esempio, determinano la generazione di eventi da parte dei provider proxy standard per i controlli Windows Forms e Win32.  
  
 Per una visualizzazione più ampia degli [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] eventi, vedere [Panoramica degli eventi di automazione interfaccia utente](ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>
## <a name="subscribing-to-events"></a>Sottoscrizione di eventi  
 Le applicazioni client sottoscrivono eventi di una particolare tipologia registrando un gestore eventi, con uno dei metodi seguenti.  
  
|Metodo|Tipo evento|Tipo argomenti evento|Tipo di delegato|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Modifica dello stato attivo|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Modifica proprietà|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Modifica struttura|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Tutti gli altri eventi, identificati da <xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> o <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Prima di chiamare il metodo, è necessario creare un metodo delegato per gestire l'evento. Se si preferisce, è possibile gestire tipologie diverse di eventi con un solo metodo e passare questo metodo in più chiamate a uno dei metodi della tabella. Ad esempio, è possibile configurare un singolo <xref:System.Windows.Automation.AutomationEventHandler> per gestire svariati eventi in modo diverso in base all'<xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.  
  
> [!NOTE]
> Per elaborare eventi di chiusura di finestra, eseguire il cast del tipo di argomento passato al gestore eventi come <xref:System.Windows.Automation.WindowClosedEventArgs>. Poiché l'elemento di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per la finestra non è più valido, non è possibile usare il parametro `sender` per recuperare le informazioni. Usare invece <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A>.  
  
> [!CAUTION]
> Se l'applicazione può ricevere eventi dalla propria [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], non usare il thread dell'[!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] dell'applicazione per sottoscrivere gli eventi o per annullare una sottoscrizione, perché potrebbe verificarsi un comportamento imprevisto. Per altre informazioni, vedere [UI Automation Threading Issues](ui-automation-threading-issues.md).  
  
 All'arresto o quando gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] non interessano più l'applicazione, i client di automazione interfaccia utente devono chiamare uno dei metodi seguenti.  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Annulla la registrazione di un gestore eventi che era stato registrato usando <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Annulla la registrazione di un gestore eventi che era stato registrato usando <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Annulla la registrazione di un gestore eventi che era stato registrato usando <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Annulla la registrazione di tutti i gestori eventi registrati.|  
  
 Per un esempio di codice, vedere [sottoscrivere eventi di automazione interfaccia utente](subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>Vedere anche

- [Sottoscrivere gli eventi di automazione interfaccia utente](subscribe-to-ui-automation-events.md)
- [Cenni preliminari sugli eventi di automazione interfaccia utente](ui-automation-events-overview.md)
- [Cenni preliminari sulle proprietà di automazione interfaccia utente](ui-automation-properties-overview.md)
- [Esempio TrackFocus](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/FocusTracker)
