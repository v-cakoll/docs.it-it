---
title: Mapping dei pattern di controllo per i client di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: b98735b111d634584ec019a75d942f39e38cc8c5
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679580"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Mapping dei pattern di controllo per i client di automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate sulle [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: Automazione interfaccia utente](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In questo argomento vengono elencati i tipi di controllo e i pattern di controllo associati.  
  
 Nella tabella seguente i pattern di controllo sono organizzati nelle categorie seguenti:  
  
-   Supportato. Il controllo deve supportare questo il pattern di controllo.  
  
-   Supporto condizionale. Il controllo può supportare questo pattern di controllo a seconda dello stato del controllo.  
  
-   Non supportato. Il controllo non supporta questo pattern di controllo. I controlli personalizzati possono supportare questo pattern di controllo.  
  
> [!NOTE]
>  Alcuni controlli sono caratterizzati dal supporto condizionale per diversi pattern di controllo a seconda della funzionalità del controllo. Ad esempio, il controllo voce di menu prevede il supporto condizionale per il pattern di controllo <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>o <xref:System.Windows.Automation.SelectionItemPattern> a seconda della relativa funzione nel controllo menu.  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>Pattern di controllo di automazione interfaccia utente per i client  
  
|Tipo di controllo|Supportato|Supporto condizionale|Non supportato|  
|------------------|---------------|-------------------------|-------------------|  
|Button|nessuno|Invoke, Toggle, ExpandCollapse|nessuno|  
|Calendar|Grid, Table|Selection, Scroll|Value|  
|CheckBox|Toggle|nessuno|nessuno|  
|ComboBox|ExpandCollapse|Selection, Value|Scroll|  
|DataGrid|Grid|Scroll, Selection, Table|nessuno|  
|DataItem|SelectionItem|ExpandCollapse, GridItem, ScrollItem, Table, Toggle, Value|nessuno|  
|Document|Testo|Scroll, Value|nessuno|  
|Edit|nessuno|Text, RangeValue, Value|nessuno|  
|Raggruppa|nessuno|ExpandCollapse|nessuno|  
|Header|nessuno|Transform|nessuno|  
|HeaderItem|nessuno|Transform, Invoke|nessuno|  
|Hyperlink|Invoke|Value|nessuno|  
|Image|nessuno|GridItem, TableItem|Invoke, SelectionItem|  
|List|nessuno|Grid, MultipleView, Scroll, Selection|Tabella|  
|ListItem|SelectionItem|ExpandCollapse, GridItem, Invoke, ScrollItem, Toggle, Value|nessuno|  
|Menu|nessuno|Nessuna|nessuno|  
|MenuBar|nessuno|ExpandCollapse, Dock, Transform|nessuno|  
|MenuItem|nessuno|ExpandCollapse, Invoke, SelectionItem, Toggle|nessuno|  
|Pane|nessuno|Dock Scroll, Transform|Finestra|  
|ProgressBar|nessuno|RangeValue, Value|nessuno|  
|RadioButton|SelectionItem|nessuno|Toggle|  
|ScrollBar|nessuno|RangeValue|Scroll|  
|Separatore|nessuno|Nessuna|nessuno|  
|Slider|nessuno|RangeValue, Selection, Value|nessuno|  
|Spinner|nessuno|RangeValue, Selection, Value|nessuno|  
|Pulsante di menu combinato|Invoke, ExpandCollapse|nessuno|nessuno|  
|StatusBar|nessuno|Grid|nessuno|  
|Scheda|Selection|Scroll|nessuno|  
|TabItem|SelectionItem|nessuno|Invoke|  
|Tabella|Grid, GridItem, Table, TableItem|nessuno|nessuno|  
|Testo|nessuno|GridItem, TableItem, Text|Value|  
|Thumb|Transform|nessuno|nessuno|  
|TitleBar|nessuno|Nessuna|nessuno|  
|ToolBar|nessuno|Dock, ExpandCollapse, Transform|nessuno|  
|ToolTip|nessuno|Text, Window|nessuno|  
|Tree|nessuno|Scroll, Selection|nessuno|  
|TreeItem|ExpandCollapse|Invoke, ScrollItem, SelectionItem, Toggle|nessuno|  
|Window|Transform, Window|Dock|nessuno|  
  
> [!NOTE]
>  Se un tipo di controllo non dispone di pattern di controllo supportati ma ha uno o più pattern di controllo supportati in modo condizionale, uno dei pattern di controllo condizionali risulterà sempre supportato.  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-overview.md)
