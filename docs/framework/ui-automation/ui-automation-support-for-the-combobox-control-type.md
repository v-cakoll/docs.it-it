---
title: Supporto di automazione interfaccia utente per il tipo di controllo ComboBox
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Combo Box
- UI Automation, Combo Box control type
- ComboBox controls
ms.assetid: bb321126-4770-41da-983a-67b7b89d45dd
ms.openlocfilehash: 45632529c9c263f1ae8d17768fbab6b34a10ebeb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69914144"
---
# <a name="ui-automation-support-for-the-combobox-control-type"></a>Supporto di automazione interfaccia utente per il tipo di controllo ComboBox
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.  
  
 In questo argomento vengono fornite informazioni sul supporto di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo ComboBox. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]un tipo di controllo è un set di condizioni che un controllo deve soddisfare per usare la proprietà <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Le condizioni includono linee guida specifiche per la struttura ad albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i valori delle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i pattern di controllo e gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 Una casella combinata è un casella di riepilogo combinata con un controllo statico o un controllo di modifica che visualizza l'elemento attualmente selezionato nel componente casella di riepilogo della casella combinata. Il componente casella di riepilogo del controllo viene visualizzato ogni volta o solo quando l'utente seleziona la freccia a discesa (un pulsante di comando) accanto al controllo. Se il campo di selezione è un controllo di modifica, l'utente può immettere informazioni non presenti nell'elenco. In caso contrario, l'utente può solo selezionare gli elementi nell'elenco.  
  
 Nelle sezioni seguenti vengono definiti la struttura ad albero necessaria di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , le proprietà, i pattern di controllo e gli eventi per il tipo di controllo ComboBox. I requisiti di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] si applicano a tutti i controlli casella combinata, in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]o [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Struttura ad albero di automazione interfaccia utente obbligatoria  
 Nella tabella seguente vengono illustrate la visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relativo ai controlli casella combinata e viene descritto il possibile contenuto di ogni visualizzazione. Per altre informazioni sull'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Visualizzazione controlli|Visualizzazione contenuto|  
|------------------|------------------|  
|ComboBox<br /><br /> -Edit (0 o 1)<br />-List (1)<br />-Elemento elenco (figlio dell'elenco; da 0 a molti)<br />-Pulsante (1)|ComboBox<br /><br /> -Elemento elenco (da 0 a molti)|  
  
 Il controllo di modifica nella visualizzazione controlli della casella combinata è necessario solo se la casella combinata può essere modificata in modo che accetti qualsiasi input, come nel caso della casella combinata nella finestra di dialogo Esegui.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Proprietà di automazione interfaccia utente obbligatorie  
 La tabella seguente elenca le proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il cui valore o la cui definizione è particolarmente rilevante per i controlli casella combinata. Per altre informazioni sulle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|Proprietà di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Value|Note|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vedere le note.|Il valore di questa proprietà deve essere univoco in tutti i controlli in un'applicazione.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vedere le note.|Il rettangolo più esterno che contiene l'intero controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vedere le note.|Supportata se è presente un rettangolo di delimitazione. Se non tutti i punti all'interno del rettangolo di delimitazione sono selezionabili ed è stato eseguito un processo di hit testing specializzato, eseguire l'override e implementare un punto selezionabile.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|ComboBox|Questo valore è uguale per tutti i framework dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Vedere le note.|Il testo della Guida per i controlli casella combinata deve spiegare perché all'utente viene chiesto di scegliere un'opzione dalla casella combinata. Il testo è simile a quello delle informazioni presentate in una descrizione comando. Ad esempio, "Selezionare un'opzione per impostare la risoluzione dello schermo".|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Il controllo casella combinata viene sempre incluso nella visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Il controllo casella combinata viene sempre incluso nella visualizzazione controlli dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|True|I controlli casella combinata espongono un set di elementi da un contenitore di selezione. Il controllo casella combinata può ricevere lo stato attivo, anche se, quando un client di automazione interfaccia utente imposta lo stato attivo su una casella combinata, tutti gli elementi nel sottoalbero della casella combinata possono ricevere lo stato attivo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vedere le note.|I controlli casella combinata in genere includono un'etichetta di testo statico a cui questa proprietà fa riferimento.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"combo box"|Stringa localizzata corrispondente al tipo di controllo ComboBox.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vedere le note.|Il controllo casella combinata in genere ricava il proprio nome da un controllo di testo statico.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Pattern di controllo obbligatori per l'automazione interfaccia utente  
 La tabella seguente elenca i pattern di controllo di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli casella combinata. Per altre informazioni sui pattern di controllo, vedere [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Pattern di controllo|Supporto|Note|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Sì|Il controllo casella combinata, per essere tale, deve sempre contenere il pulsante a discesa.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Yes|Visualizza la selezione corrente nella casella combinata. Questo supporto viene delegato alla casella di riepilogo sotto la casella combinata.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|A seconda dei casi|Se la casella combinata può accettare valori di testo arbitrari, il pattern Value deve essere supportato. Questo pattern consente di impostare a livello di codice i contenuti delle stringhe della casella combinata. Se il pattern Value non è supportato, significa che l'utente deve effettuare una selezione tra gli elementi elenco nel sottoalbero della casella combinata.|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|Never|Il pattern Scroll non è mai direttamente supportato in una casella combinata. È supportato se è possibile scorrere una casella di riepilogo contenuta in una casella combinata. Può essere supportato solo quando la casella di riepilogo è visibile sullo schermo.|  
  
<a name="Required_Events"></a>   
## <a name="required-events"></a>Eventi obbligatori  
 La tabella seguente elenca gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli casella combinata. Per altre informazioni sugli eventi, vedere [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Supporto|Note|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Obbligatoria|Nessuna|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Obbligatoria|Nessuna|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Obbligatoria|Nessuna|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Obbligatoria|Nessuna|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obbligatoria|Nessuna|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> .|Obbligatoria|Nessuna|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|A seconda dei casi|Se il controllo supporta il pattern Value, deve supportare questo evento.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.ControlType.ComboBox>
- [Panoramica dei tipi di controllo per l'automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)
- [Panoramica di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-overview.md)
