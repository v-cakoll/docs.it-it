---
title: Mapping dei pattern di controllo per i client di automazione interfaccia utente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
caps.latest.revision: "18"
author: Xansky
ms.author: mhopkins
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 6a5f9d115c601775cc4f5b1c61d71d739f7a405b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Mapping dei pattern di controllo per i client di automazione interfaccia utente
> [!NOTE]
>  Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere l'argomento sull' [API Automazione interfaccia utente di Windows](http://go.microsoft.com/fwlink/?LinkID=156746).  
  
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
|Button|Nessuno|Invoke, Toggle, ExpandCollapse|Nessuno|  
|Calendar|Grid, Table|Selection, Scroll|Value|  
|CheckBox|Toggle|nessuno|nessuno|  
|ComboBox|ExpandCollapse|Selection, Value|Scroll|  
|DataGrid|Grid|Scroll, Selection, Table|Nessuno|  
|DataItem|SelectionItem|ExpandCollapse, GridItem, ScrollItem, Table, Toggle, Value|Nessuno|  
|Document|Testo|Scroll, Value|Nessuno|  
|Edit|nessuno|Text, RangeValue, Value|None|  
|Group|nessuno|ExpandCollapse|nessuno|  
|Header|nessuno|Transform|nessuno|  
|HeaderItem|Nessuno|Transform, Invoke|nessuno|  
|Hyperlink|Invoke|Value|nessuno|  
|Image|Nessuno|GridItem, TableItem|Invoke, SelectionItem|  
|List|nessuno|Grid, MultipleView, Scroll, Selection|Table|  
|ListItem|SelectionItem|ExpandCollapse, GridItem, Invoke, ScrollItem, Toggle, Value|Nessuno|  
|Menu|nessuno|Nessuna|Nessuno|  
|MenuBar|Nessuno|ExpandCollapse, Dock, Transform|nessuno|  
|MenuItem|Nessuno|ExpandCollapse, Invoke, SelectionItem, Toggle|Nessuno|  
|Pane|Nessuno|Dock Scroll, Transform|Window|  
|ProgressBar|Nessuno|RangeValue, Value|nessuno|  
|RadioButton|SelectionItem|nessuno|Toggle|  
|ScrollBar|nessuno|RangeValue|Scroll|  
|Separatore|Nessuno|Nessuna|Nessuno|  
|Slider|nessuno|RangeValue, Selection, Value|Nessuno|  
|Spinner|nessuno|RangeValue, Selection, Value|nessuno|  
|Pulsante di menu combinato|Invoke, ExpandCollapse|Nessuno|nessuno|  
|StatusBar|Nessuno|Grid|Nessuno|  
|Tab|Selection|Scroll|nessuno|  
|TabItem|SelectionItem|nessuno|Invoke|  
|Table|Grid, GridItem, Table, TableItem|Nessuno|nessuno|  
|Testo|Nessuno|GridItem, TableItem, Text|Valore|  
|Thumb|Transform|Nessuno|nessuno|  
|TitleBar|Nessuno|Nessuna|nessuno|  
|ToolBar|Nessuno|Dock, ExpandCollapse, Transform|nessuno|  
|ToolTip|nessuno|Text, Window|nessuno|  
|Tree|Nessuno|Scroll, Selection|nessuno|  
|TreeItem|ExpandCollapse|Invoke, ScrollItem, SelectionItem, Toggle|Nessuno|  
|Window|Transform, Window|Dock|nessuno|  
  
> [!NOTE]
>  Se un tipo di controllo non dispone di pattern di controllo supportati ma ha uno o più pattern di controllo supportati in modo condizionale, uno dei pattern di controllo condizionali risulterà sempre supportato.  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di automazione interfaccia utente](../../../docs/framework/ui-automation/ui-automation-overview.md)
