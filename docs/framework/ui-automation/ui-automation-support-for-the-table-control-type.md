---
title: Supporto per automazione interfaccia utente del tipo di controllo Table
description: Ottenere informazioni sul supporto di automazione interfaccia utente per il tipo di controllo Table. Informazioni sulla struttura ad albero, le proprietà, i pattern di controllo e gli eventi di richiesti.
ms.date: 03/30/2017
helpviewer_keywords:
- TableControl type
- control types, Table
- UI Automation, Table control type
ms.assetid: 9050dde5-6469-4c83-abb7-f861c24ff985
ms.openlocfilehash: 13790d601b370f60a0e9a998effcbf4744b63712
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87163629"
---
# <a name="ui-automation-support-for-the-table-control-type"></a>Supporto per automazione interfaccia utente del tipo di controllo Table
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono fornite informazioni sul supporto di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo Table. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]un tipo di controllo è un set di condizioni che un controllo deve soddisfare per usare la proprietà <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Le condizioni includono linee guida specifiche per la struttura ad albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i valori delle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e i pattern di controllo.  
  
 I controlli tabella contengono righe e colonne di testo e, facoltativamente, intestazioni di riga e intestazioni di colonna.  
  
 Nelle sezioni seguenti vengono definiti la struttura ad albero, le proprietà, i pattern di controllo e gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo Table. I [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisiti di si applicano a tutti i controlli tabella, sia [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Win32 che Windows Forms.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>
## <a name="required-ui-automation-tree-structure"></a>Struttura ad albero di automazione interfaccia utente obbligatoria  
 Nella tabella seguente viene illustrata la visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relativo ai controlli tabella e viene descritto il possibile contenuto di ogni visualizzazione. Per altre informazioni sull'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Visualizzazione controlli|Visualizzazione contenuto|  
|------------------|------------------|  
|Tabella<br /><br /> -Header (0 o 1)<br />-Text (0 o 1)<br />-Vari controlli (0 o più)|Tabella<br /><br /> -Text (0 o più)<br />-Vari controlli (0 o più)|  
  
 Se un controllo tabella include intestazioni di riga o colonna, queste informazioni devono essere esposte nella visualizzazione controlli dell'albero di automazione interfaccia utente. La visualizzazione contenuto non deve esporre queste informazioni perché è possibile accedervi usando la proprietà TablePattern.  
  
<a name="Required_UI_Automation_Properties"></a>
## <a name="required-ui-automation-properties"></a>Proprietà di automazione interfaccia utente obbligatorie  
 La tabella seguente elenca le proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il cui valore o la cui definizione è particolarmente rilevante per i controlli Table. Per altre informazioni sulle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Proprietà di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valore|Note|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vedere le note.|Il valore di questa proprietà deve essere univoco in tutti i controlli in un'applicazione.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vedere le note.|Il rettangolo più esterno che contiene l'intero controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vedere le note.|Supportata se è presente un rettangolo di delimitazione. Se non tutti i punti all'interno del rettangolo di delimitazione sono selezionabili ed è stato eseguito un processo di hit testing specializzato, eseguire l'override e implementare un punto selezionabile.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vedere le note.|Se il controllo può ricevere lo stato attivo, deve supportare questa proprietà.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vedere le note.|Il controllo tabella in genere ricava il proprio nome da un'etichetta di testo statico. Se non è presente alcuna etichetta di testo statico, è necessario assegnare una proprietà Name che deve essere sempre disponibile per descrivere lo scopo della tabella.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vedere le note.|Se è presente un'etichetta di testo statico, questa proprietà deve esporre un riferimento all'elemento di automazione del controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Tabella|Questo valore è uguale per tutti i framework dell'interfaccia utente.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"table"|Stringa localizzata corrispondente al tipo di controllo Table.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Vedere le note.|Altre informazioni sullo scopo della tabella devono essere esposte tramite questa proprietà se non viene illustrata in modo sufficiente accedendo alla proprietà NameProperty.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Il controllo tabella deve essere sempre di tipo contenuto.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Il controllo tabella deve essere sempre un controllo.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>
## <a name="required-ui-automation-control-patterns"></a>Pattern di controllo obbligatori per l'automazione interfaccia utente  
 La tabella seguente elenca i pattern di controllo dell' [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli tabella. Per altre informazioni sui pattern di controllo, vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Pattern di controllo|Supporto|Note|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridProvider>|Sì|Il controllo tabella supporta sempre questo pattern di controllo perché gli elementi che contiene dispone di dati visualizzati in una griglia.|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Sì (obbligatorio con oggetti figlio)|Gli oggetti interni di una tabella devono supportare sia il pattern di controllo GridItem sia il pattern di controllo TableItem. La tabella stessa non deve supportare il pattern di controllo GridItem o TableItem, a meno che la tabella non faccia parte di un'altra tabella.|  
|<xref:System.Windows.Automation.Provider.ITableProvider>|Sì|Il controllo tabella supporta sempre l'associazione di intestazioni al contenuto.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Sì (obbligatorio con oggetti figlio)|Gli oggetti interni di una tabella devono supportare sia il pattern di controllo GridItem sia il pattern di controllo TableItem. La tabella stessa non deve supportare il pattern di controllo GridItem o TableItem, a meno che la tabella non faccia parte di un'altra tabella.|  
  
<a name="Required_UI_Automation_Events"></a>
## <a name="required-ui-automation-events"></a>Eventi di automazione interfaccia utente obbligatori  
 La tabella seguente elenca gli eventi dell' [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli tabella. Per altre informazioni sugli eventi, vedere [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Supporto|Note|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Richiesto|Nessuno|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.ControlType.Table>
- [Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente](ui-automation-control-types-overview.md)
- [Cenni preliminari su automazione interfaccia utente](ui-automation-overview.md)
