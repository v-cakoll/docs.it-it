---
title: Gestione predefinita di tastiera e mouse nel controllo DataGridView Windows Forms
ms.date: 02/13/2018
helpviewer_keywords:
- data grids [Windows Forms], mouse handling
- DataGridView control [Windows Forms], navigation keys
- keyboards [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], keyboard handling
- mouse [Windows Forms], default handling in DataGridView control
- DataGridView control [Windows Forms], mouse handling
- navigation keys [Windows Forms], DataGridView control
ms.assetid: 4519b928-bfc8-4e8b-bb9c-b1e76a0ca552
ms.openlocfilehash: 97b8c8c3e418586bbc0053c358a2924484115a26
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69969136"
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Gestione predefinita di tastiera e mouse nel controllo DataGridView Windows Forms

Le tabelle seguenti descrivono come gli utenti possono interagire <xref:System.Windows.Forms.DataGridView> con il controllo tramite una tastiera e un mouse.  
  
> [!NOTE]
> Per personalizzare il comportamento della tastiera, è possibile gestire gli eventi della <xref:System.Windows.Forms.Control.KeyDown>tastiera standard, ad esempio. In modalità di modifica, tuttavia, il controllo di modifica ospitato riceve l'input da tastiera e gli eventi della tastiera non <xref:System.Windows.Forms.DataGridView> si verificano per il controllo. Per gestire gli eventi di controllo di modifica, alleghi i gestori al controllo di <xref:System.Windows.Forms.DataGridView.EditingControlShowing> modifica in un gestore eventi. In alternativa, è possibile personalizzare il comportamento della tastiera <xref:System.Windows.Forms.DataGridView> in una sottoclasse eseguendo <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> l' <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> override dei metodi e.  
  
## <a name="default-keyboard-handling"></a>Gestione della tastiera predefinita  
  
### <a name="basic-navigation-and-entry-keys"></a>Tasti di navigazione e di accesso di base  
  
|Tasto o combinazione di tasti|DESCRIZIONE|  
|----------------------------|-----------------|  
|Freccia GIÙ|Sposta lo stato attivo sulla cella immediatamente sotto la cella corrente. Se lo stato attivo si trova nell'ultima riga, non esegue alcuna operazione.|  
|FRECCIA SINISTRA|Sposta lo stato attivo sulla cella precedente della riga. Se lo stato attivo si trova nella prima cella della riga, non esegue alcuna operazione.|  
|FRECCIA DESTRA|Sposta lo stato attivo sulla cella successiva nella riga. Se lo stato attivo si trova nell'ultima cella della riga, non esegue alcuna operazione.|  
|Freccia SU|Sposta lo stato attivo sulla cella immediatamente sopra la cella corrente. Se lo stato attivo si trova nella prima riga, non esegue alcuna operazione.|  
|HOME|Sposta lo stato attivo sulla prima cella della riga corrente.|  
|FINE|Sposta lo stato attivo sull'ultima cella della riga corrente.|  
|PGGIÙ|Scorre il controllo verso il basso del numero di righe visualizzate completamente. Sposta lo stato attivo sull'ultima riga completamente visualizzata senza modificare le colonne.|  
|PGSU|Scorre il controllo verso l'alto in base al numero di righe visualizzate completamente. Sposta lo stato attivo sulla prima riga visualizzata senza modificare le colonne.|  
|TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà `false`è, sposta lo stato attivo sulla cella successiva nella riga corrente. Se lo stato attivo si trova già nell'ultima cella della riga, sposta lo stato attivo sulla prima cella nella riga successiva. Se lo stato attivo si trova nell'ultima cella del controllo, sposta lo stato attivo sul controllo successivo nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà `true`è, sposta lo stato attivo sul controllo successivo nell'ordine di tabulazione del contenitore padre.|  
|MAIUSC+TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà `false`è, sposta lo stato attivo sulla cella precedente nella riga corrente. Se lo stato attivo si trova già nella prima cella della riga, sposta lo stato attivo sull'ultima cella della riga precedente. Se lo stato attivo si trova nella prima cella del controllo, sposta lo stato attivo sul controllo precedente nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà `true`è, sposta lo stato attivo sul controllo precedente nell'ordine di tabulazione del contenitore padre.|  
|CTRL+TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà `false`è, sposta lo stato attivo sul controllo successivo nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà `true`è, sposta lo stato attivo sulla cella successiva nella riga corrente. Se lo stato attivo si trova già nell'ultima cella della riga, sposta lo stato attivo sulla prima cella nella riga successiva. Se lo stato attivo si trova nell'ultima cella del controllo, sposta lo stato attivo sul controllo successivo nell'ordine di tabulazione del contenitore padre.|  
|CTRL+MAIUSC+TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà `false`è, sposta lo stato attivo sul controllo precedente nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà `true`è, sposta lo stato attivo sulla cella precedente nella riga corrente. Se lo stato attivo si trova già nella prima cella della riga, sposta lo stato attivo sull'ultima cella della riga precedente. Se lo stato attivo si trova nella prima cella del controllo, sposta lo stato attivo sul controllo precedente nell'ordine di tabulazione del contenitore padre.|  
|CTRL + FRECCIA|Sposta lo stato attivo sulla cella più lontana nella direzione della freccia.|  
|CTRL + HOME|Sposta lo stato attivo sulla prima cella del controllo.|  
|CTRL + FINE|Sposta lo stato attivo sull'ultima cella del controllo.|  
|CTRL + PAGINA GIÙ/GIÙ|Uguale alla pagina giù o PGSU.|  
|F2|Inserisce la cella corrente in modalità di modifica della cella <xref:System.Windows.Forms.DataGridView.EditMode%2A> se il valore <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> della <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>proprietà è o.|
|F3|Ordina la colonna corrente se il <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> valore della proprietà <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>è. Equivale a fare clic sull'intestazione di colonna corrente. Disponibile a partire da .NET Framework 4.7.2. Per abilitare questa funzionalità, le applicazioni devono avere come destinazione .NET Framework 4.7.2 o versioni successive oppure esplicitamente esplicitamente i miglioramenti dell'accessibilità usando le opzioni AppContext.|  
|F4|Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewComboBoxCell>, inserisce la cella in modalità di modifica e visualizza l'elenco a discesa.|  
|ALT + FRECCIA SU/GIÙ|Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewComboBoxCell>, inserisce la cella in modalità di modifica e visualizza l'elenco a discesa.|  
|BARRA SPAZIATRICE|Se la cella corrente è <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>o <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, genera gli <xref:System.Windows.Forms.DataGridView.CellClick> eventi e <xref:System.Windows.Forms.DataGridView.CellContentClick> . Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewButtonCell>oggetto, viene anche premuto il pulsante. Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, modifica anche lo stato di selezione.|  
|INVIO|Consente di eseguire il commit di tutte le modifiche apportate alla cella e alla riga correnti e di spostare lo stato attivo sulla cella immediatamente sotto la cella corrente. Se lo stato attivo si trova nell'ultima riga, viene eseguito il commit di tutte le modifiche senza spostare lo stato attivo.|  
|ESC|Se il controllo è in modalità di modifica, Annulla la modifica. Se il controllo non è in modalità di modifica, Annulla tutte le modifiche apportate alla riga corrente se il controllo è associato a un'origine dati che supporta la modifica o la modalità virtuale è stata implementata con l'ambito di commit a livello di riga.|  
|BACKSPACE|Elimina il carattere prima del punto di inserimento durante la modifica di una cella.|  
|DELETE|Elimina il carattere dopo il punto di inserimento durante la modifica di una cella.|  
|CTRL+INVIO|Consente di eseguire il commit di tutte le modifiche apportate alla cella corrente senza spostare lo stato attivo. Consente inoltre di eseguire il commit di tutte le modifiche apportate alla riga corrente se il controllo è associato a un'origine dati che supporta la modifica o la modalità virtuale è stata implementata con l'ambito del commit a livello di riga.|  
|CTRL+0|Immette un <xref:System.DBNull.Value?displayProperty=nameWithType> valore nella cella corrente se la cella può essere modificata. Per impostazione predefinita, il valore di visualizzazione <xref:System.DBNull> per un valore <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> di cella corrisponde al valore della proprietà <xref:System.Windows.Forms.DataGridViewCellStyle> dell'oggetto attivo per la cella corrente.|  
  
### <a name="selection-keys"></a>Tasti di selezione

 Se la <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> proprietà è impostata su `false` e la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> proprietà è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, la modifica della cella corrente mediante i tasti di spostamento consente di modificare la selezione nella nuova cella. I tasti MAIUSC, CTRL e ALT non influiscono su questo comportamento.  
  
 Se è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, lo stesso comportamento si verifica ma con le aggiunte seguenti. <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
  
|Tasto o combinazione di tasti|DESCRIZIONE|  
|----------------------------|-----------------|  
|MAIUSC + BARRA SPAZIATRICE|Consente di selezionare la riga o la colonna completa (come fare clic sull'intestazione di riga o di colonna).|  
|tasto di navigazione (tasto di direzione, PGSU, HOME, fine)|Se viene selezionata una riga o una colonna completa, la modifica della cella corrente in una nuova riga o colonna consente di spostare la selezione nella nuova riga o colonna completa (a seconda della modalità di selezione).|  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `false` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, la modifica della cella corrente in una nuova riga o colonna tramite la tastiera sposta la selezione sulla nuova riga o colonna completa. I tasti MAIUSC, CTRL e ALT non influiscono su questo comportamento.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `true`, il comportamento di navigazione non cambia, ma lo spostamento con la tastiera mentre si preme MAIUSC (inclusa la combinazione di tasti CTRL + MAIUSC) modifica una selezione a più celle. Prima dell'inizio della navigazione, il controllo contrassegna la cella corrente come una cella di ancoraggio. Quando si sposta mentre si preme MAIUSC, la selezione include tutte le celle tra la cella di ancoraggio e la cella corrente. Se sono già state selezionate, le altre celle del controllo rimarranno selezionate, ma potrebbero essere deselezionate se la navigazione tramite tastiera le inserisce temporaneamente tra la cella di ancoraggio e la cella corrente.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `true` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, il comportamento della cella di ancoraggio e della cella corrente è lo stesso, ma solo le righe o le colonne complete diventano selezionate o deselezionate.  
  
## <a name="default-mouse-handling"></a>Gestione predefinita del mouse
  
### <a name="basic-mouse-handling"></a>Gestione del mouse di base
  
> [!NOTE]
> Quando si fa clic su una cella con il pulsante sinistro del mouse, viene sempre modificata la cella corrente. Quando si fa clic su una cella con il pulsante destro del mouse, viene aperto un menu di scelta rapida, quando disponibile.  
  
|Azione del mouse|Descrizione|  
|------------------|-----------------|  
|Pulsante sinistro del mouse|Crea la cella con clic sulla cella corrente e genera l' <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> evento.|  
|Pulsante sinistro del mouse su|Genera l'evento <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>.|  
|Clic del pulsante sinistro del mouse|Genera gli <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> eventi <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> e.|  
|Pulsante sinistro del mouse e trascinamento in una cella di intestazione di colonna|Se la <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> proprietà è `true`, sposta la colonna in modo che possa essere rilasciata in una nuova posizione.|  
  
### <a name="mouse-selection"></a>Selezione del mouse

 Non è associato alcun comportamento di selezione al pulsante centrale del mouse o alla rotellina del mouse.  
  
 Se la <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> proprietà è impostata su `false` e la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> proprietà è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, si verifica il comportamento seguente.  
  
|Azione del mouse|Descrizione|  
|------------------|-----------------|  
|Fare clic sul pulsante sinistro del mouse|Seleziona solo la cella corrente se l'utente fa clic su una cella. Nessun comportamento di selezione se l'utente fa clic su un'intestazione di riga o di colonna.|  
|Fare clic con il pulsante destro del mouse|Consente di visualizzare un menu di scelta rapida, se disponibile.|  
  
 Lo stesso comportamento si verifica quando <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> l'oggetto è <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> impostato <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>su o, ad eccezione del fatto che, a seconda della modalità di selezione, se si fa clic su un'intestazione di riga o di colonna, viene selezionata la riga o la colonna completa e la cella corrente viene impostata sulla prima cella della riga o della colonna.  
  
 Se <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, facendo clic su una cella di una riga o di una colonna verrà selezionata la riga o la colonna completa.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `true`, facendo clic su una cella quando si preme CTRL o Maiusc verrà modificata una selezione a più celle.  
  
 Quando si fa clic su una cella tenendo premuto CTRL, la cella cambia lo stato di selezione mentre tutte le altre celle mantengono lo stato di selezione corrente.  
  
 Quando si fa clic su una cella o una serie di celle mentre si preme MAIUSC, la selezione include tutte le celle tra la cella corrente e una cella di ancoraggio che si trova nella posizione della cella corrente prima del primo clic. Quando si fa clic e si trascina il puntatore su più celle, la cella di ancoraggio è la cella su cui si fa clic all'inizio dell'operazione di trascinamento. Clic successivi durante la pressione di SHIFT modificare la cella corrente, ma non la cella di ancoraggio. Le altre celle del controllo rimarranno selezionate se sono già state selezionate, ma potrebbero essere deselezionate se la navigazione del mouse le inserisce temporaneamente tra la cella di ancoraggio e la cella corrente.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>e è impostato su o, facendo clic su un'intestazione di riga o di colonna (a seconda della modalità di selezione) mentre si preme MAIUSC verrà modificata una selezione esistente di righe o colonne complete se tale `true` selezione esistente. In caso contrario, cancellerà la selezione e avvierà una nuova selezione di righe o colonne complete. Se si fa clic su un'intestazione di riga o di colonna quando si preme CTRL, tuttavia, la riga o la colonna selezionata viene aggiunta o rimossa dalla selezione corrente senza modificare la selezione corrente.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `true` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, fare clic su una cella quando si preme MAIUSC o CTRL si comporta nello stesso modo, ad eccezione del fatto che sono interessate solo righe e colonne complete.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Controllo DataGridView](datagridview-control-windows-forms.md)
