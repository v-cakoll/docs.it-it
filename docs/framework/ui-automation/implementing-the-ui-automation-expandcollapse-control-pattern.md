---
title: Implementazione del pattern di controllo ExpandCollapse di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, ExpandCollapse control pattern
- ExpandCollapse control pattern
- control patterns, ExpandCollapse
ms.assetid: 1dbabb8c-0d68-47c1-a35e-1c01cb01af26
ms.openlocfilehash: ff07f5264ccb3ec699e3676a2e9ba64443b2875f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211660"
---
# <a name="implementing-the-ui-automation-expandcollapse-control-pattern"></a>Implementazione del pattern di controllo ExpandCollapse di automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>, incluse le informazioni relative a proprietà, metodi ed eventi. Alla fine della panoramica sono elencati collegamenti a ulteriore materiale di riferimento.  
  
 Il pattern di controllo <xref:System.Windows.Automation.ExpandCollapsePattern> è usato per supportare i controlli in grado di espandersi visivamente per visualizzare una maggiore quantità di contenuto e di comprimersi per nascondere il contenuto stesso. Per esempi di controlli che implementano questo pattern di controllo, vedere [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo ExpandCollapse, tenere presenti le linee guida e le convenzioni seguenti:  
  
-   I controlli di aggregazione, compilati con oggetti figlio che forniscono all'interfaccia utente funzionalità di espansione/compressione, devono supportare il pattern di controllo <xref:System.Windows.Automation.ExpandCollapsePattern> , contrariamente ai relativi elementi figlio. Ad esempio, un controllo casella combinata viene compilato con una combinazione di controlli casella di riepilogo, pulsante e casella di modifica, ma solo la casella combinata padre deve supportare il pattern di controllo <xref:System.Windows.Automation.ExpandCollapsePattern>.  
  
    > [!NOTE]
    >  Un'eccezione è costituita dal controllo menu, che è un'aggregazione di singoli oggetti MenuItem. Gli oggetti MenuItem possono supportare il pattern di controllo <xref:System.Windows.Automation.ExpandCollapsePattern> , contrariamente al controllo menu padre. Un'eccezione analoga si applica ai controlli Tree e TreeItem.  
  
-   Quando <xref:System.Windows.Automation.ExpandCollapseState> di un controllo è impostato su <xref:System.Windows.Automation.ExpandCollapseState.LeafNode>, le funzionalità <xref:System.Windows.Automation.ExpandCollapsePattern> per il controllo non sono attive e l'unica informazione che è possibile ottenere mediante questo pattern di controllo è <xref:System.Windows.Automation.ExpandCollapseState>. Se successivamente vengono aggiunti oggetti figlio, <xref:System.Windows.Automation.ExpandCollapseState> cambia e la funzionalità <xref:System.Windows.Automation.ExpandCollapsePattern> viene attivata.  
  
-   <xref:System.Windows.Automation.ExpandCollapseState> si intende la visibilità degli oggetti figlio diretti di sola lettura. non fa riferimento alla visibilità di tutti i discendenti.  
  
-   La funzionalità di espansione e compressione è specifica del controllo. Di seguito sono riportati alcuni esempi di questo comportamento.  
  
    -   Il menu personale di Office può essere un MenuItem a tre stati (<xref:System.Windows.Automation.ExpandCollapseState.Expanded>, <xref:System.Windows.Automation.ExpandCollapseState.Collapsed> e <xref:System.Windows.Automation.ExpandCollapseState.PartiallyExpanded>) dove il controllo specifica lo stato da adottare quando si verifica una chiamata a <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> o a <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> .  
  
    -   Una chiamata a <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> per un controllo TreeItem può visualizzare tutti i discendenti o solo elementi figlio diretti.  
  
    -   Se la chiamata a <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> o a <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> per un controllo mantiene lo stato dei relativi discendenti, deve essere inviato un evento di modifica della visibilità, non un evento di modifica stato. Se il controllo padre non mantiene lo stato dei relativi discendenti quando viene compresso, il controllo può eliminare tutti i discendenti non più visibili e generare un evento di eliminazione permanente oppure può modificare <xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A> per ogni discendente e generare un evento di modifica della visibilità.  
  
-   Per garantire lo spostamento, è consigliabile che un oggetto si trovi nell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] (con stato di visibilità appropriato) indipendentemente dallo stato <xref:System.Windows.Automation.ExpandCollapseState>dell'elemento padre. Se i discendenti vengono generati su richiesta, possono essere visualizzati nell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] solo dopo essere stati visualizzati per la prima volta o solo quando sono visibili.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-iexpandcollapseprovider"></a>Membri obbligatori per IExpandCollapseProvider  
 Le proprietà e i metodi seguenti sono obbligatori per l'implementazione di <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>.  
  
|Membri obbligatori|Tipo di membro|Note|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider.ExpandCollapseState%2A>|Proprietà|nessuno|  
|<xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A>|Metodo|nessuno|  
|<xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A>|Metodo|nessuno|  
|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|event|A questo controllo non sono associati eventi; usare questo delegato generico.|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Eccezioni  
 I provider devono generare le eccezioni seguenti.  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Viene eseguita una chiamata a <xref:System.Windows.Automation.ExpandCollapsePattern.Expand%2A> o a <xref:System.Windows.Automation.ExpandCollapsePattern.Collapse%2A> quando <xref:System.Windows.Automation.ExpandCollapseState> = <xref:System.Windows.Automation.ExpandCollapseState.LeafNode>.|  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui pattern di controllo per l'automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Supportare pattern di controllo in un provider di automazione interfaccia utente](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Pattern di controllo di automazione interfaccia utente per i client](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Navigare tra gli elementi di automazione interfaccia utente utilizzando TreeWalker](../../../docs/framework/ui-automation/navigate-among-ui-automation-elements-with-treewalker.md)
- [Panoramica dell'albero di automazione dell'interfaccia utente](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
