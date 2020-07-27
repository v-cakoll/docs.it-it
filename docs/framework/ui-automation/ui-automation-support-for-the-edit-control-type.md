---
title: Supporto di automazione interfaccia utente per il tipo di controllo Edit
description: Ottenere informazioni sul supporto di automazione interfaccia utente per il tipo di controllo Edit. Informazioni sulla struttura ad albero, le proprietà, i pattern di controllo e gli eventi di richiesti.
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Edit
- Edit control type
- UI Automation, Edit control type
ms.assetid: 6db9d231-c0a0-4e17-910e-ac80357f774f
ms.openlocfilehash: 6c404786d58cfcb4cc7dabd982eea33694b7cd0b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167943"
---
# <a name="ui-automation-support-for-the-edit-control-type"></a>Supporto di automazione interfaccia utente per il tipo di controllo Edit

> [!NOTE]
> Questa documentazione è destinata agli sviluppatori di .NET Framework che vogliono usare le classi gestite di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] definite nello spazio dei nomi <xref:System.Windows.Automation>. Per informazioni aggiornate su [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], vedere [Windows Automation API: automazione interfaccia utente](/windows/win32/winauto/entry-uiauto-win32).

In questo argomento vengono fornite informazioni sul supporto di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo di modifica. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]un tipo di controllo è un set di condizioni che un controllo deve soddisfare per usare la proprietà <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> . Le condizioni includono linee guida specifiche per la struttura ad albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , i valori delle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] e i pattern di controllo.

I controlli di modifica consentono a un utente di visualizzare e modificare una semplice riga di testo senza il supporto del formato RTF.

Nelle sezioni seguenti vengono definiti la struttura ad albero, le proprietà, i pattern di controllo e gli eventi di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] per il tipo di controllo di modifica. I [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requisiti di si applicano a tutti i controlli di modifica, sia [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Win32 che Windows Forms.

<a name="Required_UI_Automation_Tree_Structure"></a>

## <a name="required-ui-automation-tree-structure"></a>Struttura ad albero di automazione interfaccia utente obbligatoria

Nella tabella seguente viene illustrata la visualizzazione controlli e la visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] relativo ai controlli di modifica e viene descritto il possibile contenuto di ogni visualizzazione. Per altre informazioni sull'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Tree Overview](ui-automation-tree-overview.md).

|Visualizzazione controlli|Visualizzazione contenuto|
|------------------|------------------|
|Modifica|Modifica|

I controlli che implementano il tipo di controllo di modifica non includeranno alcuna barra di scorrimento nella visualizzazione controlli dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] perché si tratta di un controllo a riga singola. In alcuni scenari di layout una singola riga di testo può essere interrotta da un ritorno a capo. Il tipo di controllo di modifica è ideale per contenere piccole quantità di testo modificabile o selezionabile.

<a name="Required_UI_Automation_Properties"></a>

## <a name="required-ui-automation-properties"></a>Proprietà di automazione interfaccia utente obbligatorie

La tabella seguente elenca le proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] il cui valore o la cui definizione è particolarmente rilevante per i controlli di modifica. Per altre informazioni sulle proprietà di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , vedere [UI Automation Properties for Clients](ui-automation-properties-for-clients.md).

|Proprietà di[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Valore|Note|
|------------------------------------------------------------------------------------|-----------|-----------|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Vedere le note.|Il valore di questa proprietà deve essere univoco in tutti i controlli in un'applicazione.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Vedere le note.|Il rettangolo più esterno che contiene l'intero controllo.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Vedere le note.|Il controllo di modifica deve disporre di un punto selezionabile che rende disponibile lo stato attivo per l'input alla parte di modifica del controllo quando un utente fa clic su tale punto.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Vedere le note.|Se il controllo può ricevere lo stato attivo, deve supportare questa proprietà.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Vedere le note.|Il nome del controllo di modifica viene in genere generato da un'etichetta di testo statico. Se non è presente alcuna etichetta di testo statico, un valore di proprietà per `Name` deve essere assegnato dallo sviluppatore dell'applicazione. La proprietà `Name` non deve mai includere il contenuto testuale del controllo di modifica.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Vedere le note.|Se è presente un'etichetta di testo statico associata al controllo, questa proprietà deve esporre un riferimento a tale controllo. Se il controllo testo è un sottocomponente di un altro controllo, non avrà una proprietà `LabeledBy` impostata.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Modifica|Questo valore è uguale per tutti i framework dell' [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|"edit"|Stringa localizzata corrispondente al tipo di controllo Edit.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Il controllo di modifica viene sempre incluso nella visualizzazione contenuto dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Il controllo di modifica viene sempre incluso nella visualizzazione controlli dell'albero di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] .|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsPasswordProperty>|Vedere le note.|Deve essere impostata su true nei controlli di modifica che contengono password. Se un controllo di modifica include contenuto di tipo Password, questa proprietà può essere usata da una utilità per la lettura dello schermo per determinare se le sequenze di tasti devono essere lette mentre l'utente digita il testo.|

<a name="Required_UI_Automation_Control_Patterns"></a>

## <a name="required-ui-automation-control-patterns-and-properties"></a>Pattern di controllo e proprietà obbligatori per l'automazione interfaccia utente

La tabella seguente elenca i pattern di controllo che devono essere supportati da tutti i controlli di modifica. Per altre informazioni sui pattern di controllo, vedere [UI Automation Control Patterns Overview](ui-automation-control-patterns-overview.md).

|Pattern di controllo/proprietà del pattern di controllo|Supporto/valore|Note|
|-----------------------------------------------|--------------------|-----------|
|<xref:System.Windows.Automation.Provider.ITextProvider>|Dipende da|I controlli di modifica devono supportare il pattern di controllo Text in quanto le informazioni testuali dettagliate devono sempre essere disponibili per i client.|
|<xref:System.Windows.Automation.Provider.IValueProvider>|Dipende da|Tutti i controlli di modifica che accettano una stringa devono esporre il pattern Value.|
|<xref:System.Windows.Automation.Provider.IValueProvider.IsReadOnly%2A>|Vedere le note.|Questa proprietà deve essere impostata per indicare se il controllo può avere un valore impostato a livello di codice oppure se è modificabile dall'utente.|
|<xref:System.Windows.Automation.Provider.IValueProvider.Value%2A>|Vedere le note.|Questa proprietà restituirà il contenuto testuale del controllo di modifica. Se `IsPasswordProperty` è impostata su `true`, questa proprietà deve generare `InvalidOperationException` quando richiesto.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Dipende da|Tutti i controlli di modifica che accettano un intervallo numerico devono esporre il pattern di controllo RangeValue.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Minimum%2A>|Vedere le note.|Questa proprietà deve essere il valore più piccolo su cui può essere impostato il contenuto del controllo di modifica.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Maximum%2A>|Vedere le note.|Questa proprietà deve essere il valore più grande su cui può essere impostato il contenuto del controllo di modifica.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.SmallChange%2A>|Vedere le note.|Questa proprietà deve indicare il numero di cifre decimali che è possibile impostare per il valore. Se il controllo di modifica accetta solo valori integer, impostare `SmallChangeProperty` su 1. Se il controllo di modifica accetta un intervallo compreso tra 1,0 e 2,0, impostare `SmallChangeProperty` su 0,1. Se il controllo di modifica accetta un intervallo compreso tra 1,0 e 2,0, impostare `SmallChangeProperty` su 0,001.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.LargeChange%2A>|`Null`|Questa proprietà non deve essere esposta in un controllo di modifica.|
|<xref:System.Windows.Automation.Provider.IRangeValueProvider.Value%2A>|Vedere le note.|Questa proprietà indicherà il contenuto numerico del controllo di modifica. Quando un valore più preciso viene impostato da un client di [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] all'interno degli intervalli specificati nelle proprietà `Minimum` e `Maximum` , la proprietà Value verrà automaticamente arrotondata al valore accettato più vicino.|

<a name="Required_UI_Automation_Events"></a>

## <a name="required-ui-automation-events"></a>Eventi di automazione interfaccia utente obbligatori

La tabella seguente elenca gli eventi dell' [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] che devono essere supportati da tutti i controlli di modifica. Per altre informazioni sugli eventi, vedere [UI Automation Events Overview](ui-automation-events-overview.md).

|o[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]|Supporto|Note|
|---------------------------------------------------------------------------------|-------------|-----------|
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Richiesto|Nessuno|
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextSelectionChangedEvent>|Richiesto|Nessuno|
|<xref:System.Windows.Automation.TextPatternIdentifiers.TextChangedEvent>|Richiesto|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> .|Richiesto|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> .|Richiesto|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> .|Richiesto|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> .|Richiesto|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> .|Dipende da|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> .|Mai|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> .|Mai|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> .|Mai|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> .|Mai|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> .|Mai|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> .|Mai|Nessuno|
|Evento di modifica della proprietà<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty> .|Dipende da|Se il controllo supporta il pattern di controllo RangeValue, deve supportare questo evento.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Richiesto|Nessuno|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Richiesto|Nessuno|

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Automation.ControlType.Edit>
- [Cenni preliminari sui tipi di controllo per l'automazione interfaccia utente](ui-automation-control-types-overview.md)
- [Cenni preliminari su automazione interfaccia utente](ui-automation-overview.md)
