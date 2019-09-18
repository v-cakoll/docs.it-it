---
title: Mapping dei pattern di controllo per i client di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: cfd8e5dbe34df7b947646c714a360cf56b0435a4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043866"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Mapping dei pattern di controllo per i client di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]vedere [API di automazione di Windows: Automazione](https://go.microsoft.com/fwlink/?LinkID=156746)interfaccia utente.  
  
 In questo argomento vengono elencati i tipi di controllo e i pattern di controllo associati.  
  
 Nella tabella seguente i pattern di controllo sono organizzati nelle categorie seguenti:  
  
- Supportato. Il controllo deve supportare questo il pattern di controllo.  
  
- Supporto condizionale. Il controllo può supportare questo pattern di controllo a seconda dello stato del controllo.  
  
- Non supportati. Il controllo non supporta questo pattern di controllo. I controlli personalizzati possono supportare questo pattern di controllo.  
  
> [!NOTE]
> Alcuni controlli sono caratterizzati dal supporto condizionale per diversi pattern di controllo a seconda della funzionalità del controllo. Ad esempio, il controllo voce di menu prevede il supporto condizionale per il pattern di controllo <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>o <xref:System.Windows.Automation.SelectionItemPattern> a seconda della relativa funzione nel controllo menu.  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>Pattern di controllo di automazione interfaccia utente per i client  
  
|Tipo di controllo|Supportato|Supporto condizionale|Non supportato|  
|------------------|---------------|-------------------------|-------------------|  
|Button|Nessuna|Invoke, Toggle, ExpandCollapse|Nessuna|  
|Calendar|Grid, Table|Selection, Scroll|Value|  
|CheckBox|Toggle|Nessuna|Nessuna|  
|ComboBox|ExpandCollapse|Selection, Value|Scroll|  
|DataGrid|Grid|Scroll, Selection, Table|Nessuna|  
|DataItem|SelectionItem|ExpandCollapse, GridItem, ScrollItem, Table, Toggle, Value|Nessuna|  
|Documento|Text|Scroll, Value|Nessuna|  
|Edit|Nessuna|Text, RangeValue, Value|Nessuna|  
|Group|Nessuna|ExpandCollapse|Nessuna|  
|Header|Nessuna|Transform|Nessuna|  
|HeaderItem|Nessuna|Transform, Invoke|Nessuna|  
|Hyperlink|Invoke|Value|Nessuna|  
|Image|Nessuna|GridItem, TableItem|Invoke, SelectionItem|  
|List|Nessuna|Grid, MultipleView, Scroll, Selection|Tabella|  
|ListItem|SelectionItem|ExpandCollapse, GridItem, Invoke, ScrollItem, Toggle, Value|Nessuna|  
|Menu|Nessuna|Nessuna|Nessuna|  
|MenuBar|Nessuna|ExpandCollapse, Dock, Transform|Nessuna|  
|MenuItem|Nessuna|ExpandCollapse, Invoke, SelectionItem, Toggle|Nessuna|  
|Pane|Nessuna|Dock Scroll, Transform|Finestra|  
|ProgressBar|Nessuna|RangeValue, Value|Nessuna|  
|RadioButton|SelectionItem|Nessuna|Toggle|  
|ScrollBar|Nessuna|RangeValue|Scroll|  
|Separatore|Nessuna|Nessuna|Nessuna|  
|Slider|Nessuna|RangeValue, Selection, Value|Nessuna|  
|Spinner|Nessuna|RangeValue, Selection, Value|Nessuna|  
|Pulsante di menu combinato|Invoke, ExpandCollapse|Nessuna|Nessuna|  
|StatusBar|Nessuna|Grid|Nessuna|  
|TAB|Selection|Scroll|Nessuna|  
|TabItem|SelectionItem|Nessuna|Invoke|  
|Tabella|Grid, GridItem, Table, TableItem|Nessuna|Nessuna|  
|Text|Nessuna|GridItem, TableItem, Text|Value|  
|Thumb|Transform|Nessuna|Nessuna|  
|TitleBar|Nessuna|Nessuna|Nessuna|  
|ToolBar|Nessuna|Dock, ExpandCollapse, Transform|Nessuna|  
|ToolTip|Nessuna|Text, Window|Nessuna|  
|Tree|Nessuna|Scroll, Selection|Nessuna|  
|TreeItem|ExpandCollapse|Invoke, ScrollItem, SelectionItem, Toggle|Nessuna|  
|Window|Transform, Window|Dock|Nessuna|  
  
> [!NOTE]
> Se un tipo di controllo non dispone di pattern di controllo supportati ma ha uno o più pattern di controllo supportati in modo condizionale, uno dei pattern di controllo condizionali risulterà sempre supportato.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di automazione interfaccia utente](ui-automation-overview.md)
