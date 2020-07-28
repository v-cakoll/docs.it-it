---
title: Implementazione del pattern di controllo SelectionItem di automazione interfaccia utente
description: Vedere linee guida e convenzioni per implementare il pattern di controllo SelectionItem in automazione interfaccia utente. Conosce i membri obbligatori per l'interfaccia ISelectionItemProvider.
ms.date: 03/30/2017
helpviewer_keywords:
- Selection Item control pattern
- UI Automation, Selection Item control pattern
- control patterns, Selection Item
ms.assetid: 76b0949a-5b23-4cfc-84cc-154f713e2e12
ms.openlocfilehash: 441417aa370563a9ce8b513be6ca4507b21e1e4a
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163544"
---
# <a name="implementing-the-ui-automation-selectionitem-control-pattern"></a>Implementazione del pattern di controllo SelectionItem di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono presentate le linee guida e le convenzioni per l'implementazione di <xref:System.Windows.Automation.Provider.ISelectionItemProvider>, incluse le informazioni relative a proprietà, metodi ed eventi. Alla fine della panoramica sono elencati collegamenti a ulteriore materiale di riferimento.  
  
 Il pattern di controllo <xref:System.Windows.Automation.SelectionItemPattern> viene usato per supportare i controlli che fungono da singoli elementi figlio selezionabili dei controlli contenitore che implementano <xref:System.Windows.Automation.Provider.ISelectionProvider>. Per esempi di controlli che implementano il pattern di controllo SelectionItem, vedere [mapping dei pattern di controllo per i client di automazione interfaccia utente](control-pattern-mapping-for-ui-automation-clients.md)  
  
<a name="Implementation_Guidelines_and_Conventions"></a>
## <a name="implementation-guidelines-and-conventions"></a>Linee guida e convenzioni di implementazione  
 Quando si implementa il pattern di controllo SelectionItem, tenere presenti le linee guida e le convenzioni seguenti:  
  
- I controlli a selezione singola che gestiscono i controlli figlio che implementano <xref:System.Windows.Automation.Provider.IRawElementProviderFragmentRoot>, ad esempio il dispositivo di scorrimento **Risoluzione schermo** nella finestra di dialogo **Proprietà di visualizzazione** devono implementare <xref:System.Windows.Automation.Provider.ISelectionProvider> e i relativi elementi figlio devono implementare <xref:System.Windows.Automation.Provider.IRawElementProviderFragment> e <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>
## <a name="required-members-for-iselectionitemprovider"></a>Membri obbligatori per ISelectionItemProvider  
 Le proprietà, i metodi e gli eventi seguenti sono obbligatori per l'implementazione di <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.  
  
|Membri obbligatori|Tipo di membro|Note|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Proprietà|Nessuno|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.GetSelection%2A>|Metodo|Nessuno|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Event|Generato quando una selezione in un contenitore ha subito modifiche significative e richiede l'invio di un numero di eventi <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent> e <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent> rispetto a quanto definito mediante la costante <xref:System.Windows.Automation.Provider.AutomationInteropProvider.InvalidateLimit> .|  
  
- Se il risultato di un <xref:System.Windows.Automation.SelectionItemPattern.Select%2A>, <xref:System.Windows.Automation.SelectionItemPattern.AddToSelection%2A>o un <xref:System.Windows.Automation.SelectionItemPattern.RemoveFromSelection%2A> è un singolo elemento selezionato, è necessario generare <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent> . In caso contrario inviare <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>/ <xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent> a seconda dei casi.  
  
<a name="Exceptions"></a>
## <a name="exceptions"></a>Eccezioni  
 I provider devono generare le eccezioni seguenti.  
  
|Tipo di eccezione|Condizione|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Quando vengono tentate le seguenti operazioni:<br /><br /> -   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> viene chiamato in un contenitore a selezione singola dove <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> = `true` e un elemento è già selezionato.<br />-   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.RemoveFromSelection%2A> viene chiamato in un contenitore a selezione multipla dove <xref:System.Windows.Automation.SelectionPattern.IsSelectionRequiredProperty> = `true` ed è selezionato solo un elemento.<br />-   <xref:System.Windows.Automation.Provider.ISelectionItemProvider.AddToSelection%2A> viene chiamato in un contenitore a selezione singola dove <xref:System.Windows.Automation.SelectionPattern.CanSelectMultipleProperty> = `false` e un altro elemento è già selezionato.|  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sui pattern di controllo per l'automazione interfaccia utente](ui-automation-control-patterns-overview.md)
- [Supportare pattern di controllo in un provider di automazione interfaccia utente](support-control-patterns-in-a-ui-automation-provider.md)
- [Pattern di controllo di automazione interfaccia utente per i client](ui-automation-control-patterns-for-clients.md)
- [Implementazione del pattern di controllo Selection di automazione interfaccia utente](implementing-the-ui-automation-selection-control-pattern.md)
- [Panoramica dell'albero di automazione dell'interfaccia utente](ui-automation-tree-overview.md)
- [Utilizzare la memorizzazione nella cache per l'automazione interfaccia utente](use-caching-in-ui-automation.md)
- [Esempio di provider di frammenti](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771502(v=vs.90))
