---
title: Comportamento predefinito di tastiera e mouse nel controllo DataGrid
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGrid [WPF], keyboard behavior
- DataGrid [WPF], mouse behavior
- keyboard behavior [WPF], DataGrid
- mouse behavior [WPF], DataGrid
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ddbbab88a22a4350626a36f79236aab67da24a7f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="default-keyboard-and-mouse-behavior-in-the-datagrid-control"></a>Comportamento predefinito di tastiera e mouse nel controllo DataGrid
Questo argomento viene descritto come è possibile interagire con il <xref:System.Windows.Controls.DataGrid> controllo usando la tastiera e mouse.  
  
 Interazioni tipiche con i <xref:System.Windows.Controls.DataGrid> includono navigazione, selezione e la modifica. Comportamento di selezione è interessato dal <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> e <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> proprietà. I valori predefiniti che causano il comportamento descritto in questo argomento sono <xref:System.Windows.Controls.DataGridSelectionMode.Extended?displayProperty=nameWithType> e <xref:System.Windows.Controls.DataGridSelectionUnit.FullRow?displayProperty=nameWithType>. Modifica di questi valori potrebbe causare un comportamento diverso rispetto a quanto descritto. Quando una cella è in modalità di modifica, il controllo di modifica potrebbe sostituire il comportamento della tastiera standard di <xref:System.Windows.Controls.DataGrid>.  
  
## <a name="default-keyboard-behavior"></a>Comportamento predefinito della tastiera  
 La tabella seguente elenca il comportamento predefinito della tastiera per il <xref:System.Windows.Controls.DataGrid>.  
  
|Tasto o combinazione|Descrizione|  
|----------------------------|-----------------|  
|Freccia GIÙ|Sposta lo stato attivo alla cella direttamente sotto la cella corrente. Se lo stato attivo è nell'ultima riga, premere il tasto freccia giù non esegue alcuna operazione.|  
|Freccia SU|Sposta lo stato attivo per la cella immediatamente sopra la cella corrente. Se lo stato attivo è nella prima riga, premere la freccia non esegue alcuna operazione.|  
|FRECCIA SINISTRA|Sposta lo stato attivo alla cella nella riga precedente. Se lo stato attivo è nella prima cella nella riga, premere la freccia sinistra non esegue alcuna operazione.|  
|FRECCIA DESTRA|Sposta lo stato attivo alla cella nella riga successiva. Se lo stato attivo è nell'ultima cella nella riga, premere la freccia destra non esegue alcuna operazione.|  
|HOME|Sposta lo stato attivo alla prima cella nella riga corrente.|  
|FINE|Sposta lo stato attivo all'ultima cella nella riga corrente.|  
|PGGIÙ|Se non sono raggruppate in righe, scorre verso il basso il controllo per il numero di righe visualizzate in modo completo. Sposta lo stato attivo per l'ultima riga visualizzata completamente senza modificare le colonne.<br /><br /> Se sono raggruppate le righe, sposta lo stato attivo per l'ultima riga di <xref:System.Windows.Controls.DataGrid> senza modificare le colonne.|  
|PGSU|Se non sono raggruppate in righe, consente di scorrere il controllo verso l'alto il numero di righe visualizzate in modo completo. Spostare lo stato attivo alla prima riga visualizzata senza modificare le colonne.<br /><br /> Se sono raggruppate le righe, sposta lo stato attivo per la prima riga di <xref:System.Windows.Controls.DataGrid> senza modificare le colonne.|  
|TAB|Sposta lo stato attivo alla cella successiva nella riga corrente. Se lo stato attivo è nell'ultima cella della riga, sposta lo stato attivo alla prima cella nella riga successiva. Se lo stato attivo è nell'ultima cella nel controllo, sposta lo stato attivo al controllo successivo nell'ordine di tabulazione del contenitore padre.<br /><br /> Se la cella corrente è in modalità di modifica e premendo TAB lo stato attivo per abbandonare la riga corrente, qualsiasi modifica apportata alla riga viene eseguito il commit prima che venga modificato lo stato attivo.|  
|MAIUSC+TAB|Sposta lo stato attivo alla cella precedente nella riga corrente. Se lo stato attivo è già nella prima cella della riga, sposta lo stato attivo all'ultima cella della riga precedente. Se lo stato attivo è nella prima cella nel controllo, sposta lo stato attivo al controllo precedente nell'ordine di tabulazione del contenitore padre.<br /><br /> Se la cella corrente è in modalità di modifica e premendo TAB lo stato attivo per abbandonare la riga corrente, qualsiasi modifica apportata alla riga viene eseguito il commit prima che venga modificato lo stato attivo.|  
|CTRL+freccia GIÙ|Sposta lo stato attivo all'ultima cella della colonna corrente.|  
|CTRL+FRECCIA SU|Sposta lo stato attivo alla prima cella della colonna corrente.|  
|CTRL+freccia DESTRA|Sposta lo stato attivo all'ultima cella nella riga corrente.|  
|CTRL+freccia SINISTRA|Sposta lo stato attivo alla prima cella nella riga corrente.|  
|CTRL + HOME|Sposta lo stato attivo alla prima cella nel controllo.|  
|CTRL + FINE|Sposta lo stato attivo all'ultima cella nel controllo.|  
|CTRL+PGGIÙ|Uguale a PGGIÙ.|  
|CTRL+PGSU|Uguale a PGSU.|  
|F2|Se il <xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=nameWithType> proprietà `false` e <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=nameWithType> proprietà `false` per la colonna corrente, pone la cella corrente in modalità di modifica.|  
|INVIO|Esegue il commit di tutte le modifiche alla cella corrente e alla riga e sposta lo stato attivo alla cella direttamente sotto la cella corrente. Se lo stato attivo è nell'ultima riga, esegue il commit di tutte le modifiche senza spostare lo stato attivo.|  
|ESC|Se il controllo è in modalità di modifica, Annulla la modifica e vengono annullate le modifiche apportate nel controllo. Se l'origine dati sottostante implementa <xref:System.ComponentModel.IEditableObject>, se si preme ESC Annulla la modalità di modifica per l'intera riga.|  
|BACKSPACE|Elimina il carattere prima del cursore quando si modifica una cella.|  
|DELETE|Elimina il carattere dopo il cursore quando si modifica una cella.|  
|CTRL+INVIO|Esegue il commit di tutte le modifiche alla cella corrente senza spostare lo stato attivo.|  
|CTRL+A|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostato su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, seleziona tutte le righe di <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="selection-keys"></a>Tasti di selezione  
 Se il <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostata su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, non modifica il comportamento di navigazione, ma si sposta con la tastiera tenendo premuto il tasto MAIUSC (CTRL + MAIUSC incluso) verrà modificata una selezione di più righe. Prima dello spostamento, il controllo Contrassegna la riga corrente come una riga di ancoraggio. Quando si Esplora premuto il tasto MAIUSC, la selezione include tutte le righe tra la riga di ancoraggio e la riga corrente.  
  
 Le seguenti chiavi selezione modificare la selezione di più righe.  
  
-   MAIUSC+freccia GIÙ  
  
-   MAIUSC+freccia SU  
  
-   MAIUSC+PGGIÙ  
  
-   MAIUSC+PGSU  
  
-   CTRL+MAIUSC+freccia GIÙ  
  
-   CTRL+MAIUSC+freccia SU  
  
-   CTRL + MAIUSC + HOME  
  
-   CTRL + MAIUSC + FINE  
  
## <a name="default-mouse-behavior"></a>Comportamento predefinito del Mouse  
 La tabella seguente elenca il comportamento predefinito del mouse per il <xref:System.Windows.Controls.DataGrid>.  
  
|Azione del mouse|Descrizione|  
|------------------|-----------------|  
|Fare clic su una riga non selezionata|Rende la riga selezionata la riga corrente e la cella selezionata, la cella corrente.|  
|Fare clic sulla cella corrente|Pone la cella corrente in modalità di modifica.|  
|Trascinare una cella di intestazione di colonna|Se il <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=nameWithType> proprietà `true` e <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=nameWithType> proprietà `true` per la colonna corrente, la colonna viene spostata in modo che possono essere eliminato in una nuova posizione.|  
|Trascinare un separatore di intestazione di colonna|Se il <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> proprietà `true` e <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> proprietà `true` per la colonna corrente, la colonna viene ridimensionata.|  
|Fare doppio clic sul separatore di intestazione di colonna|Se il <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> proprietà è `true` e <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> proprietà `true` per la colonna corrente, ridimensiona automaticamente la colonna con il <xref:System.Windows.Controls.DataGridLength.Auto%2A> modalità di ridimensionamento.|  
|Fare clic su una cella di intestazione di colonna|Se il <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=nameWithType> proprietà `true` e <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=nameWithType> proprietà `true` per la colonna corrente, Ordina la colonna.<br /><br /> Fare clic sull'intestazione di una colonna già ordinata verrà invertire la direzione di ordinamento della colonna.<br /><br /> Premere il tasto MAIUSC mentre facendo clic sulle intestazioni di colonna più verrà ordinato in base a più colonne nell'ordine selezionato.|  
|CTRL + clic su una riga|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostato su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, viene modificata una selezione di più righe non contigue.<br /><br /> Se la riga è già selezionata, la riga verrà deselezionata.|  
|MAIUSC + clic su una riga|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostato su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, viene modificata una selezione di più righe contigua.|  
|Fare clic su un'intestazione di gruppo di righe|Espande o comprime il gruppo.|  
|Fare clic sul pulsante nell'angolo superiore sinistro di selezionare tutte le<xref:System.Windows.Controls.DataGrid>|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostato su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, seleziona tutte le righe di <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="mouse-selection"></a>Selezione del mouse  
 Se il <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostata su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, fare clic su una riga tenendo premuto CTRL o MAIUSC verrà modificata la selezione di più righe.  
  
 Quando si fa clic su una riga tenendo premuto il tasto CTRL, la riga viene modificato lo stato di selezione mentre tutte le altre righe mantengono lo stato di selezione corrente. Questa operazione per selezionare le righe non adiacenti.  
  
 Quando si fa clic su una riga tenendo premuto il tasto MAIUSC, la selezione include tutte le righe tra la riga corrente e si trova in corrispondenza della posizione della riga corrente prima di fare clic su una riga di ancoraggio. Si seleziona il tasto MAIUSC modifica la riga corrente, ma non la riga di ancoraggio. Questa operazione per selezionare un intervallo di righe adiacenti.  
  
 CTRL + MAIUSC possono essere combinati per selezionare gli intervalli non adiacenti di righe adiacenti. A tale scopo, selezionare il primo intervallo premendo MAIUSC + clic come descritto in precedenza. Dopo aver selezionato il primo intervallo di righe, utilizzare CTRL + clic per selezionare la prima riga nell'intervallo successivo e quindi l'ultima riga nell'intervallo successivo tenendo premuto il tasto CTRL + MAIUSC.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.DataGrid>  
 <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>
