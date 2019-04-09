---
title: Supporto per automazione interfaccia utente del tipo di controllo ProgressBar
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Progress Bar
- ProgressBar control type
- UI Automation, Progress Bar control type
ms.assetid: 302e778c-24b0-4789-814a-c8d37cf53a5f
ms.openlocfilehash: 7a3347aa0fa272ea0b93ac2ad504943f37c65b2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217731"
---
# <a name="ui-automation-support-for-the-progressbar-control-type"></a>Supporto per automazione interfaccia utente del tipo di controllo ProgressBar
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento vengono fornite informazioni sul supporto di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo ProgressBar. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]un tipo di controllo è un set di condizioni che un controllo deve soddisfare per usare la proprietà <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Le condizioni includono linee guida specifiche per la struttura ad albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i valori delle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i pattern di controllo e gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
 I controlli indicatore di stato sono un esempio di controlli che implementano il tipo di controllo ProgressBar. I controlli indicatore di stato vengono usati per indicare lo stato di avanzamento di un'operazione la cui esecuzione richiede molto tempo. Il controllo è costituito da un rettangolo che viene riempito gradualmente con il colore di sistema durante l'esecuzione dell'operazione.  
  
 Nelle sezioni seguenti vengono definiti la struttura ad albero, le proprietà, i pattern di controllo e gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo ProgressBar. I requisiti di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] si applicano a tutti i controlli elenco, ovvero [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]o [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Struttura ad albero di automazione interfaccia utente obbligatoria  
 Nella tabella seguente viene illustrata la visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relativo ai controlli indicatore di stato e viene descritto il possibile contenuto di ogni visualizzazione. Per altre informazioni sull'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Visualizzazione controlli|Visualizzazione contenuto|  
|------------------|------------------|  
|ProgressBar|ProgressBar|  
  
 I controlli indicatore di stato non includono elementi figli nella visualizzazione controlli o nella visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Proprietà di automazione interfaccia utente obbligatorie  
 La tabella seguente elenca le proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il cui valore o la cui definizione è particolarmente rilevante per i controlli indicatore di stato. Per ulteriori informazioni sul [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] proprietà, vedere [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Proprietà|Value|Note|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vedere le note.|Il valore di questa proprietà deve essere univoco in tutti i controlli in un'applicazione.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vedere le note.|Il rettangolo più esterno che contiene l'intero controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vedere le note.|Supportata se è presente un rettangolo di delimitazione. Se non tutti i punti all'interno del rettangolo di delimitazione sono selezionabili ed è stato eseguito un processo di hit testing specializzato, eseguire l'override e implementare un punto selezionabile.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vedere le note.|Se il controllo può ricevere lo stato attivo, deve supportare questa proprietà.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vedere le note.|Il controllo indicatore di stato in genere ricava il proprio nome da un'etichetta di testo statico. Se non è presente alcuna etichetta di testo statico, lo sviluppatore dell'applicazione deve esporre un valore per la proprietà `Name` .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vedere le note.|Se è presente un'etichetta di testo statico, questa proprietà deve esporre un riferimento a tale controllo.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|ProgressBar|Questo valore è uguale per tutti i framework dell'interfaccia utente.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"progress bar"|Stringa localizzata corrispondente al tipo di controllo ProgressBar.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Il controllo indicatore di stato viene sempre incluso nella visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Il controllo indicatore di stato viene sempre incluso nella visualizzazione controlli dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|  
  
<a name="Required_UI_Automation_Control_Patterns_and_Properties"></a>   
## <a name="required-ui-automation-control-patterns-and-properties"></a>Pattern di controllo e proprietà obbligatori per l'automazione interfaccia utente  
 La tabella seguente elenca i pattern di controllo per [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati dai controlli indicatore di stato. Per altre informazioni sui pattern di controllo, vedere [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Pattern di controllo/proprietà del pattern|Supporto/valore|Note|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|A seconda dei casi|Il controllo indicatore di stato che fornisce un'indicazione testuale dello stato di avanzamento deve implementare <xref:System.Windows.Automation.Provider.IValueProvider>.|  
|<xref:System.Windows.Automation.Provider.IValueProvider.IsReadOnly%2A>|True|Il valore per questa proprietà è sempre True.|  
|<xref:System.Windows.Automation.Provider.IValueProvider.Value%2A>|Vedere le note.|Questa proprietà espone lo stato di avanzamento in formato testuale di un controllo indicatore di stato.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|A seconda dei casi|Devono implementare i controlli barra di stato che accettano un intervallo numerico <xref:System.Windows.Automation.Provider.IRangeValueProvider>|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Minimum%2A>|0.0|Il valore di questa proprietà è il valore minimo che è possibile impostare per il controllo.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Maximum%2A>|100.0|Il valore di questa proprietà è il valore massimo che è possibile impostare per il controllo.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.SmallChange%2A>|NaN|Questa proprietà non è necessaria perché i controlli indicatore di stato sono di sola lettura.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.LargeChange%2A>|NaN|Questa proprietà non è necessaria perché i controlli indicatore di stato sono di sola lettura.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Eventi di automazione interfaccia utente obbligatori  
 La tabella seguente elenca gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli indicatore di stato. Per altre informazioni sugli eventi, vedere [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] event|Supporto|Note|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> evento di modifica della proprietà.|Obbligatorio|nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> evento di modifica della proprietà.|Obbligatorio|nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> evento di modifica della proprietà.|Obbligatorio|nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> evento di modifica della proprietà.|Obbligatorio|nessuno|  
|<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> evento di modifica della proprietà.|A seconda dei casi|nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Obbligatorio|nessuno|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Obbligatorio|nessuno|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.ControlType.ProgressBar>
- [Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)
- [Cenni preliminari su automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-overview.md)
