---
title: Mapping dei pattern di controllo per i client di automazione interfaccia utente
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 48298cb8d89958c701d7150aeb497e82d565bde1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433866"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Mapping dei pattern di controllo per i client di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono elencati i tipi di controllo e i pattern di controllo associati.  
  
 Nella tabella seguente i pattern di controllo sono organizzati nelle categorie seguenti:  
  
- Supportato. Il controllo deve supportare questo il pattern di controllo.  
  
- Supporto condizionale. Il controllo può supportare questo pattern di controllo a seconda dello stato del controllo.  
  
- Non supportato. Il controllo non supporta questo pattern di controllo. I controlli personalizzati possono supportare questo pattern di controllo.  
  
> [!NOTE]
> Alcuni controlli sono caratterizzati dal supporto condizionale per diversi pattern di controllo a seconda della funzionalità del controllo. Ad esempio, il controllo voce di menu prevede il supporto condizionale per il pattern di controllo <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>o <xref:System.Windows.Automation.SelectionItemPattern> a seconda della relativa funzione nel controllo menu.  
  
<a name="control_mapping_clients"></a>   
## <a name="ui-automation-control-patterns-for-clients"></a>Pattern di controllo di automazione interfaccia utente per i client  
  
|Tipo di controllo|Supportato|Supporto condizionale|Non supportato|  
|------------------|---------------|-------------------------|-------------------|  
|Pulsante|Nessuna|Invoke, Toggle, ExpandCollapse|Nessuna|  
|Calendar|Grid, Table|Selection, Scroll|Valore|  
|Casella di controllo|Toggle|Nessuna|Nessuna|  
|ComboBox|ExpandCollapse|Selection, Value|Scroll|  
|DataGrid|Grid|Scroll, Selection, Table|Nessuna|  
|DataItem|SelectionItem|ExpandCollapse, GridItem, ScrollItem, Table, Toggle, Value|Nessuna|  
|Documento|Testo|Scroll, Value|Nessuna|  
|Edit|Nessuna|Text, RangeValue, Value|Nessuna|  
|Gruppo|Nessuna|ExpandCollapse|Nessuna|  
|Intestazione|Nessuna|Trasforma|Nessuna|  
|HeaderItem|Nessuna|Transform, Invoke|Nessuna|  
|Hyperlink|Richiamare|Valore|Nessuna|  
|Immagine|Nessuna|GridItem, TableItem|Invoke, SelectionItem|  
|Elenco|Nessuna|Grid, MultipleView, Scroll, Selection|Tabella|  
|ListItem|SelectionItem|ExpandCollapse, GridItem, Invoke, ScrollItem, Toggle, Value|Nessuna|  
|Menu|Nessuna|Nessuna|Nessuna|  
|Barra dei menu|Nessuna|ExpandCollapse, Dock, Transform|Nessuna|  
|Voce di menu|Nessuna|ExpandCollapse, Invoke, SelectionItem, Toggle|Nessuna|  
|Riquadro|Nessuna|Dock Scroll, Transform|Finestra|  
|ProgressBar|Nessuna|RangeValue, Value|Nessuna|  
|Pulsante di opzione|SelectionItem|Nessuna|Toggle|  
|ScrollBar|Nessuna|RangeValue|Scroll|  
|Separatore|Nessuna|Nessuna|Nessuna|  
|Dispositivo di scorrimento|Nessuna|RangeValue, Selection, Value|Nessuna|  
|Spinner|Nessuna|RangeValue, Selection, Value|Nessuna|  
|Pulsante di menu combinato|Invoke, ExpandCollapse|Nessuna|Nessuna|  
|Barra di stato|Nessuna|Grid|Nessuna|  
|Tab|Selezione|Scroll|Nessuna|  
|TabItem|SelectionItem|Nessuna|Richiamare|  
|Tabella|Grid, GridItem, Table, TableItem|Nessuna|Nessuna|  
|Testo|Nessuna|GridItem, TableItem, Text|Valore|  
|Visualizzazione di anteprima|Trasforma|Nessuna|Nessuna|  
|Barra del titolo|Nessuna|Nessuna|Nessuna|  
|ToolBar|Nessuna|Dock, ExpandCollapse, Transform|Nessuna|  
|ToolTip|Nessuna|Text, Window|Nessuna|  
|Struttura ad albero|Nessuna|Scroll, Selection|Nessuna|  
|TreeItem|ExpandCollapse|Invoke, ScrollItem, SelectionItem, Toggle|Nessuna|  
|Finestra|Transform, Window|Dock|Nessuna|  
  
> [!NOTE]
> Se un tipo di controllo non dispone di pattern di controllo supportati ma ha uno o più pattern di controllo supportati in modo condizionale, uno dei pattern di controllo condizionali risulterà sempre supportato.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica di automazione interfaccia utente](ui-automation-overview.md)
