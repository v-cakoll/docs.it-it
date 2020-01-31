---
title: Supporto per automazione interfaccia utente del tipo di controllo Spinner
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Spinner control type
- Spinner control type
- control types, Spinner
ms.assetid: 3a29d185-65d8-42e3-bcc3-7f43e96f40c5
ms.openlocfilehash: 189773525a448befe670e2a62a1ee4134ff71b0f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785955"
---
# <a name="ui-automation-support-for-the-spinner-control-type"></a>Supporto per automazione interfaccia utente del tipo di controllo Spinner
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono fornite informazioni sul supporto di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo Spinner. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]un tipo di controllo è un set di condizioni che un controllo deve soddisfare per usare la proprietà <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Le condizioni includono linee guida specifiche per la struttura ad albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i valori delle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e i pattern di controllo.  
  
 I controlli casella di selezione vengono usati per effettuare selezioni da un dominio di elementi o un intervallo di numeri.  
  
 Nelle sezioni seguenti vengono definiti la struttura ad albero, le proprietà, i pattern di controllo e gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo Spinner. I requisiti [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] si applicano a tutti i controlli casella di selezione, sia [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Win32 che Windows Forms.  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Struttura ad albero di automazione interfaccia utente obbligatoria  
 Nella tabella seguente vengono illustrate la visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che fanno riferimento ai controlli casella di selezione quando supportano i pattern di controllo RangeValue, Value e Selection, nonché viene descritto il possibile contenuto di ogni visualizzazione. Per altre informazioni sull'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
 **Pattern di controllo RangeValue o Value**  
  
|Visualizzazione controlli|Visualizzazione contenuto|  
|------------------|------------------|  
|Spinner<br /><br /> -Edit (0 o 1)<br />-Pulsante (2)|Spinner|  
  
 **Selection (pattern di controllo)**  
  
|Visualizzazione controlli|Visualizzazione contenuto|  
|------------------|------------------|  
|Spinner<br /><br /> -Edit (0 o 1)<br />-Pulsante (2)<br />-Elemento elenco (0 o più)|Spinner<br /><br /> -ListItem (0 o più)|  
  
 Per assicurarsi che i due pulsanti nel sottoalbero della visualizzazione controlli possano essere distinti dagli strumenti di test automatici, assegnare il `SmallIncrement` o `SmallDecrement` `AutomationId` in base alle esigenze. Per alcune implementazioni il controllo di modifica associato può essere un elemento di pari livello del controllo Spinner.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Proprietà di automazione interfaccia utente obbligatorie  
 La tabella seguente elenca le proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il cui valore o la cui definizione è particolarmente rilevante per i controlli casella di selezione. Per ulteriori informazioni sulle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [UI Automation Properties for clients](ui-automation-properties-for-clients.md).  
  
|Proprietà di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valore|Note|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vedere le note.|Il valore di questa proprietà deve essere univoco in tutti i controlli in un'applicazione.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vedere le note.|Il rettangolo più esterno che contiene l'intero controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vedere le note.|Il punto selezionabile del controllo casella di selezione fornisce lo stato attivo alla parte modificabile del controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vedere le note.|Se il controllo può ricevere lo stato attivo, deve supportare questa proprietà.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vedere le note.|Il controllo casella di selezione in genere ricava il proprio nome da un'etichetta di testo statico.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vedere le note.|I controlli casella di selezione hanno un'etichetta di testo statico.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Spinner|Questo valore è uguale per tutti i framework dell'interfaccia utente.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"spinner"|Stringa localizzata corrispondente al tipo di controllo Spinner.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Il controllo casella di selezione deve essere sempre di tipo contenuto.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Il controllo casella di selezione deve essere sempre un contenuto.|  
  
<a name="Required_UI_Automation_Control_Patterns_and_Properties"></a>   
## <a name="required-ui-automation-control-patterns-and-properties"></a>Pattern di controllo e proprietà obbligatori per l'automazione interfaccia utente  
 La tabella seguente elenca i pattern di controllo di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli casella di selezione. Per altre informazioni sui pattern di controllo, vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Pattern di controllo/proprietà del pattern|Supporto/valore|Note|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|A seconda dei casi|I controlli casella di selezione che dispongono di un elenco di elementi da selezionare devono supportare questo pattern.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|Falso|I controlli casella di selezione sono sempre contenitori a selezione singola.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|A seconda dei casi|I controlli casella di selezione che occupano un intervallo numerico possono supportare questo pattern.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|A seconda dei casi|I controlli casella di selezione che si estendono su un set discreto di opzioni o numeri possono supportare questo pattern.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Eventi di automazione interfaccia utente obbligatori  
 La tabella seguente elenca gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli casella di selezione. Per altre informazioni sugli eventi, vedere [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Supporto|Note|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|A seconda dei casi|nessuna|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Richiesto|nessuna|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Richiesto|nessuna|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Richiesto|nessuna|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|A seconda dei casi|nessuna|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty> .|A seconda dei casi|nessuna|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Richiesto|nessuna|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Richiesto|nessuna|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.ControlType.Spinner>
- [Panoramica dei tipi di controllo per l'automazione interfaccia utente](ui-automation-control-types-overview.md)
- [Panoramica di automazione interfaccia utente](ui-automation-overview.md)
