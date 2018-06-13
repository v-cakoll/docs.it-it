---
title: Gestione del controllo DataGridView Windows Form predefinita della tastiera e mouse
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
ms.openlocfilehash: b0ed468fe7d38fbeda90d5347338bce14059b730
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529568"
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Gestione del controllo DataGridView Windows Form predefinita della tastiera e mouse

Le tabelle seguenti descrivono come è possibile interagire con il <xref:System.Windows.Forms.DataGridView> controllo mediante una tastiera e mouse.  
  
> [!NOTE]
>  Per personalizzare il comportamento della tastiera, è possibile gestire gli eventi della tastiera standard, ad esempio <xref:System.Windows.Forms.Control.KeyDown>. In modalità di modifica, tuttavia, il controllo di modificando ospitato riceve l'input da tastiera e non si verificano gli eventi di tastiera per il <xref:System.Windows.Forms.DataGridView> controllo. Per gestire gli eventi controllo di modifica, associare i gestori per il controllo di modifica in un <xref:System.Windows.Forms.DataGridView.EditingControlShowing> gestore dell'evento. In alternativa, è possibile personalizzare il comportamento della tastiera in un <xref:System.Windows.Forms.DataGridView> sottoclasse eseguendo l'override di <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> e <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> metodi.  
  
## <a name="default-keyboard-handling"></a>Gestione predefinita della tastiera  
  
### <a name="basic-navigation-and-entry-keys"></a>Tasti di navigazione e la voce di base  
  
|Tasto o combinazione|Descrizione|  
|----------------------------|-----------------|  
|Freccia GIÙ|Sposta lo stato attivo alla cella direttamente sotto la cella corrente. Se lo stato attivo è nell'ultima riga, non esegue alcuna operazione.|  
|FRECCIA SINISTRA|Sposta lo stato attivo alla cella nella riga precedente. Se lo stato attivo è nella prima cella nella riga, non esegue alcuna operazione.|  
|FRECCIA DESTRA|Sposta lo stato attivo alla cella nella riga successiva. Se lo stato attivo è nell'ultima cella nella riga, non esegue alcuna operazione.|  
|Freccia SU|Sposta lo stato attivo per la cella immediatamente sopra la cella corrente. Se lo stato attivo è nella prima riga, non esegue alcuna operazione.|  
|HOME|Sposta lo stato attivo alla prima cella nella riga corrente.|  
|FINE|Sposta lo stato attivo all'ultima cella nella riga corrente.|  
|PGGIÙ|Consente di scorrere il controllo verso il basso il numero di righe visualizzate in modo completo. Sposta lo stato attivo per l'ultima riga visualizzata completamente senza modificare le colonne.|  
|PGSU|Consente di scorrere il controllo verso l'alto il numero di righe visualizzate in modo completo. Spostare lo stato attivo alla prima riga visualizzata senza modificare le colonne.|  
|TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `false`, sposta lo stato attivo alla cella successiva nella riga corrente. Se lo stato attivo è già nell'ultima cella della riga, sposta lo stato attivo alla prima cella nella riga successiva. Se lo stato attivo è nell'ultima cella nel controllo, sposta lo stato attivo al controllo successivo nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `true`, sposta lo stato attivo al controllo successivo nell'ordine di tabulazione del contenitore padre.|  
|MAIUSC+TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `false`, sposta lo stato attivo alla cella precedente nella riga corrente. Se lo stato attivo è già nella prima cella della riga, sposta lo stato attivo all'ultima cella della riga precedente. Se lo stato attivo è nella prima cella nel controllo, sposta lo stato attivo al controllo precedente nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `true`, sposta lo stato attivo al controllo precedente nell'ordine di tabulazione del contenitore padre.|  
|CTRL+TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `false`, sposta lo stato attivo al controllo successivo nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `true`, sposta lo stato attivo alla cella successiva nella riga corrente. Se lo stato attivo è già nell'ultima cella della riga, sposta lo stato attivo alla prima cella nella riga successiva. Se lo stato attivo è nell'ultima cella nel controllo, sposta lo stato attivo al controllo successivo nell'ordine di tabulazione del contenitore padre.|  
|CTRL+MAIUSC+TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `false`, sposta lo stato attivo al controllo precedente nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `true`, sposta lo stato attivo alla cella precedente nella riga corrente. Se lo stato attivo è già nella prima cella della riga, sposta lo stato attivo all'ultima cella della riga precedente. Se lo stato attivo è nella prima cella nel controllo, sposta lo stato attivo al controllo precedente nell'ordine di tabulazione del contenitore padre.|  
|CTRL + FRECCIA|Sposta lo stato attivo all'ultima cella nella direzione della freccia.|  
|CTRL + HOME|Sposta lo stato attivo alla prima cella nel controllo.|  
|CTRL + FINE|Sposta lo stato attivo all'ultima cella nel controllo.|  
|CTRL + PAGINA IN ALTO/BASSO|Uguale a PGGIÙ o PGSU.|  
|F2|Pone la cella corrente in modalità di modifica se la <xref:System.Windows.Forms.DataGridView.EditMode%2A> valore della proprietà è <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> o <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>.|
|F3|Ordina la colonna corrente se il <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> valore della proprietà è <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>. È uguale alla selezione di intestazione di colonna corrente. Disponibile a partire da .NET Framework 4.7.2. Per abilitare questa funzionalità, applicazioni sia come destinazione .NET Framework 4.7.2 o versioni successive oppure acconsentire in modo esplicito questi miglioramenti di utilizzo delle opzioni di AppContext.|  
|F4|Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewComboBoxCell>, pone la cella in modalità di modifica e visualizza l'elenco a discesa.|  
|ALT + FRECCIA SU/GIÙ|Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewComboBoxCell>, pone la cella in modalità di modifica e visualizza l'elenco a discesa.|  
|BARRA SPAZIATRICE|Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>, o <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, genera il <xref:System.Windows.Forms.DataGridView.CellClick> e <xref:System.Windows.Forms.DataGridView.CellContentClick> eventi. Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewButtonCell>, anche preme il pulsante. Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, cambia anche lo stato di selezione.|  
|INVIO|Esegue il commit di tutte le modifiche alla cella corrente e alla riga e sposta lo stato attivo alla cella direttamente sotto la cella corrente. Se lo stato attivo è nell'ultima riga, esegue il commit di tutte le modifiche senza spostare lo stato attivo.|  
|ESC|Se il controllo è in modalità di modifica, Annulla la modifica. Se il controllo non è in modalità di modifica, verranno annullate le modifiche apportate alla riga corrente se il controllo è associato a un'origine dati che supporta la modifica o la modalità virtuale è stata implementata con ambito di commit a livello di riga.|  
|BACKSPACE|Elimina il carattere che precede il punto di inserimento quando si modifica una cella.|  
|DELETE|Elimina il carattere dopo il punto di inserimento quando si modifica una cella.|  
|CTRL+INVIO|Esegue il commit di tutte le modifiche alla cella corrente senza spostare lo stato attivo. Anche le modifiche alla riga corrente se il controllo è associato a un'origine dati che supporta la modalità di modifica o virtuale è stata implementata con commit a livello di riga ambito di commit.|  
|CTRL+0|Immette un <xref:System.DBNull.Value?displayProperty=nameWithType> valore nella cella corrente, se la cella può essere modificata. Per impostazione predefinita, il valore visualizzato per un <xref:System.DBNull> valore di cella è il valore della <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> proprietà del <xref:System.Windows.Forms.DataGridViewCellStyle> attiva per la cella corrente.|  
  
### <a name="selection-keys"></a>Tasti di selezione

 Se il <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `false` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, la cella corrente usando i tasti di navigazione modifica la selezione nella nuova cella. Questo comportamento non influenzano il MAIUSC, CTRL e ALT.  
  
 Se il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, lo stesso comportamento si verifica, ma con le seguenti aggiunte.  
  
|Tasto o combinazione|Descrizione|  
|----------------------------|-----------------|  
|MAIUSC + BARRA SPAZIATRICE|Seleziona l'intera riga o colonna (come fare clic sull'intestazione di riga o colonna).|  
|chiave di navigazione (tasto di direzione, PGSU/PGGIÙ, HOME, fine)|Se è selezionata un'intera riga o colonna, modificare la cella corrente a una nuova riga o colonna la selezione si sposta nella nuova riga o colonna (a seconda della modalità di selezione).|  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `false` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, modificare la cella corrente a una nuova riga o colonna usando la tastiera, la selezione si sposta nella nuova riga o colonna. Questo comportamento non influenzano il MAIUSC, CTRL e ALT.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `true`, non modifica il comportamento di navigazione, ma si sposta con la tastiera tenendo premuto il tasto MAIUSC (CTRL + MAIUSC compreso) viene modificata la selezione di celle. Prima dello spostamento, il controllo Contrassegna la cella corrente come una cella di aggancio. Quando si Esplora premuto il tasto MAIUSC, la selezione include tutte le celle tra la cella di aggancio e la cella corrente. Le altre celle nel controllo rimane selezionate se sono già selezionate, ma potrebbero essere deselezionate se la navigazione da tastiera li inserisce temporaneamente tra la cella di aggancio e la cella corrente.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `true` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, il comportamento delle cella di aggancio cella corrente è uguale, ma solo righe o colonne intere vengono selezionate o deselezionate.  
  
## <a name="default-mouse-handling"></a>Gestione predefinita del mouse
  
### <a name="basic-mouse-handling"></a>Gestione di base del mouse
  
> [!NOTE]
>  Scegliere sempre una cella con il pulsante sinistro del mouse cambia la cella corrente. Fare clic su una cella con il pulsante destro del mouse apre un menu di scelta rapida, quando diventano disponibili.  
  
|Azione del mouse|Descrizione|  
|------------------|-----------------|  
|Selezione del pulsante sinistro del mouse|Rende la cella selezionata la cella corrente e genera il <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> evento.|  
|Rilascio del pulsante sinistro del mouse|Genera l'evento <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>.|  
|Fare clic su pulsante sinistro del mouse|Genera il <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> e <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> eventi|  
|Selezione del pulsante sinistro del mouse e trascinare in una cella di intestazione di colonna|Se il <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> proprietà `true`, la colonna viene spostata in modo che possono essere eliminato in una nuova posizione.|  
  
### <a name="mouse-selection"></a>Selezione del mouse

 Nessun comportamento di selezione è associato con il pulsante centrale del mouse o la rotellina del mouse.  
  
 Se il <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `false` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, verifica quanto segue.  
  
|Azione del mouse|Descrizione|  
|------------------|-----------------|  
|Fare clic sul pulsante sinistro del mouse|Se l'utente fa clic su una cella, seleziona solo la cella corrente. Nessun comportamento di selezione se l'utente fa clic su un'intestazione di riga o colonna.|  
|Scegliere il pulsante destro del mouse|Visualizza un menu di scelta rapida se è disponibile.|  
  
 Lo stesso comportamento si verifica quando il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, ad eccezione del fatto che, a seconda della modalità di selezione, fare clic su un'intestazione di riga o colonna verrà selezionare l'intera riga o colonna e impostare la cella corrente alla prima cella nella riga o colonna.  
  
 Se <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, facendo clic su qualsiasi cella di una riga o colonna verrà selezionata l'intera riga o colonna.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `true`, fare clic su una cella tenendo premuto CTRL o MAIUSC viene modificata la selezione di celle.  
  
 Quando si fa clic su una cella tenendo premuto il tasto CTRL, la cella viene modificato lo stato di selezione mentre tutte le altre celle mantengono lo stato di selezione corrente.  
  
 Quando si fa clic su una cella o una serie di celle tenendo premuto il tasto MAIUSC, la selezione include tutte le celle tra la cella corrente e una cella di aggancio si trova in corrispondenza della posizione della cella corrente prima del primo clic. Facendo clic e trascina il puntatore su più celle, la cella di aggancio è la cella selezionata all'inizio dell'operazione di trascinamento. Si seleziona il tasto MAIUSC modifica la cella corrente, ma non la cella di aggancio. Le altre celle nel controllo rimane selezionate se sono già selezionate, ma potrebbero essere deselezionate se lo spostamento del mouse li inserisce temporaneamente tra la cella di aggancio e la cella corrente.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `true` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, fare clic su un'intestazione di riga o colonna (a seconda della modalità di selezione) tenendo premuto il tasto MAIUSC viene modificata una selezione esistente di intere righe o colonne se tali un selezione esiste. In caso contrario, verrà deselezionarla e avvia una nuova selezione di righe o colonne intere. Fare clic su un'intestazione di riga o colonna tenendo premuto il tasto CTRL, può tuttavia, aggiungere o rimuovere la riga selezionata o la colonna dalla selezione corrente senza modificare in altro modo la selezione corrente.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostato su `true` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostato su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, facendo clic su una cella tenendo premuto il tasto MAIUSC o CTRL si comporta allo stesso modo, ad eccezione che solo intere righe e colonne sono interessate.  
  
## <a name="see-also"></a>Vedere anche

<xref:System.Windows.Forms.DataGridView>  
 [Controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
