---
title: Comportamento predefinito di tastiera e mouse nel controllo DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid [WPF], keyboard behavior
- DataGrid [WPF], mouse behavior
- keyboard behavior [WPF], DataGrid
- mouse behavior [WPF], DataGrid
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
ms.openlocfilehash: 6be464ce85bd3ba91dd6e6cc810ec7d04edc0c3d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083322"
---
# <a name="default-keyboard-and-mouse-behavior-in-the-datagrid-control"></a>Comportamento predefinito di tastiera e mouse nel controllo DataGrid
In questo argomento descrive come gli utenti possono interagire con il <xref:System.Windows.Controls.DataGrid> controllo usando la tastiera e mouse.  
  
 Interazioni tipiche con i <xref:System.Windows.Controls.DataGrid> includono navigazione, selezione e modifica. Comportamento di selezione è influenzato il <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> e <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> proprietà. I valori predefiniti che causano il comportamento descritto in questo argomento sono <xref:System.Windows.Controls.DataGridSelectionMode.Extended?displayProperty=nameWithType> e <xref:System.Windows.Controls.DataGridSelectionUnit.FullRow?displayProperty=nameWithType>. Modifica di questi valori potrà causare un comportamento che è diverso da quella descritta. Quando una cella è in modalità di modifica, il controllo di modifica potrebbe quindi sostituire il comportamento della tastiera standard il <xref:System.Windows.Controls.DataGrid>.  
  
## <a name="default-keyboard-behavior"></a>Comportamento predefinito della tastiera  
 La tabella seguente elenca il comportamento predefinito della tastiera per il <xref:System.Windows.Controls.DataGrid>.  
  
|Tasto o della combinazione|Descrizione|  
|----------------------------|-----------------|  
|Freccia GIÙ|Sposta lo stato attivo per la cella posta immediatamente sotto la cella corrente. Se lo stato attivo è nell'ultima riga, premendo il tasto freccia giù non esegue alcuna operazione.|  
|Freccia SU|Sposta lo stato attivo sulla cella immediatamente sopra la cella corrente. Se lo stato attivo è nella prima riga, premere la freccia verso l'alto non esegue alcuna operazione.|  
|FRECCIA SINISTRA|Sposta lo stato attivo alla cella nella riga precedente. Se lo stato attivo è nella prima cella nella riga, premendo il tasto freccia sinistra non esegue alcuna operazione.|  
|FRECCIA DESTRA|Sposta lo stato attivo sulla cella nella riga successiva. Se lo stato attivo è nell'ultima cella della riga, premendo il tasto freccia destra non esegue alcuna operazione.|  
|HOME|Sposta lo stato attivo alla prima cella nella riga corrente.|  
|FINE|Sposta lo stato attivo all'ultima cella nella riga corrente.|  
|PGGIÙ|Se non sono raggruppate in righe, scorre il controllo verso il basso per il numero di righe visualizzate in modo completo. Sposta lo stato attivo per l'ultima riga visualizzata completamente senza modificare le colonne.<br /><br /> Se vengono raggruppate in righe, si sposta lo stato attivo per l'ultima riga nel <xref:System.Windows.Controls.DataGrid> senza modificare le colonne.|  
|PGSU|Se non sono raggruppate in righe, scorre il controllo verso l'alto per il numero di righe visualizzate in modo completo. Sposta lo stato attivo alla prima riga visualizzata senza modificare le colonne.<br /><br /> Se vengono raggruppate in righe, sposta lo stato attivo alla prima riga il <xref:System.Windows.Controls.DataGrid> senza modificare le colonne.|  
|TAB|Sposta lo stato attivo alla cella successiva nella riga corrente. Se lo stato attivo è nell'ultima cella della riga, sposta lo stato attivo alla prima cella nella riga successiva. Se lo stato attivo è nell'ultima cella nel controllo, si sposta lo stato attivo al controllo successivo nell'ordine di tabulazione del contenitore padre.<br /><br /> Se la cella corrente è in modalità di modifica e premendo TAB lo stato attivo per spostare dalla riga corrente, tutte le modifiche apportate alla riga vanno eseguito il commit prima che venga modificato lo stato attivo.|  
|MAIUSC+TAB|Sposta lo stato attivo per la cella precedente nella riga corrente. Se lo stato attivo è già nella prima cella della riga, sposta lo stato attivo all'ultima cella nella riga precedente. Se lo stato attivo è nella prima cella nel controllo, si sposta lo stato attivo al controllo precedente nell'ordine di tabulazione del contenitore padre.<br /><br /> Se la cella corrente è in modalità di modifica e premendo TAB lo stato attivo per spostare dalla riga corrente, tutte le modifiche apportate alla riga vanno eseguito il commit prima che venga modificato lo stato attivo.|  
|CTRL+freccia GIÙ|Sposta lo stato attivo all'ultima cella nella colonna corrente.|  
|CTRL+FRECCIA SU|Sposta lo stato attivo alla prima cella nella colonna corrente.|  
|CTRL+freccia DESTRA|Sposta lo stato attivo all'ultima cella nella riga corrente.|  
|CTRL+freccia SINISTRA|Sposta lo stato attivo alla prima cella nella riga corrente.|  
|CTRL+HOME|Sposta lo stato attivo alla prima cella nel controllo.|  
|CTRL + FINE|Sposta lo stato attivo all'ultima cella nel controllo.|  
|CTRL+PGGIÙ|Uguale a PGGIÙ.|  
|CTRL+PGSU|Uguale a PGSU.|  
|F2|Se il <xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=nameWithType> proprietà è `false` e il <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=nameWithType> è di proprietà `false` per la colonna corrente, inserisce la cella corrente in modalità di modifica.|  
|INVIO|Esegue il commit di tutte le modifiche alla cella corrente e alla riga e sposta lo stato attivo per la cella posta immediatamente sotto la cella corrente. Se lo stato attivo è nell'ultima riga, esegue il commit di tutte le modifiche senza spostare lo stato attivo.|  
|ESC|Se il controllo è in modalità di modifica, Annulla la modifica e vengono annullate le modifiche apportate nel controllo. Se l'origine dati sottostante implementa <xref:System.ComponentModel.IEditableObject>, premendo ESC un secondo momento verrà annullata la modalità di modifica per l'intera riga.|  
|BACKSPACE|Elimina il carattere prima del cursore quando si modifica una cella.|  
|DELETE|Elimina i caratteri dopo il cursore quando si modifica una cella.|  
|CTRL+INVIO|Esegue il commit di tutte le modifiche alla cella corrente senza spostare lo stato attivo.|  
|CTRL+A|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostata su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, consente di selezionare tutte le righe di <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="selection-keys"></a>Tasti di selezione  
 Se il <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostata su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, il comportamento di navigazione rimane invariato, ma lo spostamento con la tastiera tenendo premuto il tasto MAIUSC (CTRL + MAIUSC inclusi) viene modificata la selezione con più righe. Prima dello spostamento, il controllo Contrassegna la riga corrente come una riga di ancoraggio. Quando si passa il tasto MAIUSC, la selezione include tutte le righe tra la riga di ancoraggio e la riga corrente.  
  
 Le chiavi di selezione seguente modificata la selezione di più righe.  
  
-   MAIUSC+freccia GIÙ  
  
-   MAIUSC+freccia SU  
  
-   MAIUSC+PGGIÙ  
  
-   MAIUSC+PGSU  
  
-   CTRL+MAIUSC+freccia GIÙ  
  
-   CTRL+MAIUSC+freccia SU  
  
-   CTRL + MAIUSC + HOME  
  
-   CTRL + MAIUSC + END  
  
## <a name="default-mouse-behavior"></a>Comportamento predefinito del Mouse  
 La tabella seguente elenca il comportamento del mouse predefinito per il <xref:System.Windows.Controls.DataGrid>.  
  
|Azione del mouse|Descrizione|  
|------------------|-----------------|  
|Fare clic su una riga non selezionata|Rende la riga selezionata la riga corrente e la cella selezionata la cella corrente.|  
|Fare clic sulla cella corrente|Inserisce la cella corrente in modalità di modifica.|  
|Trascinare una cella di intestazione di colonna|Se il <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=nameWithType> proprietà viene `true` e il <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=nameWithType> è di proprietà `true` per la colonna corrente, la colonna viene spostata in modo che sia possibile rilasciarla in una nuova posizione.|  
|Trascinare un separatore dell'intestazione colonna|Se il <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> proprietà viene `true` e il <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> è di proprietà `true` per la colonna corrente, la colonna viene ridimensionata.|  
|Fare doppio clic sul separatore dell'intestazione di colonna|Se il <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> proprietà è `true` e il <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> è di proprietà `true` per la colonna corrente, ridimensiona automaticamente la colonna con il <xref:System.Windows.Controls.DataGridLength.Auto%2A> la modalità di ridimensionamento.|  
|Fare clic su una cella di intestazione di colonna|Se il <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=nameWithType> proprietà è `true` e il <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=nameWithType> è di proprietà `true` Ordina la colonna per la colonna corrente.<br /><br /> Fare clic sull'intestazione di una colonna già ordinata invertirà la direzione di ordinamento della colonna.<br /><br /> Premendo il tasto MAIUSC quando facendo clic più intestazioni di colonna verrà ordinato in base a più colonne nell'ordine selezionato.|  
|CTRL + clic su una riga|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostata su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, viene modificata una selezione con più righe non contigue.<br /><br /> Se la riga è già selezionata, la riga verrà deselezionata.|  
|MAIUSC + clic su una riga|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostata su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, viene modificata una selezione con più righe contigue.|  
|Fare clic su un'intestazione di gruppo di righe|Espande o comprime il gruppo.|  
|Fare clic sul pulsante nell'angolo superiore sinistro di selezionare tutti i <xref:System.Windows.Controls.DataGrid>|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostata su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, consente di selezionare tutte le righe di <xref:System.Windows.Controls.DataGrid>.|  
  
## <a name="mouse-selection"></a>Selezione del mouse  
 Se il <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostata su <xref:System.Windows.Controls.DataGridSelectionMode.Extended>, facendo clic su una riga tenendo premuto il tasto CTRL o MAIUSC viene modificata la selezione con più righe.  
  
 Quando si fa clic su una riga mentre vengono premuti CTRL, la riga viene modificato lo stato di selezione tutte le altre righe mantenendo lo stato di selezione corrente. Questa operazione per selezionare righe non adiacenti.  
  
 Quando si fa clic su una riga tenendo premuto il tasto MAIUSC, la selezione include tutte le righe tra la riga corrente e che si trova in corrispondenza della posizione della riga corrente prima di fare clic su una riga di ancoraggio. Facendo clic successivamente sarà tenendo premuto il tasto MAIUSC modificare la riga corrente, ma non la riga di ancoraggio. Questa operazione per selezionare un intervallo di righe adiacenti.  
  
 È possibile combinare CTRL + MAIUSC per selezionare intervalli di righe adiacenti non adiacenti. A tale scopo, selezionare il primo intervallo usando MAIUSC + clic come descritto in precedenza. Dopo aver selezionato il primo intervallo di righe, usare CTRL + fare clic per selezionare la prima riga dell'intervallo successivo e quindi fare clic sull'ultima riga dell'intervallo successivo mentre vengono premuti CTRL + MAIUSC.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>
