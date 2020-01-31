---
title: Procedure consigliate per il ridimensionamento del controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 63500a79def89510b4bc7a436abc4620a7265a79
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744130"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Procedure consigliate per ridimensionare il controllo DataGridView Windows Form

Il controllo <xref:System.Windows.Forms.DataGridView> è progettato per garantire la massima scalabilità. Se è necessario visualizzare grandi quantità di dati, attenersi alle linee guida descritte in questo argomento per evitare l'utilizzo di grandi quantità di memoria o la riduzione della velocità di risposta dell'interfaccia utente (UI). In questo argomento vengono illustrati i problemi seguenti:

- Uso efficiente degli stili delle celle

- Utilizzo efficiente di menu di scelta rapida

- Uso efficiente del ridimensionamento automatico

- Utilizzo efficiente delle raccolte celle, righe e colonne selezionate

- Uso di righe condivise

- Impedire la condivisione delle righe

Se si hanno esigenze di prestazioni particolari, è possibile implementare la modalità virtuale e fornire le proprie operazioni di gestione dei dati. Per altre informazioni, vedere [modalità di visualizzazione dati nel controllo DataGridView Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md).

## <a name="using-cell-styles-efficiently"></a>Uso efficiente degli stili delle celle

Ogni cella, riga e colonna può avere le proprie informazioni di stile. Le informazioni sullo stile vengono archiviate in oggetti <xref:System.Windows.Forms.DataGridViewCellStyle>. La creazione di oggetti stile cella per molti singoli elementi di <xref:System.Windows.Forms.DataGridView> può risultare inefficiente, soprattutto quando si lavora con grandi quantità di dati. Per evitare un effetto sulle prestazioni, attenersi alle linee guida seguenti:

- Evitare di impostare le proprietà di stile della cella per singoli oggetti <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewRow>. Include l'oggetto riga specificato dalla proprietà <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>. Ogni nuova riga clonata dal modello di riga riceverà la propria copia dell'oggetto stile della cella del modello. Per la massima scalabilità, impostare le proprietà di stile della cella a livello di <xref:System.Windows.Forms.DataGridView>. Ad esempio, impostare la proprietà <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> invece della proprietà <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>.

- Se per alcune celle è necessaria una formattazione diversa da quella predefinita, utilizzare la stessa istanza di <xref:System.Windows.Forms.DataGridViewCellStyle> tra gruppi di celle, righe o colonne. Evitare di impostare direttamente le proprietà di tipo <xref:System.Windows.Forms.DataGridViewCellStyle> su singole celle, righe e colonne. Per un esempio di condivisione dello stile della cella, vedere [procedura: impostare stili di cella predefiniti per il controllo DataGridView Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). È anche possibile evitare una riduzione delle prestazioni quando si impostano gli stili delle celle singolarmente gestendo il gestore dell'evento <xref:System.Windows.Forms.DataGridView.CellFormatting>. Per un esempio, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).

- Quando si determina lo stile di una cella, utilizzare la proprietà <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> invece della proprietà <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>. L'accesso alla proprietà <xref:System.Windows.Forms.DataGridViewCell.Style%2A> crea una nuova istanza della classe <xref:System.Windows.Forms.DataGridViewCellStyle> se la proprietà non è già stata utilizzata. Inoltre, questo oggetto potrebbe non contenere le informazioni di stile complete per la cella se alcuni stili vengono ereditati dalla riga, dalla colonna o dal controllo. Per ulteriori informazioni sull'ereditarietà dello stile della cella, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).

## <a name="using-shortcut-menus-efficiently"></a>Utilizzo efficiente di menu di scelta rapida

Ogni cella, riga e colonna può avere un proprio menu di scelta rapida. I menu di scelta rapida nel controllo <xref:System.Windows.Forms.DataGridView> sono rappresentati da controlli di <xref:System.Windows.Forms.ContextMenuStrip>. Così come per gli oggetti di stile cella, la creazione di menu di scelta rapida per molti singoli elementi di <xref:System.Windows.Forms.DataGridView> avrà un impatto negativo sulle prestazioni. Per evitare questi rigore, attenersi alle linee guida seguenti:

- Evitare di creare menu di scelta rapida per singole celle e righe. Questo include il modello di riga, che viene clonato insieme al relativo menu di scelta rapida quando vengono aggiunte nuove righe al controllo. Per la massima scalabilità, usare solo la proprietà <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> del controllo per specificare un singolo menu di scelta rapida per l'intero controllo.

- Se sono necessari più menu di scelta rapida per più righe o celle, gestire gli eventi <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> o <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>. Questi eventi consentono di gestire gli oggetti del menu di scelta rapida, consentendo di ottimizzare le prestazioni.

## <a name="using-automatic-resizing-efficiently"></a>Uso efficiente del ridimensionamento automatico

Le righe, le colonne e le intestazioni possono essere ridimensionate automaticamente come modifiche al contenuto della cella, in modo che l'intero contenuto delle celle venga visualizzato senza ritaglio. La modifica delle modalità di ridimensionamento può inoltre ridimensionare righe, colonne e intestazioni. Per determinare la dimensione corretta, il controllo <xref:System.Windows.Forms.DataGridView> deve esaminare il valore di ogni cella che deve contenere. Quando si utilizzano set di dati di grandi dimensioni, questa analisi può influire negativamente sulle prestazioni del controllo quando si verifica il ridimensionamento automatico. Per evitare le penalizzazioni delle prestazioni, attenersi alle linee guida seguenti:

- Evitare di usare il ridimensionamento automatico in un controllo <xref:System.Windows.Forms.DataGridView> con un set di righe di grandi dimensioni. Se si usa il ridimensionamento automatico, è sufficiente ridimensionare in base alle righe visualizzate. Usare anche solo le righe visualizzate in modalità virtuale.

  - Per righe e colonne, utilizzare il `DisplayedCells` o `DisplayedCellsExceptHeaders` campo delle enumerazioni <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>e <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>.

  - Per le intestazioni di riga, usare il campo <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> o <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> dell'enumerazione <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>.

- Per la massima scalabilità, disattivare il ridimensionamento automatico e usare il ridimensionamento a livello di codice.

Per ulteriori informazioni, vedere [Opzioni di ridimensionamento nel controllo DataGridView Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).

## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Utilizzo efficiente delle raccolte celle, righe e colonne selezionate

La raccolta di <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> non viene eseguita in modo efficiente con selezioni di grandi dimensioni. Le raccolte <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> e <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> possono anche essere inefficienti, anche se a un livello inferiore perché sono presenti molte meno righe rispetto alle celle di un controllo <xref:System.Windows.Forms.DataGridView> tipico e molte meno colonne rispetto alle righe. Per evitare le penalizzazioni delle prestazioni durante l'utilizzo di queste raccolte, attenersi alle linee guida seguenti:

- Per determinare se tutte le celle del <xref:System.Windows.Forms.DataGridView> sono state selezionate prima di accedere al contenuto della raccolta <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, controllare il valore restituito del metodo <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>. Si noti, tuttavia, che questo metodo può impedire la condivisione delle righe. Per altre informazioni, vedere la sezione successiva.

- Evitare di utilizzare la proprietà <xref:System.Collections.ICollection.Count%2A> della <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> per determinare il numero di celle selezionate. Usare invece il metodo <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> e passare il valore <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType>. Analogamente, utilizzare i metodi <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> per determinare il numero di elementi selezionati, anziché accedere alle raccolte di righe e colonne selezionate.

- Evitare le modalità di selezione basate su celle. In alternativa, impostare la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.

## <a name="using-shared-rows"></a>Uso di righe condivise

Un utilizzo efficiente della memoria viene effettuato nel controllo <xref:System.Windows.Forms.DataGridView> tramite righe condivise. Le righe condividono quante più informazioni sul loro aspetto e comportamento possibile condividendo le istanze della classe <xref:System.Windows.Forms.DataGridViewRow>.

Durante la condivisione di istanze di riga viene salvata la memoria, le righe possono essere facilmente non condivise. Ad esempio, ogni volta che un utente interagisce direttamente con una cella, viene annullata la condivisione della relativa riga. Poiché questa operazione non può essere evitata, le linee guida in questo argomento sono utili solo quando si lavora con grandi quantità di dati e solo quando gli utenti interagiranno con una parte relativamente piccola dei dati ogni volta che viene eseguito il programma.

Una riga non può essere condivisa in un controllo <xref:System.Windows.Forms.DataGridView> non associato se una delle relative celle contiene valori. Quando il controllo <xref:System.Windows.Forms.DataGridView> è associato a un'origine dati esterna o quando si implementa la modalità virtuale e si fornisce un'origine dati personalizzata, i valori delle celle vengono archiviati all'esterno del controllo anziché negli oggetti cella, consentendo la condivisione delle righe.

Un oggetto riga può essere condiviso solo se lo stato di tutte le relative celle può essere determinato dallo stato della riga e dagli Stati delle colonne contenenti le celle. Se si modifica lo stato di una cella in modo che non possa più essere dedotto dallo stato della relativa riga e colonna, la riga non può essere condivisa.

Una riga, ad esempio, non può essere condivisa in una delle situazioni seguenti:

- La riga contiene una sola cella selezionata che non si trova in una colonna selezionata.

- La riga contiene una cella con le proprietà <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> o <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> impostate.

- La riga contiene un <xref:System.Windows.Forms.DataGridViewComboBoxCell> con la relativa proprietà <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> impostata.

In modalità associata o in modalità virtuale è possibile fornire descrizioni comandi e menu di scelta rapida per le singole celle gestendo gli eventi <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> e <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded>.

Il controllo <xref:System.Windows.Forms.DataGridView> tenterà automaticamente di utilizzare righe condivise ogni volta che le righe vengono aggiunte al <xref:System.Windows.Forms.DataGridViewRowCollection>. Usare le linee guida seguenti per assicurarsi che le righe siano condivise:

- Evitare di chiamare l'overload `Add(Object[])` del metodo <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> e l'overload `Insert(Object[])` del metodo <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> della raccolta di <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>. Questi overload creano automaticamente righe non condivise.

- Assicurarsi che la riga specificata nella proprietà <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> possa essere condivisa nei casi seguenti:

  - Quando si chiama il `Add()` o `Add(Int32)` overload del metodo <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> o dell'overload `Insert(Int32,Int32)` del metodo <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> della raccolta di <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>.

  - Quando si aumenta il valore della proprietà <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType>.

  - Quando si imposta la proprietà <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>.

- Assicurarsi che la riga indicata dal parametro `indexSource` possa essere condivisa quando si chiamano i metodi <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>e <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> della raccolta di <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>.

- Assicurarsi che la riga o le righe specificate possano essere condivise quando si chiama l'overload `Add(DataGridViewRow)` del metodo <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, il metodo <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A>, l'overload `Insert(Int32,DataGridViewRow)` del metodo <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> e il metodo <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> della raccolta di <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>.

Per determinare se una riga è condivisa, utilizzare il metodo <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> per recuperare l'oggetto riga, quindi controllare la proprietà <xref:System.Windows.Forms.DataGridViewBand.Index%2A> dell'oggetto. Le righe condivise hanno sempre un valore della proprietà <xref:System.Windows.Forms.DataGridViewBand.Index%2A>-1.

## <a name="preventing-rows-from-becoming-unshared"></a>Impedire la condivisione delle righe

È possibile annullare la condivisione delle righe condivise in seguito all'azione del codice o dell'utente. Per evitare un effetto sulle prestazioni, è consigliabile evitare che le righe vengano non condivise. Durante lo sviluppo di applicazioni, è possibile gestire l'evento <xref:System.Windows.Forms.DataGridView.RowUnshared> per determinare quando le righe diventano non condivise. Questa operazione è utile durante il debug dei problemi di condivisione delle righe.

Per impedire che le righe diventino non condivise, attenersi alle linee guida seguenti:

- Evitare di indicizzare la raccolta di <xref:System.Windows.Forms.DataGridView.Rows%2A> o scorrerla con un ciclo di `foreach`. In genere non è necessario accedere direttamente alle righe. <xref:System.Windows.Forms.DataGridView> metodi che operano sulle righe accettano argomenti di indice di riga anziché istanze di riga. Inoltre, i gestori per gli eventi correlati alla riga ricevono oggetti argomento dell'evento con proprietà di riga che è possibile usare per modificare le righe senza comportarne la condivisione.

- Se è necessario accedere a un oggetto riga, usare il metodo <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> e passare l'indice effettivo della riga. Si noti, tuttavia, che la modifica di un oggetto riga condiviso recuperato tramite questo metodo modificherà tutte le righe che condividono questo oggetto. La riga per i nuovi record non è tuttavia condivisa con altre righe, pertanto non sarà interessata quando si modifica un'altra riga. Si noti inoltre che diverse righe rappresentate da una riga condivisa possono avere diversi menu di scelta rapida. Per recuperare il menu di scelta rapida corretto da un'istanza di riga condivisa, utilizzare il metodo <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> e passare l'indice effettivo della riga. Se invece si accede alla proprietà <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> della riga condivisa, verrà utilizzato l'indice di riga condiviso di-1 e non verrà recuperato il menu di scelta rapida corretto.

- Evitare l'indicizzazione della raccolta <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType>. Se si accede direttamente a una cella, viene annullata la condivisione della riga padre, creando un'istanza di una nuova <xref:System.Windows.Forms.DataGridViewRow>. I gestori per gli eventi correlati alle celle ricevono oggetti argomento dell'evento con proprietà delle celle che è possibile usare per modificare le celle senza causare la condivisione delle righe. È inoltre possibile utilizzare la proprietà <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> per recuperare gli indici di riga e di colonna della cella corrente senza accedere direttamente alla cella.

- Evitare le modalità di selezione basate su celle. Queste modalità comportano la non condivisione delle righe. In alternativa, impostare la proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> su <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.

- Non gestire gli eventi <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType>. Questi eventi impediscono la condivisione delle righe. Non chiamare inoltre i metodi <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType>, che generano questi eventi.

- Non accedere alla raccolta di <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> quando il valore della proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> è <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>. In questo modo verrà annullata la condivisione di tutte le righe selezionate.

- Non chiamare il metodo <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType>. Questo metodo può impedire la condivisione delle righe.

- Non chiamare il metodo <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> quando il valore della proprietà <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> è <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>. In questo modo verrà annullata la condivisione di tutte le righe.

- Non impostare la proprietà <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> o <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> di una cella su `false` quando la proprietà corrispondente nella relativa colonna è impostata su `true`. In questo modo verrà annullata la condivisione di tutte le righe.

- Non accedere alla proprietà <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType>. In questo modo verrà annullata la condivisione di tutte le righe.

- Non chiamare l'overload `Sort(IComparer)` del metodo <xref:System.Windows.Forms.DataGridView.Sort%2A>. L'ordinamento con un operatore di confronto personalizzato causa la non condivisione di tutte le righe.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Form](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md)
