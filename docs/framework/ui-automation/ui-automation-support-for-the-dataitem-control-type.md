---
title: Supporto per automazione interfaccia utente del tipo di controllo DataItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- UI Automation, Data Item control type
- Data Item control type
- control types, Data Item
ms.assetid: 181708fd-2595-4c43-9abd-75811627d64c
caps.latest.revision: "36"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: be826cce87d428a156bb7a10d858e5848b2f1143
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="ui-automation-support-for-the-dataitem-control-type"></a>Supporto per automazione interfaccia utente del tipo di controllo DataItem
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento vengono fornite informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per il tipo di controllo DataItem. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] un tipo di controllo è un set di condizioni che un controllo deve soddisfare per usare la proprietà <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Le condizioni includono linee guida specifiche per la struttura ad albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i valori delle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e i pattern di controllo.  
  
 Una voce in un elenco Contatti, ad esempio, è un controllo elemento dati. Un controllo elemento dati contiene informazioni di interesse per un utente finale. È più complicato del semplice elemento elenco poiché contiene informazioni più dettagliate.  
  
 Nelle sezioni seguenti vengono definiti la struttura ad albero, le proprietà, i pattern di controllo e gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo DataItem. I requisiti di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] si applicano a tutti i controlli elemento dati, ovvero [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]o [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Struttura ad albero di automazione interfaccia utente obbligatoria  
 Nella tabella seguente viene illustrata la visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relativo ai controlli elemento dati e viene descritto il possibile contenuto di ogni visualizzazione. Per altre informazioni sull'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Albero di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Visualizzazione controlli|Albero di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Visualizzazione contenuto|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|DataItem<br /><br /> -Varia (0 o più, può essere strutturato in una gerarchia)|DataItem<br /><br /> -Varia (0 o più, può essere strutturato in una gerarchia)|  
  
 Un elemento dati in una griglia di dati può contenere vari tipi di oggetti, incluso un altro livello di elementi dati o specifici elementi di griglia quali testo, immagini o controlli di modifica. Se l'elemento dati dispone di un ruolo di oggetto specifico, l'elemento deve essere esposto come tipo di controllo specifico; ad esempio, un tipo di controllo ListItem per un elemento dati selezionabile della griglia.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Proprietà di automazione interfaccia utente obbligatorie  
 La tabella seguente elenca le proprietà il cui valore o la cui definizione è particolarmente rilevante per i controlli elemento dati. Per altre informazioni sulle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|Proprietà|Valore|Note|  
|--------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vedere le note.|Il valore di questa proprietà deve essere univoco in tutti i controlli in un'applicazione.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vedere le note.|Il rettangolo più esterno che contiene l'intero controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vedere le note.|Supportata se è presente un rettangolo di delimitazione. Se non tutti i punti all'interno del rettangolo di delimitazione sono selezionabili ed è stato eseguito un processo di hit testing specializzato, eseguire l'override e implementare un punto selezionabile.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|DataItem|Questo valore è uguale per tutti i framework dell'interfaccia utente.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Il controllo elemento dati deve essere sempre un contenuto.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Il controllo elemento dati deve essere sempre un controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vedere le note.|Se il controllo può ricevere lo stato attivo, deve supportare questa proprietà.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemStatusProperty>|Vedere le note.|Se il controllo contiene uno stato aggiornato dinamicamente, è necessario che questa proprietà sia supportata in modo da consentire ai prodotti di assistive technology di ricevere aggiornamenti quando lo stato dell'elemento cambia.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemTypeProperty>|Vedere le note.|Si tratta del valore della stringa che indica all'utente finale l'oggetto sottostante rappresentato dall'elemento, ad esempio "File multimediale" o "Contatto".|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|I controlli elemento dati non hanno un'etichetta di testo statico.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"elemento dati"|Stringa localizzata corrispondente al tipo di controllo DataItem.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vedere le note.|Il controllo elemento dati contiene sempre un elemento di testo primario correlato all'identificatore semantico che un utente assocerebbe all'elemento.|  
  
<a name="_Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Pattern di controllo obbligatori per l'automazione interfaccia utente  
 La tabella seguente elenca i pattern di controllo di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli elemento dati. Per altre informazioni sui pattern di controllo, vedere [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Pattern di controllo|Supporto|Note|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|A seconda dei casi|Se è possibile espandere o comprimere l'elemento dati per visualizzare e nascondere informazioni, è necessario il supporto del pattern Expand Collapse.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|A seconda dei casi|Gli elementi dati supportano il pattern GridItem quando un insieme di elementi dati è disponibile in un contenitore in cui è possibile spostarsi elemento per elemento.|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|A seconda dei casi|Tutti gli elementi dati supportano la possibilità di scorrimento nella visualizzazione con il pattern ScrollItem quando il relativo contenitore dei dati ha più elementi adattabili allo schermo.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Sì|Tutti gli elementi dati devono supportare il pattern SelectionItem per indicare quando l'elemento è selezionato.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|A seconda dei casi|Se l'elemento dati è contenuto in un tipo di controllo DataGrid, supporta questo pattern.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|A seconda dei casi|Se l'elemento dati contiene uno stato che può essere alternato ciclicamente.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|A seconda dei casi|Se il testo primario dell'elemento dati è modificabile, il pattern Value deve essere supportato.|  
  
<a name="Working_with_Data_Items_in_Large_Lists"></a>   
## <a name="working-with-data-items-in-large-lists"></a>Uso di elementi dati in elenchi di grandi dimensioni  
 Gli elenchi di grandi dimensioni sono spesso virtualizzati nei framework dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] per migliorare le prestazioni. Per questo motivo, un client di automazione interfaccia utente non può usare la funzionalità di query di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per cercare il contenuto dell'intero albero come avviene per altri contenitori di elementi. È necessario che un client scorra la visualizzazione dell'elemento (o che espanda il controllo in modo che vengano visualizzate tutte le opzioni rilevanti) prima di accedere al set completo di informazioni dell'elemento dati.  
  
 Quando si chiama `SetFocus` sull'elemento di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per l'elemento dati, il case di [!INCLUDE[TLA#tla_winexpl](../../../includes/tlasharptla-winexpl-md.md)] viene restituito correttamente e causa l'impostazione dello stato attivo su Edit nel sottoalbero dell'elemento dati.  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Eventi di automazione interfaccia utente obbligatori  
 La tabella seguente elenca gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli elemento dati. Per altre informazioni sugli eventi, vedere [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] |Supporto|Note|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Obbligatorio|nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Obbligatorio|nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Obbligatorio|nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Obbligatorio|nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> .|Obbligatorio|Nessuna|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obbligatorio|nessuno|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|A seconda dei casi|nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> .|A seconda dei casi|Nessuno|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Obbligatorio|Nessuna|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Obbligatorio|Nessuna|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Obbligatorio|nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> .|A seconda dei casi|nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|A seconda dei casi|nessuno|  
  
<a name="Data_Item_Control_Type_Example"></a>   
## <a name="dataitem-control-type-example"></a>Esempio del tipo di controllo DataItem  
 Nell'immagine seguente viene illustrato un tipo di controllo DataItem in un controllo ListView che fornisce supporto per le informazioni dettagliate all'interno delle colonne.  
  
 ![Grafico di un controllo visualizzazione elenco con due elementi di dati](../../../docs/framework/ui-automation/media/uiauto-data-grid-detailed.GIF "uiauto_data_grid_detailed")  
  
 La visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relative al controllo elemento dati sono visualizzate di seguito. I pattern di controllo per ogni elemento di automazione sono indicati tra parentesi. Il gruppo "Contoso" fa inoltre parte della griglia del controllo host DataGrid.  
  
|Albero di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Visualizzazione controlli|Albero di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Visualizzazione contenuto|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|-Gruppo "Contoso" (tabella, della griglia)<br />-DataItem "account Receivable.doc" (Invoke, SelectionItem, TableItem, GridItem)<br />-Immagine "Accounts Receivable.doc"<br />: Consente di modificare "Nome" (valore TableItem, GridItem, "Accounts Receivable.doc")<br />: Consente di modificare "Data ultima modifica" (valore TableItem, GridItem, "25/8/2006 3:29 PM")<br />: Consente di modificare "Dimensioni" (valore GridItem, TableItem, "11.0 KB)<br />-DataItem "account Payable.doc" (Invoke, SelectionItem, TableItem, GridItem)<br />-   ...|-Gruppo "Contoso" (tabella, della griglia)<br />-DataItem "account Receivable.doc" (Invoke, SelectionItem, TableItem, GridItem)<br />-Immagine "Accounts Receivable.doc"<br />: Consente di modificare "Nome" (valore TableItem, GridItem, "Accounts Receivable.doc")<br />: Consente di modificare "Data ultima modifica" (valore TableItem, GridItem, "25/8/2006 3:29 PM")<br />: Consente di modificare "Dimensioni" (valore GridItem, TableItem, "11.0 KB)<br />-DataItem "account Payable.doc" (Invoke, SelectionItem, TableItem, GridItem)<br />-   …|  
  
 Se una griglia rappresenta un elenco di elementi selezionabili, è possibile esporre gli elementi dell'interfaccia utente corrispondenti con il tipo di controllo ListItem anziché con DataItem. Nell'esempio precedente, gli elementi DataItem ("Accounts Receivable.doc" e "Accounts Payable.doc") in Group ("Contoso") possono essere migliorati esponendoli come tipi di controllo ListItem, poiché questo tipo già supporta il pattern di controllo SelectionItem.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Automation.ControlType.DataItem>  
 [Panoramica dei tipi di controllo per l'automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [Panoramica di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-overview.md)
