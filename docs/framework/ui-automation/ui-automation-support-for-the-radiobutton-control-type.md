---
title: Supporto di automazione interfaccia utente per il tipo di controllo RadioButton
description: Ottenere informazioni sul supporto di automazione interfaccia utente per il tipo di controllo RadioButton. Informazioni sulla struttura ad albero, le proprietà, i pattern di controllo e gli eventi di richiesti.
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Radio Button
- UI Automation, Radio Button control type
- RadioButton control type
ms.assetid: 87170464-7857-41f1-bcf7-bb41be31cb53
ms.openlocfilehash: d0ecf6bd65b1a0008577e927939617af11043daa
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165991"
---
# <a name="ui-automation-support-for-the-radiobutton-control-type"></a>Supporto di automazione interfaccia utente per il tipo di controllo RadioButton
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono fornite informazioni sul supporto di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo RadioButton. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]un tipo di controllo è un set di condizioni che un controllo deve soddisfare per usare la proprietà <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Le condizioni includono linee guida specifiche per la struttura ad albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i valori delle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e i pattern di controllo.  
  
 Un pulsante di opzione è composto da un pulsante circolare e testo definito dall'applicazione (etichetta), un'icona o una bitmap che indica una scelta che l'utente può effettuare selezionando il pulsante. Un'applicazione usa in genere i pulsanti di opzione in una casella di gruppo per consentire all'utente di effettuare la scelta da un set di opzioni correlate che si escludono a vicenda. Ad esempio, l'applicazione potrebbe visualizzare un gruppo di pulsanti di opzione da cui l'utente può selezionare una preferenza di formato per il testo selezionato nell'area client. L'utente può selezionare un formato allineato a sinistra, a destra oppure centrato selezionando il pulsante di opzione corrispondente. In genere, l'utente può selezionare una sola opzione alla volta da un set di pulsanti di opzione.  
  
 Nelle sezioni seguenti vengono definiti la struttura ad albero, le proprietà, i pattern di controllo e gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo RadioButton. I [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisiti di si applicano a tutti i controlli elenco, sia [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Win32 che Windows Forms.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>
## <a name="required-ui-automation-tree-structure"></a>Struttura ad albero di automazione interfaccia utente obbligatoria  
 Nella tabella seguente viene illustrata la visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relativo ai controlli RadioButton e viene descritto il possibile contenuto di ogni visualizzazione. Per altre informazioni sull'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Visualizzazione controlli|Visualizzazione contenuto|  
|------------------|------------------|  
|RadioButton|RadioButton|  
  
 Non sono presenti elementi figli nella visualizzazione controlli o nella visualizzazione contenuto.  
  
<a name="Required_UI_Automation_Properties"></a>
## <a name="required-ui-automation-properties"></a>Proprietà di automazione interfaccia utente obbligatorie  
 La tabella seguente elenca le proprietà [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il cui valore o la cui definizione è particolarmente rilevante per il tipo di controllo RadioButton. Per altre informazioni sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] proprietà, vedere [proprietà di automazione interfaccia utente per i client](ui-automation-properties-for-clients.md).  
  
|Proprietà di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valore|Note|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vedere le note.|Il valore di questa proprietà deve essere univoco in tutti i controlli in un'applicazione.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vedere le note.|Il rettangolo più esterno che contiene l'intero controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vedere le note.|Se il controllo può ricevere lo stato attivo, deve supportare questa proprietà.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vedere le note.|Il nome del controllo RadioButton è il testo visualizzato accanto al pulsante con lo stato di selezione.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vedere le note.|Il punto selezionabile del pulsante di opzione DEVE essere un punto che imposta la selezione sul pulsante di opzione se viene selezionato con il puntatore del mouse.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|I pulsanti di opzione sono controlli con etichetta automatica.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|RadioButton|Questo valore è uguale per tutti i framework dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"radio button"|Stringa localizzata corrispondente al tipo di controllo RadioButton.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Il controllo pulsante di opzione viene sempre incluso nella visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Il controllo pulsante di opzione viene sempre incluso nella visualizzazione controlli dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>
## <a name="required-ui-automation-control-patterns"></a>Pattern di controllo obbligatori per l'automazione interfaccia utente  
 La tabella seguente elenca i pattern di controllo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli pulsante di opzione. Per altre informazioni sui pattern di controllo, vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Pattern di controllo/proprietà del pattern di controllo|Supporto/valore|Note|  
|-----------------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Sì|Tutti i controlli pulsante di opzione devono supportare il pattern SelectionItem per poter essere selezionati.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider.SelectionContainer%2A>|Vedere le note.|La proprietà `SelectionContainerProperty` deve sempre essere completata in modo da consentire a un client di automazione interfaccia utente di determinare quali altri pulsanti di opzione in un contesto specifico sono correlati tra loro.  Per la versione Win32 del pulsante di opzione, questa proprietà non sarà supportata perché non è possibile ottenere queste informazioni da tale framework legacy.|  
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Mai|Dopo aver impostato questa proprietà, il pulsante di opzione non può scorrere tra i propri stati.  Questo pattern non deve essere mai supportato nel pulsante di opzione.|  
  
<a name="Required_UI_Automation_Events"></a>
## <a name="required-ui-automation-events"></a>Eventi di automazione interfaccia utente obbligatori  
 La tabella seguente elenca gli eventi dell' [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli pulsante di opzione. Per altre informazioni sugli eventi, vedere [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Supporto|Note|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> .|Mai|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Richiesto|Nessuno|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.ControlType.RadioButton>
- [Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente](ui-automation-control-types-overview.md)
- [Cenni preliminari su automazione interfaccia utente](ui-automation-overview.md)
