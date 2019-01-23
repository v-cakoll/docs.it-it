---
title: Gestione del controllo DataGridView di Windows Forms predefinita della tastiera e mouse
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
ms.openlocfilehash: 4d0a3cb7a56b388ee9bd3f932f9fec604b39fa62
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521764"
---
# <a name="default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control"></a>Gestione del controllo DataGridView di Windows Forms predefinita della tastiera e mouse

Le tabelle seguenti descrivono come gli utenti possono interagire con il <xref:System.Windows.Forms.DataGridView> controllo grazie a una tastiera e mouse.  
  
> [!NOTE]
>  Per personalizzare il comportamento della tastiera, è possibile gestire gli eventi della tastiera standard, ad esempio <xref:System.Windows.Forms.Control.KeyDown>. In modalità di modifica, tuttavia, il controllo di modifica ospitato riceve l'input da tastiera e non si verificano gli eventi della tastiera per il <xref:System.Windows.Forms.DataGridView> controllo. Per gestire gli eventi di controllo modifica, associare i gestori per il controllo di modifica in un <xref:System.Windows.Forms.DataGridView.EditingControlShowing> gestore dell'evento. In alternativa, è possibile personalizzare il comportamento della tastiera in un' <xref:System.Windows.Forms.DataGridView> sottoclasse eseguendo l'override di <xref:System.Windows.Forms.DataGridView.ProcessDialogKey%2A> e <xref:System.Windows.Forms.DataGridView.ProcessDataGridViewKey%2A> metodi.  
  
## <a name="default-keyboard-handling"></a>Gestione della tastiera predefinita  
  
### <a name="basic-navigation-and-entry-keys"></a>Tasti di navigazione e immissione di base  
  
|Tasto o della combinazione|Descrizione|  
|----------------------------|-----------------|  
|Freccia GIÙ|Sposta lo stato attivo per la cella posta immediatamente sotto la cella corrente. Se lo stato attivo è nell'ultima riga, non esegue alcuna operazione.|  
|FRECCIA SINISTRA|Sposta lo stato attivo alla cella nella riga precedente. Se lo stato attivo è nella prima cella nella riga, non esegue alcuna operazione.|  
|FRECCIA DESTRA|Sposta lo stato attivo sulla cella nella riga successiva. Se lo stato attivo è nell'ultima cella della riga, non esegue alcuna operazione.|  
|Freccia SU|Sposta lo stato attivo sulla cella immediatamente sopra la cella corrente. Se lo stato attivo è nella prima riga, non esegue alcuna operazione.|  
|HOME|Sposta lo stato attivo alla prima cella nella riga corrente.|  
|FINE|Sposta lo stato attivo all'ultima cella nella riga corrente.|  
|PGGIÙ|Scorre il controllo verso il basso per il numero di righe visualizzate in modo completo. Sposta lo stato attivo per l'ultima riga visualizzata completamente senza modificare le colonne.|  
|PGSU|Scorre il controllo verso l'alto per il numero di righe visualizzate in modo completo. Sposta lo stato attivo alla prima riga visualizzata senza modificare le colonne.|  
|TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `false`, sposta lo stato attivo alla cella successiva nella riga corrente. Se lo stato attivo è già nell'ultima cella della riga, sposta lo stato attivo alla prima cella nella riga successiva. Se lo stato attivo è nell'ultima cella nel controllo, si sposta lo stato attivo al controllo successivo nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `true`, sposta lo stato attivo al controllo successivo nell'ordine di tabulazione del contenitore padre.|  
|MAIUSC+TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `false`, sposta lo stato attivo per la cella precedente nella riga corrente. Se lo stato attivo è già nella prima cella della riga, sposta lo stato attivo all'ultima cella nella riga precedente. Se lo stato attivo è nella prima cella nel controllo, si sposta lo stato attivo al controllo precedente nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `true`, sposta lo stato attivo al controllo precedente nell'ordine di tabulazione del contenitore padre.|  
|CTRL+TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `false`, sposta lo stato attivo al controllo successivo nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `true`, sposta lo stato attivo alla cella successiva nella riga corrente. Se lo stato attivo è già nell'ultima cella della riga, sposta lo stato attivo alla prima cella nella riga successiva. Se lo stato attivo è nell'ultima cella nel controllo, si sposta lo stato attivo al controllo successivo nell'ordine di tabulazione del contenitore padre.|  
|CTRL+MAIUSC+TAB|Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `false`, sposta lo stato attivo al controllo precedente nell'ordine di tabulazione del contenitore padre.<br /><br /> Se il <xref:System.Windows.Forms.DataGridView.StandardTab%2A> valore della proprietà è `true`, sposta lo stato attivo per la cella precedente nella riga corrente. Se lo stato attivo è già nella prima cella della riga, sposta lo stato attivo all'ultima cella nella riga precedente. Se lo stato attivo è nella prima cella nel controllo, si sposta lo stato attivo al controllo precedente nell'ordine di tabulazione del contenitore padre.|  
|CTRL + TASTI DI DIREZIONE|Sposta lo stato attivo all'ultima cella nella direzione della freccia.|  
|CTRL+HOME|Sposta lo stato attivo alla prima cella nel controllo.|  
|CTRL + FINE|Sposta lo stato attivo all'ultima cella nel controllo.|  
|CTRL + PGGIÙ RIDURRE O AUMENTARE|Uguale a PGSU o PGGIÙ.|  
|F2|Inserisce la cella corrente in modalità di modifica cella se il <xref:System.Windows.Forms.DataGridView.EditMode%2A> valore della proprietà è <xref:System.Windows.Forms.DataGridViewEditMode.EditOnF2> o <xref:System.Windows.Forms.DataGridViewEditMode.EditOnKeystrokeOrF2>.|
|F3|Ordina la colonna corrente se il <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> valore della proprietà è <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>. È uguale alla selezione intestazione di colonna corrente. Disponibile a partire da .NET Framework 4.7.2. Per abilitare questa funzionalità, le applicazioni devono avere come destinazione .NET Framework 4.7.2 o versioni successive o acconsentire in modo esplicito usando opzioni di AppContext miglioramenti dell'accessibilità.|  
|F4|Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewComboBoxCell>, inserisce la cella in modalità di modifica e visualizza l'elenco a discesa.|  
|ALT + FRECCIA SU/FRECCIA GIÙ|Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewComboBoxCell>, inserisce la cella in modalità di modifica e visualizza l'elenco a discesa.|  
|BARRA SPAZIATRICE|Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewButtonCell>, <xref:System.Windows.Forms.DataGridViewLinkCell>, o <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, genera il <xref:System.Windows.Forms.DataGridView.CellClick> e <xref:System.Windows.Forms.DataGridView.CellContentClick> eventi. Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewButtonCell>, anche preme il pulsante. Se la cella corrente è un <xref:System.Windows.Forms.DataGridViewCheckBoxCell>, cambia anche lo stato di selezione.|  
|INVIO|Esegue il commit di tutte le modifiche alla cella corrente e alla riga e sposta lo stato attivo per la cella posta immediatamente sotto la cella corrente. Se lo stato attivo è nell'ultima riga, esegue il commit di tutte le modifiche senza spostare lo stato attivo.|  
|ESC|Se il controllo è in modalità di modifica, Annulla la modifica. Se il controllo non è in modalità di modifica, verranno annullate le modifiche apportate alla riga corrente se il controllo è associato a un'origine dati che supporta la modifica o la modalità virtuale è stata implementata con ambito di commit a livello di riga.|  
|BACKSPACE|Elimina il carattere che precede il punto di inserimento quando si modifica una cella.|  
|DELETE|Elimina i caratteri dopo il punto di inserimento quando si modifica una cella.|  
|CTRL+INVIO|Esegue il commit di tutte le modifiche alla cella corrente senza spostare lo stato attivo. Anche tutte le modifiche alla riga corrente se il controllo è associato a un'origine dati che supporta la modalità di modifica o virtuale è stata implementata con commit a livello di riga ambito commit.|  
|CTRL+0|Immette un <xref:System.DBNull.Value?displayProperty=nameWithType> valore nella cella corrente, se la cella può essere modificata. Per impostazione predefinita, il valore visualizzato per un <xref:System.DBNull> valore della cella è il valore della <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> proprietà del <xref:System.Windows.Forms.DataGridViewCellStyle> attiva per la cella corrente.|  
  
### <a name="selection-keys"></a>Tasti di selezione

 Se il <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `false` e il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, la modifica della cella corrente usando i tasti di navigazione modifica la selezione nella nuova cella. Il MAIUSC, CTRL e ALT sono non interessano questo comportamento.  
  
 Se il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, si verifica in modo analogo, ma con le aggiunte seguenti.  
  
|Tasto o della combinazione|Descrizione|  
|----------------------------|-----------------|  
|MAIUSC + BARRA SPAZIATRICE|Seleziona l'intera riga o colonna (lo stesso come fare clic sull'intestazione di riga o colonna).|  
|tasto di spostamento (tasto di direzione, PGSU/PGGIÙ, HOME, fine)|Se è selezionata una riga completa o una colonna, la modifica della cella corrente a una nuova riga o colonna Sposta la selezione alla nuova riga o colonna (a seconda della modalità di selezione).|  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `false` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, la modifica della cella corrente a una nuova riga o colonna usando la tastiera la selezione viene spostata nella nuova riga o colonna. Il MAIUSC, CTRL e ALT sono non interessano questo comportamento.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `true`, il comportamento di navigazione rimane invariato, ma lo spostamento con la tastiera tenendo premuto il tasto MAIUSC (CTRL + MAIUSC inclusi) viene modificata la selezione di celle. Prima dello spostamento, il controllo Contrassegna la cella corrente come una cella di aggancio. Quando si passa il tasto MAIUSC, la selezione include tutte le celle comprese tra la cella di aggancio e la cella corrente. Le altre celle nel controllo rimarrà selezionate se sono già state selezionate, ma potrebbe diventare non selezionati se la navigazione tramite tastiera li inserisce temporaneamente tra la cella di aggancio e la cella corrente.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `true` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, il comportamento delle cella di aggancio e cella corrente è lo stesso, ma solo le righe intere o colonne di selezione o deselezione.  
  
## <a name="default-mouse-handling"></a>Gestione predefinita del mouse
  
### <a name="basic-mouse-handling"></a>Gestione di base del mouse
  
> [!NOTE]
>  Fare clic su una cella con il pulsante sinistro del mouse sempre cambia la cella corrente. Fare clic su una cella con il pulsante destro del mouse si apre un menu di scelta rapida, quando diventano disponibili.  
  
|Azione del mouse|Descrizione|  
|------------------|-----------------|  
|Selezione del pulsante sinistro del mouse|Rende la cella selezionata la cella corrente e genera il <xref:System.Windows.Forms.DataGridView.CellMouseDown?displayProperty=nameWithType> evento.|  
|Rilascio del pulsante sinistro del mouse|Genera l'evento <xref:System.Windows.Forms.DataGridView.CellMouseUp?displayProperty=nameWithType>.|  
|Fare clic sul pulsante sinistro del mouse|Genera il <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> e <xref:System.Windows.Forms.DataGridView.CellMouseClick?displayProperty=nameWithType> eventi|  
|Selezione del pulsante sinistro del mouse e trascinare in una cella di intestazione di colonna|Se il <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType> è di proprietà `true`, la colonna viene spostata in modo che sia possibile rilasciarla in una nuova posizione.|  
  
### <a name="mouse-selection"></a>Selezione del mouse

 Nessun comportamento di selezione è associato con il pulsante centrale del mouse o la rotellina del mouse.  
  
 Se il <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `false` e il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>, si verifica quanto segue.  
  
|Azione del mouse|Descrizione|  
|------------------|-----------------|  
|Fare clic sul pulsante sinistro del mouse|Se l'utente fa clic su una cella, seleziona solo la cella corrente. Nessun comportamento di selezione se l'utente fa clic su un'intestazione di riga o colonna.|  
|Fare clic sul pulsante destro del mouse|Visualizza un menu di scelta rapida se disponibile.|  
  
 Lo stesso comportamento si verifica quando la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, ad eccezione del fatto che, a seconda della modalità di selezione, fare clic su un'intestazione di riga o colonna verrà selezionare l'intera riga o colonna e impostare la cella corrente alla prima cella nella riga o colonna.  
  
 Se <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, facendo clic su qualsiasi cella di una riga o colonna verrà selezionata l'intera riga o colonna.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `true`, facendo clic su una cella tenendo premuto il tasto CTRL o MAIUSC viene modificata la selezione di celle.  
  
 Quando si fa clic su una cella mentre vengono premuti CTRL, la cella viene modificato lo stato di selezione tutte le altre celle mantenendo lo stato di selezione corrente.  
  
 Quando si fa clic su una cella o una serie di celle tenendo premuto il tasto MAIUSC, la selezione include tutte le celle comprese tra la cella corrente e un ancoraggio che si trova in corrispondenza della posizione della cella corrente prima del primo clic. Quando si fa clic e trascinare il puntatore del mouse su più celle, la cella di aggancio è la cella selezionata all'inizio dell'operazione di trascinamento. Facendo clic successivamente sarà tenendo premuto il tasto MAIUSC modificare la cella corrente, ma non la cella di aggancio. Le altre celle nel controllo rimarrà selezionate se sono già state selezionate, ma potrebbe diventare non selezionati se la navigazione tramite mouse li inserisce temporaneamente tra la cella di aggancio e la cella corrente.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `true` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, facendo clic su un'intestazione di riga o colonna (a seconda della modalità di selezione) tenendo premuto il tasto MAIUSC modificherà una selezione esistente di intere righe o colonne se tali una selezione esistente. In caso contrario, verrà deselezione della selezione e avvia una nuova selezione di righe o colonne intere. Facendo clic su un'intestazione di riga o colonna tenendo premuto il tasto CTRL, tuttavia, sarà aggiungere o rimuovere la riga selezionata o la colonna dalla selezione corrente senza modificare in altro modo la selezione corrente.  
  
 Se <xref:System.Windows.Forms.DataGridView.MultiSelect%2A> è impostata su `true` e <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> è impostata su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, facendo clic su una cella tenendo premuto il tasto MAIUSC o CTRL si comporta allo stesso modo, ad eccezione che completa solo righe e colonne sono interessate.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Controllo DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)
