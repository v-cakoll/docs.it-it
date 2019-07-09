---
title: Procedure consigliate per ridimensionare il controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 65afd73c166332f08003c3b3bfcc70e488d0373a
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "67663546"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Procedure consigliate per ridimensionare il controllo DataGridView Windows Form

Il <xref:System.Windows.Forms.DataGridView> controllo è progettato per offrire la massima scalabilità. Se si desidera visualizzare grandi quantità di dati, è necessario seguire le linee guida descritte in questo argomento per evitare consumando ingenti quantità di memoria o degradare la velocità di risposta dell'interfaccia utente (UI). Questo argomento vengono illustrati i problemi seguenti:

- Usando gli stili della cella in modo efficiente

- Utilizzo efficiente di menu di scelta rapida

- Tramite il ridimensionamento automatico in modo efficiente

- Usando le raccolte di celle, righe e colonne selezionate in modo efficiente

- Utilizzo di righe condivise

- Impedisce la rimozione della condivisione di righe

Se si hanno esigenze di prestazioni speciali, è possibile implementare la modalità virtuale e fornire le proprie operazioni di gestione dati. Per altre informazioni, vedere [modalità di visualizzazione dei dati nel controllo DataGridView Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md).

## <a name="using-cell-styles-efficiently"></a>Usando gli stili della cella in modo efficiente

Ogni cella, riga e colonna può avere le proprie informazioni di stile. Le informazioni sullo stile vengono archiviate <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti. La creazione di oggetti di cella per molti singoli <xref:System.Windows.Forms.DataGridView> elementi possono risultare inefficienti, soprattutto quando si lavora con grandi quantità di dati. Per evitare un impatto sulle prestazioni, usare le linee guida seguenti:

- Evitare di impostare le proprietà di stile di cella per singoli <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewRow> oggetti. Ciò include l'oggetto riga specificata dal <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> proprietà. Ogni nuova riga che è stato clonato il modello di riga riceveranno una propria copia dell'oggetto di stile di cella del modello. Per ottenere la massima scalabilità, impostare le proprietà di stile di cella nel <xref:System.Windows.Forms.DataGridView> livello. Ad esempio, impostare il <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> proprietà anziché <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> proprietà.

- Se alcune celle è necessaria una formattazione diversa da quella predefinita, usare lo stesso <xref:System.Windows.Forms.DataGridViewCellStyle> istanza tra gruppi di celle, righe o colonne. Evitare di impostare direttamente le proprietà di tipo <xref:System.Windows.Forms.DataGridViewCellStyle> in singole celle, righe e colonne. Per un esempio di condivisione lo stile della cella, vedere [come: Impostare stili di cella predefiniti per i Windows Form controllo DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). È anche possibile evitare un calo delle prestazioni durante l'impostazione di stili della cella singolarmente mediante la gestione di <xref:System.Windows.Forms.DataGridView.CellFormatting> gestore dell'evento. Per un esempio, vedere [Procedura: Personalizzare la formattazione dei dati nel controllo DataGridView Windows Form](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).

- Quando si determina lo stile della cella, usare il <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> proprietà anziché <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> proprietà. L'accesso di <xref:System.Windows.Forms.DataGridViewCell.Style%2A> proprietà consente di creare una nuova istanza del <xref:System.Windows.Forms.DataGridViewCellStyle> classe se la proprietà non è già stata utilizzata. Inoltre, l'oggetto potrebbe non contenere le informazioni complete sullo stile per la cella se alcuni stili vengono ereditate dalla riga, colonna o controllo. Per altre informazioni sull'ereditarietà, vedere [stili della cella nel controllo DataGridView Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md).

## <a name="using-shortcut-menus-efficiently"></a>Utilizzo efficiente di menu di scelta rapida

Ogni cella, riga e colonna può avere un proprio menu di scelta rapida. Menu di scelta rapida di <xref:System.Windows.Forms.DataGridView> controllo sono rappresentate da <xref:System.Windows.Forms.ContextMenuStrip> controlli. Proprio come con gli oggetti di stile di cella, la creazione di menu di scelta rapida per molti singoli <xref:System.Windows.Forms.DataGridView> elementi influirà negativamente sulle prestazioni. Per evitare questo problema, usare le linee guida seguenti:

- Evitare di creare i menu di scelta rapida per le singole celle e righe. Ciò include il modello di riga, viene duplicato e menu di scelta rapida quando vengono aggiunte nuove righe al controllo. Per ottenere la massima scalabilità, usare solo del controllo <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà per specificare un menu di scelta rapida singolo per l'intero controllo.

- Se sono necessari più i menu di scelta rapida per più righe o celle, gestire le <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> o <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> gli eventi. Questi eventi consentono di gestire gli oggetti menu di scelta rapida manualmente, in modo da ottimizzare le prestazioni.

## <a name="using-automatic-resizing-efficiently"></a>Tramite il ridimensionamento automatico in modo efficiente

Le intestazioni, colonne e righe possono essere ridimensionate automaticamente come modifiche del contenuto cella in modo che l'intero contenuto delle celle è visualizzato senza troncamenti. Modifica delle modalità di ridimensionamento possa anche ridimensionare righe, colonne e intestazioni. Per determinare le dimensioni corrette, il <xref:System.Windows.Forms.DataGridView> controllo deve esaminare il valore di ogni cella che è necessario consentirne l'utilizzo. Quando si lavora con grandi set di dati, questa analisi può influire negativamente sulle prestazioni del controllo quando si verifica il ridimensionamento automatico. Per evitare effetti negativi sulle prestazioni, usare le linee guida seguenti:

- Evitare di utilizzare il ridimensionamento su un <xref:System.Windows.Forms.DataGridView> controllo con un ampio set di righe. Se si utilizza il ridimensionamento automatico, ridimensionare solo le righe visualizzate. Usare solo le righe visualizzate in modalità virtuale.

  - Per righe e colonne, usare il `DisplayedCells` o `DisplayedCellsExceptHeaders` campo le <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>, e <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> enumerazioni.

  - Per le intestazioni di riga, usare il <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> oppure <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> campo del <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> enumerazione.

- Per ottenere la massima scalabilità, disattivare il ridimensionamento automatico e utilizzare il ridimensionamento a livello di codice.

Per altre informazioni, vedere [opzioni di ridimensionamento nel controllo DataGridView Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md).

## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Usando le celle selezionate, righe e le raccolte di colonne in modo efficiente

Il <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> insieme non viene eseguito in modo efficiente con selezioni di grandi dimensioni. Il <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> e <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> le raccolte possono anche essere inefficiente, anche se a un livello inferiore perché sono presenti molte righe minore del numero di celle in una tipica <xref:System.Windows.Forms.DataGridView> controllo e molti meno colonne che righe. Per evitare effetti negativi sulle prestazioni quando si lavora con queste raccolte, usare le linee guida seguenti:

- Per determinare se tutte le celle nella <xref:System.Windows.Forms.DataGridView> sono state selezionate prima dell'accesso al contenuto del <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> insieme, controllare il valore restituito del <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> (metodo). Si noti tuttavia che questo metodo può causare righe venga rimossa. Per altre informazioni, vedere la sezione successiva.

- Evitare di usare la <xref:System.Collections.ICollection.Count%2A> proprietà del <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> per determinare il numero di celle selezionate. Usare invece i <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> metodo e passare il <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> valore. Analogamente, usare il <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> metodi per determinare il numero di elementi selezionati, invece di accedere agli insiemi di riga e colonna selezionati.

- Evitare le modalità di selezione basato sulle celle. Al contrario, impostare il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> proprietà <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.

## <a name="using-shared-rows"></a>Utilizzo condiviso righe

Uso efficiente della memoria viene eseguita nel <xref:System.Windows.Forms.DataGridView> controllo condivisione delle righe. Le righe condividono tutte le informazioni sull'aspetto e comportamento minor condividendo le istanze del <xref:System.Windows.Forms.DataGridViewRow> classe.

Anche se la condivisione di istanze di riga, potrai risparmiare memoria, l'impostazione di righe possono diventare non condivise. Ad esempio, ogni volta che un utente interagisce direttamente con una cella, la riga corrispondente viene rimossa. Poiché questo non può essere evitato, le linee guida in questo argomento sono utili solo quando si lavora con grandi quantità di dati e solo quando gli utenti interagiranno con una parte relativamente piccola dei dati ogni volta che viene eseguito il programma.

Una riga non può essere condiviso in un oggetto non associato <xref:System.Windows.Forms.DataGridView> controllare se una delle relative celle contengono valori. Quando il <xref:System.Windows.Forms.DataGridView> controllo è associato a un'origine dati esterna o quando si implementa la modalità virtuale e fornita la propria origine dati, i valori di cella vengono archiviati all'esterno del controllo anziché in oggetti cella, consentendo la condivisione delle righe.

Un oggetto riga può essere condiviso solo se lo stato di tutte le relative celle è possibile determinare lo stato della riga e degli stati delle colonne contenenti le celle. Se si modifica lo stato di una cella in modo che non può essere dedotto dallo stato della relativa riga e colonna, la riga non può essere condivisa.

Ad esempio, una riga non può essere condiviso in una delle situazioni seguenti:

- La riga contiene una singola cella selezionata non in una colonna selezionata.

- La riga contiene una cella con relativi <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> o <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> set di proprietà.

- La riga contiene un <xref:System.Windows.Forms.DataGridViewComboBoxCell> con relativo <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> set di proprietà.

In modalità di associazione o in modalità virtuale, è possibile fornire le descrizioni comandi e menu di scelta rapida per le singole celle gestendo il <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> e <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> eventi.

Il <xref:System.Windows.Forms.DataGridView> controllo tenterà automaticamente di utilizzare le righe condivise ogni volta che vengono aggiunte righe al <xref:System.Windows.Forms.DataGridViewRowCollection>. Usare le linee guida seguenti per assicurarsi che le righe sono condivise:

- Evitare di chiamare il `Add(Object[])` overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> metodo e il `Insert(Object[])` overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> metodo del <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> raccolta. Questi overload creano automaticamente righe non condivise.

- Assicurarsi che la riga specificata nel <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> proprietà può essere condivisi nei casi seguenti:

  - Quando si chiama il `Add()` o `Add(Int32)` gli overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> metodo o il `Insert(Int32,Int32)` overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> metodo del <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> raccolta.

  - Quando si aumenta il valore della <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> proprietà.

  - Quando si impostano le <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> proprietà.

- Assicurarsi che la riga indicata dal `indexSource` parametro può essere condiviso quando si chiama il <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>, e <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> metodi del <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> raccolta.

- Assicurarsi che la riga specificata o le righe possono essere condivisa quando si chiama il `Add(DataGridViewRow)` overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> metodo, il <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> metodo, il `Insert(Int32,DataGridViewRow)` overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> metodo e il <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> metodo il <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>collection.

Per determinare se una riga è condivisa, usare il <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> metodo per recuperare l'oggetto riga e quindi controllare l'oggetto <xref:System.Windows.Forms.DataGridViewBand.Index%2A> proprietà. Righe condivise hanno sempre un <xref:System.Windows.Forms.DataGridViewBand.Index%2A> valore della proprietà di -1.

## <a name="preventing-rows-from-becoming-unshared"></a>Impedisce la rimozione della condivisione di righe

Righe condivise possono essere rimossa come risultato di azione utente o di codice. Per evitare un impatto sulle prestazioni, è necessario evitare che le righe non più condivise. Durante lo sviluppo di applicazioni, è possibile gestire il <xref:System.Windows.Forms.DataGridView.RowUnshared> evento per determinare quando le righe diventano non condivise. Ciò è utile durante il debug di problemi di condivisione delle righe.

Per impedire la rimozione della condivisione di righe, usare le linee guida seguenti:

- Evitare di indicizzare i <xref:System.Windows.Forms.DataGridView.Rows%2A> collection o l'iterazione attraverso di esso con un `foreach` ciclo. Non si sarà in genere necessario accedere direttamente alle righe. <xref:System.Windows.Forms.DataGridView> i metodi che operano su righe accettano gli argomenti di indice di riga invece istanze della riga. Inoltre, gestori per gli eventi relativi alle righe ricevano oggetti argomento evento con proprietà della riga che è possibile usare per modificare le righe senza che ne venga annullata.

- Se è necessario accedere a un oggetto riga, usare il <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> metodo e passare di indice effettivo della riga. Si noti tuttavia che la modifica di un oggetto riga condivisa recuperato tramite questo metodo verrà modificato tutte le righe che condividono questo oggetto. La riga per i nuovi record non viene condivisa con altre righe, tuttavia, in modo che non sarà interessato durante la modifica di qualsiasi altra riga. Si noti anche che diverse righe, rappresentate da una riga condivisa possono avere diversi menu di scelta rapida. Per recuperare il menu di scelta rapida corretta dall'istanza di una riga condivisa, usare il <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> metodo e passare di indice effettivo della riga. Se si accede di riga condivisa <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> proprietà al contrario, verrà utilizzato l'indice di riga condiviso-1 e non recupererà il menu di scelta rapida corretto.

- Evitare di indicizzare il <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> raccolta. Accesso diretto a una cella provocherà la riga padre e la rimozione della condivisione, un'istanza di un nuovo <xref:System.Windows.Forms.DataGridViewRow>. Gestori di eventi correlati alla cella ricevono oggetti argomento evento con le proprietà di cella che è possibile usare per modificare le celle senza che le righe non più condivise. È anche possibile usare il <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> proprietà di cui recuperare gli indici di riga e colonna della cella corrente senza accedere direttamente alla cella.

- Evitare le modalità di selezione basato sulle celle. Queste modalità che righe in cui viene rimossa. Al contrario, impostare il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> proprietà <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.

- Non gestire il <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> gli eventi. Questi eventi che righe in cui viene rimossa. Inoltre, non chiamare il <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> metodi che generano questi eventi.

- Non accedono i <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> raccolta quando il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> valore della proprietà <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>, o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>. In questo modo tutte le righe selezionate verrà annullata.

- Non chiamare il <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> (metodo). Questo metodo può causare righe venga rimossa.

- Non chiamare il <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> metodo quando il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> valore della proprietà è <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>. In questo modo tutte le righe in cui viene rimossa.

- Non impostare il <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> oppure <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> proprietà di una cella alle `false` quando la proprietà corrispondente nella relativa colonna è impostata su `true`. In questo modo tutte le righe in cui viene rimossa.

- Non accedere il <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> proprietà. In questo modo tutte le righe in cui viene rimossa.

- Non si chiama il `Sort(IComparer)` eseguire l'overload del <xref:System.Windows.Forms.DataGridView.Sort%2A> (metodo). L'ordinamento con un operatore di confronto personalizzato fa sì che tutte le righe in cui viene rimossa.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Stili delle celle nel controllo DataGridView di Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Form](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](sizing-options-in-the-windows-forms-datagridview-control.md)
