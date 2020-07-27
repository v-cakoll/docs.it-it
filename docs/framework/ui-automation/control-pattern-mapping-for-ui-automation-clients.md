---
title: Mapping dei pattern di controllo per i client di automazione interfaccia utente
description: Visualizzare una tabella di mapping dei pattern di controllo per i client di automazione interfaccia utente. È possibile che le azioni per determinati tipi di controllo siano supportate, supportate in modo condizionale o non supportate.
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, for UI Automation clients
- UI Automation, clients, control patterns for
ms.assetid: 8b81645b-8be3-4e26-9c98-4fb0fceca06b
ms.openlocfilehash: 7673ce4ac88cc36a7c35e2e946a31d23b2ce6eca
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164178"
---
# <a name="control-pattern-mapping-for-ui-automation-clients"></a>Mapping dei pattern di controllo per i client di automazione interfaccia utente
> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).  
  
 In questo argomento vengono elencati i tipi di controllo e i pattern di controllo associati.  
  
 Nella tabella seguente i pattern di controllo sono organizzati nelle categorie seguenti:  
  
- Supportata. Il controllo deve supportare questo il pattern di controllo.  
  
- Supporto condizionale. Il controllo può supportare questo pattern di controllo a seconda dello stato del controllo.  
  
- Non supportata. Il controllo non supporta questo pattern di controllo. I controlli personalizzati possono supportare questo pattern di controllo.  
  
> [!NOTE]
> Alcuni controlli sono caratterizzati dal supporto condizionale per diversi pattern di controllo a seconda della funzionalità del controllo. Ad esempio, il controllo voce di menu prevede il supporto condizionale per il pattern di controllo <xref:System.Windows.Automation.InvokePattern>, <xref:System.Windows.Automation.ExpandCollapsePattern>, <xref:System.Windows.Automation.TogglePattern>o <xref:System.Windows.Automation.SelectionItemPattern> a seconda della relativa funzione nel controllo menu.  
  
<a name="control_mapping_clients"></a>
## <a name="ui-automation-control-patterns-for-clients"></a>Pattern di controllo di automazione interfaccia utente per i client  
  
|Tipo di controllo|Supportato|Supporto condizionale|Non Supportato|  
|------------------|---------------|-------------------------|-------------------|  
|Pulsante|Nessuno|Invoke, Toggle, ExpandCollapse|Nessuno|  
|Calendario|Grid, Table|Selection, Scroll|Valore|  
|CheckBox|Toggle|nessuno|nessuno|  
|ComboBox|ExpandCollapse|Selection, Value|Scroll|  
|Griglia dati|Grid|Scroll, Selection, Table|Nessuno|  
|DataItem|SelectionItem|ExpandCollapse, GridItem, ScrollItem, Table, Toggle, Value|Nessuno|  
|Document|Testo|Scroll, Value|Nessuno|  
|Modifica|Nessuno|Text, RangeValue, Value|Nessuno|  
|Group|Nessuno|ExpandCollapse|Nessuno|  
|Intestazione|Nessuno|Trasformare|Nessuno|  
|HeaderItem|Nessuno|Transform, Invoke|Nessuno|  
|Hyperlink|Invoke|Valore|Nessuno|  
|Immagine|Nessuno|GridItem, TableItem|Invoke, SelectionItem|  
|Elenco|Nessuno|Grid, MultipleView, Scroll, Selection|Tabella|  
|ListItem|SelectionItem|ExpandCollapse, GridItem, Invoke, ScrollItem, Toggle, Value|Nessuno|  
|Menu|nessuno|nessuno|nessuno|  
|Barra dei menu|Nessuno|ExpandCollapse, Dock, Transform|Nessuno|  
|MenuItem|Nessuno|ExpandCollapse, Invoke, SelectionItem, Toggle|Nessuno|  
|Riquadro|Nessuno|Dock Scroll, Transform|Finestra|  
|ProgressBar|Nessuno|RangeValue, Value|Nessuno|  
|RadioButton|SelectionItem|Nessuno|Toggle|  
|ScrollBar|Nessuno|RangeValue|Scroll|  
|Separatore|nessuno|nessuno|nessuno|  
|Dispositivo di scorrimento|Nessuno|RangeValue, Selection, Value|Nessuno|  
|Spinner|Nessuno|RangeValue, Selection, Value|Nessuno|  
|Pulsante di menu combinato|Invoke, ExpandCollapse|nessuno|nessuno|  
|Barra di stato|Nessuno|Grid|Nessuno|  
|Scheda|Selection|Scroll|Nessuno|  
|TabItem|SelectionItem|Nessuno|Invoke|  
|Tabella|Grid, GridItem, Table, TableItem|nessuno|nessuno|  
|Testo|Nessuno|GridItem, TableItem, Text|Valore|  
|Thumb|Trasformare|nessuno|nessuno|  
|TitleBar|nessuno|nessuno|nessuno|  
|ToolBar|Nessuno|Dock, ExpandCollapse, Transform|Nessuno|  
|ToolTip|Nessuno|Text, Window|Nessuno|  
|Albero|Nessuno|Scroll, Selection|Nessuno|  
|TreeItem|ExpandCollapse|Invoke, ScrollItem, SelectionItem, Toggle|Nessuno|  
|Finestra|Transform, Window|Dock|Nessuno|  
  
> [!NOTE]
> Se un tipo di controllo non dispone di pattern di controllo supportati ma ha uno o più pattern di controllo supportati in modo condizionale, uno dei pattern di controllo condizionali risulterà sempre supportato.  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari su automazione interfaccia utente](ui-automation-overview.md)
