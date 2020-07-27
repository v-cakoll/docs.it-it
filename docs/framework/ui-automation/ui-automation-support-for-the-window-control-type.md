---
title: Supporto per l'automazione interfaccia utente del tipo di controllo Window
description: Ottenere informazioni sul supporto di automazione interfaccia utente per il tipo di controllo Window. Informazioni sulla struttura ad albero, le proprietà, i pattern di controllo e gli eventi di richiesti.
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Window control type
- Window control type
- control types, Window
ms.assetid: 53be78a6-cdcc-4af3-a464-5927d19c54e8
ms.openlocfilehash: ba5ea794fb9712f7e48f76c6ca3884d4bb05728e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167708"
---
# <a name="ui-automation-support-for-the-window-control-type"></a>Supporto per l'automazione interfaccia utente del tipo di controllo Window
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono fornite informazioni sul supporto di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo Window. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]un tipo di controllo è un set di condizioni che un controllo deve soddisfare per usare la proprietà <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Le condizioni includono linee guida specifiche per la struttura ad albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i valori delle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e i pattern di controllo.  
  
 Il controllo finestra è costituito dalla cornice della finestra, che contiene oggetti figlio, ad esempio barra del titolo, oggetti client e altri oggetti.  
  
 I [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisiti nelle sezioni seguenti si applicano a tutti i controlli che implementano il tipo di controllo Window, [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] ovvero Win32 o Windows Forms.  
  
## <a name="required-ui-automation-tree-structure"></a>Struttura ad albero di automazione interfaccia utente obbligatoria  
 Nella tabella seguente viene illustrata la visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relativo ai controlli finestra e viene descritto il possibile contenuto di ogni visualizzazione. Per altre informazioni sull'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).  
  
|Visualizzazione controlli|Visualizzazione contenuto|  
|------------------|------------------|  
|Finestra|Finestra|  
  
## <a name="required-ui-automation-properties"></a>Proprietà di automazione interfaccia utente obbligatorie  
 La tabella seguente elenca le proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il cui valore o la cui definizione è particolarmente rilevante per i controlli finestra. Per altre informazioni sulle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).  
  
|Proprietà di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valore|Note|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vedere le note.|Il valore di questa proprietà deve essere univoco in tutti i controlli in un'applicazione.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vedere le note.|Il rettangolo più esterno che contiene l'intero controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vedere le note.|Il controllo finestra deve avere un punto selezionabile che genererà la selezione o deselezione della finestra.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Finestra|Questo valore è uguale per tutti i framework dell'interfaccia utente.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Il controllo finestra deve essere sempre di tipo contenuto.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Il controllo finestra deve essere sempre un controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vedere le note.|Se il controllo può ricevere lo stato attivo, deve supportare questa proprietà.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`null`|I controlli finestra in genere non hanno un'etichetta statica.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"window"|Stringa localizzata corrispondente al tipo di controllo Window.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vedere le note.|Il controllo finestra contiene sempre un elemento Window principale che fa riferimento all'elemento associato dall'utente come identificatore più significativo per l'elemento.|  
  
## <a name="required-ui-automation-control-patterns"></a>Pattern di controllo obbligatori per l'automazione interfaccia utente  
 La tabella seguente elenca i pattern di controllo di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli finestra. Per altre informazioni sui pattern di controllo, vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).  
  
|Pattern di controllo|Supporto|Note|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IDockProvider>|Condizionale|Deve essere supportato se la finestra può essere ancorata.|  
|<xref:System.Windows.Automation.Provider.ITransformProvider>|Richiesto|Abilita lo spostamento, il ridimensionamento o la rotazione della finestra sullo schermo.|  
|<xref:System.Windows.Automation.Provider.IWindowProvider>|Richiesto|Abilita operazioni specifiche per la finestra.|  
  
## <a name="required-ui-automation-events"></a>Eventi di automazione interfaccia utente obbligatori  
 La tabella seguente elenca gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli finestra. Per altre informazioni sugli eventi, vedere [UI Automation Events Overview](ui-automation-events-overview.md).  
  
|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Supporto|Note|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AsyncContentLoadedEvent>|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.AutomationElement.AutomationFocusChangedEvent>|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LayoutInvalidatedEvent>|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> .|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.AutomationElement.StructureChangedEvent>|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> .|Dipende da|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> .|Dipende da|Nessuno|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowClosedEvent>|Richiesto|Nessuno|  
|<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowOpenedEvent>|Richiesto|Nessuno|  
|Evento di modifica della proprietà<xref:System.Windows.Automation.WindowPatternIdentifiers.WindowVisualStateProperty> .|Dipende da|Nessuno|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.ControlType.Window>
- [Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente](ui-automation-control-types-overview.md)
- [Cenni preliminari su automazione interfaccia utente](ui-automation-overview.md)
