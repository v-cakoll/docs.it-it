---
title: Supporto per automazione interfaccia utente del tipo di controllo List
description: Ottenere informazioni sul supporto di automazione interfaccia utente per il tipo di controllo elenco. Informazioni sulla struttura ad albero, le proprietà, i pattern di controllo e gli eventi di richiesti.
ms.date: 03/30/2017
helpviewer_keywords:
- control types, List
- List control type
- UI Automation, List control type
ms.assetid: 0e959fcb-50f2-413b-948d-7167d279bc11
ms.openlocfilehash: 01827250ac216dbcb57a8a139637e7c48d59566d
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166077"
---
# <a name="ui-automation-support-for-the-list-control-type"></a>Supporto per automazione interfaccia utente del tipo di controllo List
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono fornite informazioni sul supporto di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo elenco. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]un tipo di controllo è un set di condizioni che un controllo deve soddisfare per usare la proprietà <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Le condizioni includono linee guida specifiche per la struttura ad albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i valori delle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e i pattern di controllo.  
  
 Il tipo di controllo elenco consente di organizzare uno o più gruppi di elementi permettendo a un utente di selezionare uno o più elementi. Il tipo di controllo elenco prevede una restrizione ampia sui tipi di elementi figlio che può contenere. I provider di automazione interfaccia utente sono quindi in grado di supportare un elemento noto per i contenitori di selezione.  
  
 I [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisiti nelle sezioni riportate di seguito si applicano a tutti i controlli che implementano il tipo di controllo elenco, sia [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Win32 che Windows Forms. I controlli contenitore elenco sono un esempio di controlli che implementano il tipo di controllo elenco.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>
## <a name="required-ui-automation-tree-structure"></a>Struttura ad albero di automazione interfaccia utente obbligatoria  
 Nella tabella seguente vengono illustrate due visualizzazioni dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relativamente ai controlli elenco e viene descritto il possibile contenuto di ogni visualizzazione. Nella visualizzazione controlli sono contenuti solo elementi controllo e nella visualizzazione contenuto vengono rimosse le informazioni ridondanti dell'albero. Ad esempio, un controllo testo usato come etichetta di una casella combinata sarà esposto come `ComboBox NameProperty`. Poiché il controllo testo è già esposto in questo modo tramite la visualizzazione controlli, non è necessario che venga esposto due volte e, pertanto, viene rimosso dalla visualizzazione contenuto. Per altre informazioni sull'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Visualizzazione controlli|Visualizzazione contenuto|  
|------------------|------------------|  
|Contiene elementi che corrispondono ai controlli.|Rimuove le informazioni ridondanti dell'albero in modo che i prodotti di assistive technology dispongano di un insieme ridotto di informazioni significative per l'utente finale.|  
|Elenco<br /><br /> -DataItem (0 o più)<br />-ListItem (0 o più)<br />-Group (0 o più)<br />-ScrollBar (0, 1 o 2)|Elenco<br /><br /> -DataItem (0 o più)<br />-ListItem (0 o più)<br />-Group (0 o più)|  
  
 La visualizzazione controlli per un controllo che implementa il tipo di controllo elenco (ad esempio un controllo elenco) contiene:  
  
- Zero o più elementi nel controllo elenco (gli elementi possono essere basati sui tipi di controllo elemento elenco o elemento dati).
  
- Zero o più controlli gruppo in un controllo elenco.
  
- Zero, uno o due controlli barra di scorrimento.
  
La visualizzazione contenuto di un controllo che implementa il tipo di controllo elenco (ad esempio un controllo elenco) contiene:  
  
- Zero o più elementi nel controllo elenco (gli elementi possono essere basati sui tipi di controllo elemento elenco o elemento dati).
  
- Zero o più gruppi nel controllo elenco.

Un controllo elenco non deve contenere elementi con una relazione gerarchica diversa dal raggruppamento. Se gli elementi hanno figli nell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , il contenitore elenco deve essere basato sul tipo di controllo Tree.  
  
 Gli elementi selezionabili nel controllo elenco sono disponibili dai discendenti nell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] del controllo elenco. Tutti gli elementi nel controllo elenco devono appartenere allo stesso gruppo di selezione. Gli elementi selezionabili nell'elenco devono essere esposti come tipi di controllo ListItem (anziché DataItem).  
  
<a name="Required_UI_Automation_Properties"></a>
## <a name="required-ui-automation-properties"></a>Proprietà di automazione interfaccia utente obbligatorie  
 La tabella seguente elenca le proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il cui valore o la cui definizione è particolarmente rilevante per i controlli elenco. Per altre informazioni sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] proprietà, vedere [proprietà di automazione interfaccia utente per i client](ui-automation-properties-for-clients.md).  
  
|Proprietà di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valore|Note|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vedere le note.|Il valore di questa proprietà deve essere univoco in tutti i controlli in un'applicazione.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vedere le note.|Il rettangolo più esterno che contiene l'intero controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vedere le note.|Se l'elenco ha un punto selezionabile, ovvero un punto su cui è possibile fare clic affinché l'elenco assuma lo stato attivo, tale punto deve essere esposto tramite questa proprietà.<br /><br /> Se il valore della `IsOffScreen` proprietà è true, <xref:System.Windows.Automation.NoClickablePointException> verrà generato l'oggetto.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vedere le note.|Se il controllo può ricevere lo stato attivo, deve supportare questa proprietà.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vedere le note.|Il valore della proprietà Name di un controllo elenco deve fornire la categoria di opzioni da cui l'utente effettua la selezione. Questa proprietà deriva in genere il nome da un'etichetta di testo statico. Se non è presente alcuna etichetta di testo statico, lo sviluppatore dell'applicazione deve esporre un valore per la proprietà Name.<br /><br /> L'unico caso in cui questa proprietà non è obbligatoria per i controlli elenco è quando si usa il controllo all'interno del sottoalbero di un altro controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vedere le note.|Se è presente un'etichetta di testo statico, questa proprietà deve esporre un riferimento a tale controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Elenco|Questo valore è uguale per tutti i framework dell'interfaccia utente.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"elenco"|Stringa localizzata corrispondente al tipo di controllo elenco.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Il controllo elenco è sempre incluso nella visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Il controllo elenco è sempre incluso nella visualizzazione controlli dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|True|Se il contenitore può accettare input da tastiera, il valore di questa proprietà deve essere True.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Vedere le note.|Il testo della Guida per i controlli elenco deve illustrare il motivo per cui viene chiesto all'utente di effettuare una selezione da un elenco di opzioni. Ad esempio, "La selezione di un elemento dall'elenco consente di impostare la risoluzione per il monitor".|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>
## <a name="required-ui-automation-control-patterns-and-properties"></a>Pattern di controllo e proprietà obbligatori per l'automazione interfaccia utente  
 La tabella seguente elenca i pattern di controllo per l' [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati dai controlli elenco. Per altre informazioni sui pattern di controllo, vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Pattern di controllo/proprietà del pattern|Supporto/valore|Note|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Richiesto|Tutti i controlli che supportano il tipo di controllo elenco devono implementare `ISelectionProvider` quando viene gestito uno stato di selezione tra gli elementi nel controllo. Se gli elementi all'interno del contenitore non sono selezionabili, usare il tipo di controllo Group.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|Dipende da|Nei controlli elenco non è necessario che un elemento sia sempre selezionato.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Dipende da|I controlli elenco possono essere contenitori per una o più selezioni.|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Dipende da|Implementare questo pattern di controllo se gli elementi nel contenitore sono scorrevoli.|  
|<xref:System.Windows.Automation.Provider.IGridProvider>|Dipende da|Implementare questo pattern quando è necessario rendere disponibile lo spostamento nella griglia elemento per elemento.|  
|<xref:System.Windows.Automation.Provider.IMultipleViewProvider>|Dipende da|Implementare questo pattern di controllo se il controllo può supportare più visualizzazioni degli elementi nel contenitore.|  
|<xref:System.Windows.Automation.Provider.ITableProvider>|Mai|`ITableProvider` non è mai supportato per il tipo di controllo elenco. Se il controllo deve supportare questo pattern di controllo, deve essere basato sul tipo del controllo DataGrid.|  
  
<a name="Required_UI_Automation_Events"></a>
## <a name="required-ui-automation-events"></a>Eventi di automazione interfaccia utente obbligatori  
 La tabella seguente elenca gli eventi dell' [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli elenco. Per altre informazioni sugli eventi, vedere [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Supporto/valore|Note|  
|---------------------------------------------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Dipende da|Nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent>|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.MultipleViewPatternIdentifiers.CurrentViewProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> .|Dipende da|Nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Richiesto|Nessuno|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.ControlType.List>
- [Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente](ui-automation-control-types-overview.md)
- [Cenni preliminari su automazione interfaccia utente](ui-automation-overview.md)
