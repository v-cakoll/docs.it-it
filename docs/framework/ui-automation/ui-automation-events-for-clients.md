---
title: Eventi di automazione interfaccia utente per i client
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: f295bbf44d6272879e8ea8e74c435d206b7af913
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2018
ms.locfileid: "45585759"
---
# <a name="ui-automation-events-for-clients"></a>Eventi di automazione interfaccia utente per i client
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione dell'interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Questo argomento viene descritto come [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] gli eventi vengono usati dai client di automazione interfaccia utente.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] consente ai client di sottoscrivere gli eventi di interesse. Questa funzionalità migliora le prestazioni eliminando la necessità di esaminare continuamente tutti il [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] elementi nel sistema per vedere se tutte le informazioni, struttura o lo stato è stato modificato.  
  
 Una maggiore efficienza è ottenuta anche grazie alla possibilità di restare in ascolto di eventi solo in un ambito definito. Ad esempio, un client può restare in ascolto di eventi di modifica dello stato attivo in tutti i [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gli elementi dell'albero, o in un solo elemento e i relativi discendenti.  
  
> [!NOTE]
>  Non presupporre che tutti i possibili eventi vengono generati da un [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] provider. Ad esempio, non tutte le modifiche alle proprietà provocano eventi da generare dai provider proxy standard per [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] e [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controlli.  
  
 Per ulteriori informazioni sugli [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gli eventi, vedere [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>Sottoscrizione di eventi  
 Le applicazioni client sottoscrivono eventi di una particolare tipologia registrando un gestore eventi, con uno dei metodi seguenti.  
  
|Metodo|Tipo di evento|Tipo argomenti evento|Tipo di delegato|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Modifica dello stato attivo|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Modifica proprietà|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Modifica struttura|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Tutti gli altri eventi, identificati da un <xref:System.Windows.Automation.AutomationEvent>|<xref:System.Windows.Automation.AutomationEventArgs> o <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Prima di chiamare il metodo, è necessario creare un metodo delegato per gestire l'evento. Se si preferisce, è possibile gestire tipologie diverse di eventi con un solo metodo e passare questo metodo in più chiamate a uno dei metodi della tabella. Ad esempio, un singolo <xref:System.Windows.Automation.AutomationEventHandler> da impostare per gestire svariati eventi in modo diverso in base al <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A>.  
  
> [!NOTE]
>  Per elaborare eventi di chiusura di finestra, il cast del tipo di argomento passato al gestore dell'evento come <xref:System.Windows.Automation.WindowClosedEventArgs>. Poiché il [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] (elemento) per la finestra non è più valido, non è possibile usare il `sender` parametro per recuperare le informazioni; usare <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A> invece.  
  
> [!CAUTION]
>  Se l'applicazione può ricevere eventi dalla propria [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)], non usare l'applicazione [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] thread per sottoscrivere gli eventi o per annullare la sottoscrizione. perché potrebbe verificarsi un comportamento imprevisto. Per altre informazioni, vedere [UI Automation Threading Issues](../../../docs/framework/ui-automation/ui-automation-threading-issues.md).  
  
 Al momento della chiusura, o quando [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] eventi non sono più interessanti per l'applicazione, i client di automazione interfaccia utente devono chiamare uno dei metodi seguenti.  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Annulla la registrazione di un gestore eventi che è stato registrato usando <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Annulla la registrazione di un gestore eventi che è stato registrato usando <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Annulla la registrazione di un gestore eventi che è stato registrato usando <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Annulla la registrazione di tutti i gestori eventi registrati.|  
  
 Ad esempio di codice, vedere [sottoscrivere gli eventi di automazione interfaccia utente](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Sottoscrivere gli eventi di automazione interfaccia utente](../../../docs/framework/ui-automation/subscribe-to-ui-automation-events.md)  
 [Panoramica degli eventi di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-events-overview.md)  
 [Panoramica delle proprietà di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-properties-overview.md)  
 [Esempio di TrackFocus](https://msdn.microsoft.com/library/4a91c0af-6bb5-4d38-a743-cf136f268fc9)
