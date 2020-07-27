---
title: Supporto per automazione interfaccia utente del tipo di controllo DataItem
description: Ottenere informazioni sul supporto di automazione interfaccia utente per il tipo di controllo DataItem. Informazioni sulla struttura ad albero, le proprietà, i pattern di controllo e gli eventi di richiesti.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Data Item control type
- Data Item control type
- control types, Data Item
ms.assetid: 181708fd-2595-4c43-9abd-75811627d64c
ms.openlocfilehash: c1b149e1033303e98bd150e62c6344b60eec1f93
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167984"
---
# <a name="ui-automation-support-for-the-dataitem-control-type"></a>Supporto per automazione interfaccia utente del tipo di controllo DataItem
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono fornite informazioni sul supporto di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] per il tipo di controllo DataItem. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] un tipo di controllo è un set di condizioni che un controllo deve soddisfare per usare la proprietà <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Le condizioni includono linee guida specifiche per la struttura ad albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i valori delle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e i pattern di controllo.  
  
 Una voce in un elenco Contatti, ad esempio, è un controllo elemento dati. Un controllo elemento dati contiene informazioni di interesse per un utente finale. È più complicato del semplice elemento elenco poiché contiene informazioni più dettagliate.  
  
 Nelle sezioni seguenti vengono definiti la struttura ad albero, le proprietà, i pattern di controllo e gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo DataItem. I [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisiti di si applicano a tutti i controlli elemento dati, sia [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Win32 che Windows Forms.  
  
## <a name="required-ui-automation-tree-structure"></a>Struttura ad albero di automazione interfaccia utente obbligatoria  
 Nella tabella seguente viene illustrata la visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relativo ai controlli elemento dati e viene descritto il possibile contenuto di ogni visualizzazione. Per altre informazioni sull'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Albero di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Visualizzazione controlli|Albero di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Visualizzazione contenuto|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|DataItem<br /><br /> -Varia (0 o più, può essere strutturato in una gerarchia)|DataItem<br /><br /> -Varia (0 o più, può essere strutturato in una gerarchia)|  
  
 Un elemento dati in una griglia di dati può contenere vari tipi di oggetti, incluso un altro livello di elementi dati o specifici elementi di griglia quali testo, immagini o controlli di modifica. Se l'elemento dati dispone di un ruolo di oggetto specifico, l'elemento deve essere esposto come tipo di controllo specifico; ad esempio, un tipo di controllo ListItem per un elemento dati selezionabile della griglia.  
  
## <a name="required-ui-automation-properties"></a>Proprietà di automazione interfaccia utente obbligatorie  
 La tabella seguente elenca le proprietà il cui valore o la cui definizione è particolarmente rilevante per i controlli elemento dati. Per altre informazioni sulle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
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
  
## <a name="required-ui-automation-control-patterns"></a>Pattern di controllo obbligatori per l'automazione interfaccia utente  
 La tabella seguente elenca i pattern di controllo di [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli elemento dati. Per altre informazioni sui pattern di controllo, vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Pattern di controllo|Supporto|Note|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Dipende da|Se è possibile espandere o comprimere l'elemento dati per visualizzare e nascondere informazioni, è necessario il supporto del pattern Expand Collapse.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Dipende da|Gli elementi dati supportano il pattern GridItem quando un insieme di elementi dati è disponibile in un contenitore in cui è possibile spostarsi elemento per elemento.|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider>|Dipende da|Tutti gli elementi dati supportano la possibilità di scorrimento nella visualizzazione con il pattern ScrollItem quando il relativo contenitore dei dati ha più elementi adattabili allo schermo.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Sì|Tutti gli elementi dati devono supportare il pattern SelectionItem per indicare quando l'elemento è selezionato.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Dipende da|Se l'elemento dati è contenuto in un tipo di controllo DataGrid, supporta questo pattern.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Dipende da|Se l'elemento dati contiene uno stato che può essere alternato ciclicamente.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Dipende da|Se il testo primario dell'elemento dati è modificabile, il pattern Value deve essere supportato.|  
  
## <a name="working-with-data-items-in-large-lists"></a>Uso di elementi dati in elenchi di grandi dimensioni  
 Gli elenchi di grandi dimensioni sono spesso virtualizzati nei framework dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] per migliorare le prestazioni. Per questo motivo, un client di automazione interfaccia utente non può usare la funzionalità di query di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per cercare il contenuto dell'intero albero come avviene per altri contenitori di elementi. È necessario che un client scorra la visualizzazione dell'elemento (o che espanda il controllo in modo che vengano visualizzate tutte le opzioni rilevanti) prima di accedere al set completo di informazioni dell'elemento dati.  
  
 Quando `SetFocus` si chiama sull' [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] elemento per l'elemento di dati, il caso di Esplora risorse di Microsoft Windows viene restituito correttamente e causa l'impostazione dello stato attivo sulla modifica all'interno del sottoalbero dell'elemento dati.  
  
## <a name="required-ui-automation-events"></a>Eventi di automazione interfaccia utente obbligatori  
 La tabella seguente elenca gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli elemento dati. Per altre informazioni sugli eventi, vedere [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Supporto|Note|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> .|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> .|Dipende da|Nessuno|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|Dipende da|Nessuno|  
  
## <a name="dataitem-control-type-example"></a>Esempio del tipo di controllo DataItem  
 Nell'immagine seguente viene illustrato un tipo di controllo DataItem in un controllo ListView che fornisce supporto per le informazioni dettagliate all'interno delle colonne.  
  
 ![Grafica di controllo ListView con due elementi di dati](./media/uiauto-data-grid-detailed.GIF "uiauto_data_grid_detailed")  
  
 La visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relative al controllo elemento dati sono visualizzate di seguito. I pattern di controllo per ogni elemento di automazione sono indicati tra parentesi. Il gruppo "Contoso" fa inoltre parte della griglia del controllo host DataGrid.  
  
|Albero di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Visualizzazione controlli|Albero di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] - Visualizzazione contenuto|  
|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------|  
|-Gruppo "contoso" (tabella, griglia)<br />-DataItem "Accounts Receivable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-Image "Accounts Receivable.doc"<br />-Edit "Name" (TableItem, GridItem, value "Accounts Receivable.doc")<br />-Modifica "Data modifica" (TableItem, GridItem, valore "8/25/2006 3:29 PM")<br />-Edit "size" (GridItem, TableItem, valore "11,0 KB)<br />-DataItem "Accounts Payable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-   ...|-Gruppo "contoso" (tabella, griglia)<br />-DataItem "Accounts Receivable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-Image "Accounts Receivable.doc"<br />-Edit "Name" (TableItem, GridItem, value "Accounts Receivable.doc")<br />-Modifica "Data modifica" (TableItem, GridItem, valore "8/25/2006 3:29 PM")<br />-Edit "size" (GridItem, TableItem, valore "11,0 KB)<br />-DataItem "Accounts Payable.doc" (TableItem, GridItem, SelectionItem, Invoke)<br />-   …|  
  
 Se una griglia rappresenta un elenco di elementi selezionabili, è possibile esporre gli elementi dell'interfaccia utente corrispondenti con il tipo di controllo ListItem anziché con DataItem. Nell'esempio precedente, gli elementi DataItem ("Accounts Receivable.doc" e "Accounts Payable.doc") in Group ("Contoso") possono essere migliorati esponendoli come tipi di controllo ListItem, poiché questo tipo già supporta il pattern di controllo SelectionItem.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.ControlType.DataItem>
- [Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente](ui-automation-control-types-overview.md)
- [Cenni preliminari su automazione interfaccia utente](ui-automation-overview.md)
