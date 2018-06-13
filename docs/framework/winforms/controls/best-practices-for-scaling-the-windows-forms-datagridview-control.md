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
ms.openlocfilehash: 91153df539871de571375d7bf6d49d712a0c43b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529808"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Procedure consigliate per ridimensionare il controllo DataGridView Windows Form
Il <xref:System.Windows.Forms.DataGridView> controllo è progettato per fornire la massima scalabilità. Se è necessario visualizzare grandi quantità di dati, è necessario seguire le linee guida descritte in questo argomento per evitare l'utilizzo di grandi quantità di memoria o diminuire la velocità di risposta dell'interfaccia utente (UI). In questo argomento vengono illustrati i problemi seguenti:  
  
-   Utilizzo efficiente di stili di cella  
  
-   Utilizzo efficiente di menu di scelta rapida  
  
-   Utilizzo in modo efficiente il ridimensionamento automatico  
  
-   Utilizzando le raccolte di celle, righe e colonne selezionate in modo efficiente  
  
-   Utilizzo di righe condivise  
  
-   Impedisce la rimozione della condivisione di righe  
  
 Se si dispone delle prestazioni di particolari esigenze, è possibile implementare la modalità virtuale e fornire operazioni di gestione dati. Per ulteriori informazioni, vedere [modalità di visualizzazione di dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-cell-styles-efficiently"></a>Utilizzo efficiente di stili di cella  
 Ogni cella, riga e colonna può avere le proprie informazioni di stile. Informazioni di stile vengono archiviate in <xref:System.Windows.Forms.DataGridViewCellStyle> oggetti. La creazione degli oggetti di stile di cella per molti singoli <xref:System.Windows.Forms.DataGridView> elementi possono risultare inefficienti, specialmente quando si lavora con grandi quantità di dati. Per evitare un impatto sulle prestazioni, utilizzare le linee guida seguenti:  
  
-   Evitare di impostare le proprietà di stile di cella per singoli <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewRow> oggetti. Ciò include l'oggetto riga specificato per il <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> proprietà. Ogni nuova riga viene clonato dal modello di riga riceverà la propria copia dell'oggetto stile di cella del modello. Per ottenere la massima scalabilità, impostare le proprietà di stile di cella nel <xref:System.Windows.Forms.DataGridView> livello. Ad esempio, impostare il <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> proprietà anziché <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> proprietà.  
  
-   Se alcune celle è necessaria una formattazione diversa da quella predefinita, utilizzare lo stesso <xref:System.Windows.Forms.DataGridViewCellStyle> istanza tra gruppi di celle, righe o colonne. Evitare di impostare direttamente le proprietà di tipo <xref:System.Windows.Forms.DataGridViewCellStyle> su singole celle, righe e colonne. Per un esempio di stile di cella condivisione, vedere [procedura: impostare stili di cella predefiniti per il controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). È anche possibile evitare una riduzione delle prestazioni durante l'impostazione di stili di cella singolarmente mediante la gestione di <xref:System.Windows.Forms.DataGridView.CellFormatting> gestore dell'evento. Per un esempio, vedere [procedura: personalizzare la formattazione dei dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
-   Quando si determina uno stile di cella, utilizzare il <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> proprietà anziché <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> proprietà. L'accesso al <xref:System.Windows.Forms.DataGridViewCell.Style%2A> proprietà consente di creare una nuova istanza di <xref:System.Windows.Forms.DataGridViewCellStyle> classe se la proprietà non è già stata utilizzata. Inoltre, l'oggetto potrebbe non contenere le informazioni di stile complete per la cella se alcuni stili vengono ereditate dalla riga, colonna o dal controllo. Per ulteriori informazioni sull'ereditarietà, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-shortcut-menus-efficiently"></a>Utilizzo efficiente di menu di scelta rapida  
 Ogni cella, riga e colonna può avere il proprio menu di scelta rapida. Menu di scelta rapida di <xref:System.Windows.Forms.DataGridView> controllo sono rappresentati da <xref:System.Windows.Forms.ContextMenuStrip> controlli. Come con gli oggetti di stile di cella, la creazione di menu di scelta rapida per molti singoli <xref:System.Windows.Forms.DataGridView> elementi influirà negativamente sulle prestazioni. Per evitare questo problema, utilizzare le linee guida seguenti:  
  
-   Evitare di creare menu di scelta rapida per le singole celle e righe. Ciò include il modello di riga, viene duplicato e il relativo menu di scelta rapida quando nuove righe vengono aggiunte al controllo. Per ottenere la massima scalabilità, utilizzare solo del controllo <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> proprietà per specificare un menu di scelta rapida solo per l'intero controllo.  
  
-   Se sono necessari più menu di scelta rapida per più righe o celle, gestire il <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> o <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> eventi. Questi eventi consentono di gestire il menu di scelta rapida manualmente, che consente di ottimizzare le prestazioni.  
  
## <a name="using-automatic-resizing-efficiently"></a>Utilizzo in modo efficiente il ridimensionamento automatico  
 Le righe, colonne e le intestazioni possono essere ridimensionate automaticamente come modifiche del contenuto cella in modo che l'intero contenuto delle celle viene visualizzato senza troncamenti. Modifica delle modalità di ridimensionamento anche possibile ridimensionare righe, colonne e intestazioni. Per determinare le dimensioni corrette, il <xref:System.Windows.Forms.DataGridView> controllo deve esaminare il valore di ogni cella che è necessario consentirne l'utilizzo. Quando si lavora con grandi set di dati, questa analisi può influire negativamente sulle prestazioni del controllo quando si verifica il ridimensionamento automatico. Per evitare effetti negativi sulle prestazioni, utilizzare le linee guida seguenti:  
  
-   Evitare di utilizzare il ridimensionamento automatico in un <xref:System.Windows.Forms.DataGridView> controllo con un ampio set di righe. Se si utilizza il ridimensionamento automatico, ridimensionare solo le righe visualizzate. Utilizzare solo le righe visualizzate in modalità virtuale.  
  
    -   Per le righe e colonne, utilizzare il `DisplayedCells` o `DisplayedCellsExceptHeaders` campo il <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>, e <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> enumerazioni.  
  
    -   Per le intestazioni di riga, utilizzare il <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> o <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> campo il <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> enumerazione.  
  
-   Per ottenere la massima scalabilità, disattivare il ridimensionamento automatico e utilizzare il ridimensionamento a livello di codice.  
  
 Per ulteriori informazioni, vedere [opzioni di ridimensionamento nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Utilizzo efficiente di celle, righe e le raccolte di colonne  
 Il <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> insieme non viene eseguito in modo efficiente con selezioni di grandi dimensioni. Il <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> e <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> raccolte anche possono risultare inefficiente, anche se a un livello inferiore perché sono presenti molte righe minore del numero di celle in una tipica <xref:System.Windows.Forms.DataGridView> controllo e molte meno colonne che righe. Per evitare effetti negativi sulle prestazioni quando si utilizzano queste raccolte, utilizzare le linee guida seguenti:  
  
-   Per determinare se tutte le celle di <xref:System.Windows.Forms.DataGridView> sono state selezionate prima dell'accesso al contenuto del <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> insieme, controllare il valore restituito del <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> (metodo). Si noti tuttavia che questo metodo può causare righe venga rimossa. Per altre informazioni, vedere la sezione successiva.  
  
-   Evitare di utilizzare il <xref:System.Collections.ICollection.Count%2A> proprietà del <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> per determinare il numero di celle selezionate. Utilizzare invece il <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> (metodo) e passare il <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> valore. Analogamente, utilizzare il <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> metodi per determinare il numero di elementi selezionati, anziché l'accesso alle raccolte di righe e colonne selezionate.  
  
-   Evitare le modalità di selezione basata sulla cella. Al contrario, impostare il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> proprietà <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
## <a name="using-shared-rows"></a>Uso di righe condivisi  
 Utilizzo efficiente della memoria viene eseguito nel <xref:System.Windows.Forms.DataGridView> controllo condivisione delle righe. Le righe condividono le informazioni sul relativo aspetto e comportamento possibile la condivisione delle istanze del <xref:System.Windows.Forms.DataGridViewRow> classe.  
  
 Mentre la condivisione delle istanze di riga, potrai risparmiare memoria, righe può facilmente essere rimossa. Ad esempio, ogni volta che un utente interagisce direttamente con una cella, la riga viene rimossa. Poiché non è possibile evitare questo, le linee guida fornite in questo argomento sono utili solo quando si lavora con grandi quantità di dati e solo quando gli utenti interagiscono con una relativamente piccola parte dei dati ogni volta che viene eseguito il programma.  
  
 Una riga non può essere condivisi in un oggetto non associato <xref:System.Windows.Forms.DataGridView> controllare se una delle relative celle contengono valori. Quando il <xref:System.Windows.Forms.DataGridView> è associato a un'origine dati esterna o quando si implementa la modalità virtuale e fornire la propria origine dati, i valori di cella vengono archiviati all'esterno del controllo anziché in oggetti cella, consentendo la condivisione delle righe.  
  
 Un oggetto riga può essere condiviso solo se lo stato di tutte le relative celle, è possibile determinare lo stato della riga e degli stati delle colonne contenenti le celle. Se si modifica lo stato di una cella in modo che non può essere dedotto dallo stato della relativa riga e colonna, la riga non può essere condivisa.  
  
 Ad esempio, una riga non può essere condivisa in una delle situazioni seguenti:  
  
-   La riga contiene una singola cella selezionata che non è presente in una colonna selezionata.  
  
-   La riga contiene una cella con il relativo <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> o <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> set di proprietà.  
  
-   La riga contiene un <xref:System.Windows.Forms.DataGridViewComboBoxCell> con il relativo <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> set di proprietà.  
  
 In modalità di associazione o la modalità virtuale, è possibile fornire le descrizioni comandi e menu di scelta rapida per le singole celle gestendo il <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> e <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> eventi.  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo tenterà automaticamente di utilizzare le righe condivise ogni volta che vengono aggiunte righe di <xref:System.Windows.Forms.DataGridViewRowCollection>. Utilizzare le linee guida seguenti per assicurarsi che le righe vengono condivisi:  
  
-   Evitare di chiamare il `Add(Object[])` overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> (metodo) e `Insert(Object[])` overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> metodo il <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> insieme. Questi overload creano automaticamente righe non condivise.  
  
-   Assicurarsi che la riga specificata nel <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> proprietà può essere condivisi nei casi seguenti:  
  
    -   Quando si chiama il `Add()` o `Add(Int32)` gli overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> (metodo) o `Insert(Int32,Int32)` overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> metodo il <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> insieme.  
  
    -   Quando viene incrementato il valore della <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> proprietà.  
  
    -   Quando si imposta la <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> proprietà.  
  
-   Assicurarsi che la riga indicata dal `indexSource` parametro può essere condivisa quando si chiama il <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>, e <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> metodi del <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> insieme.  
  
-   Assicurarsi che la riga specificata o le righe possono essere condivisa quando si chiama il `Add(DataGridViewRow)` overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> (metodo), il <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> (metodo), il `Insert(Int32,DataGridViewRow)` overload del <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> (metodo) e <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> metodo il <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>insieme.  
  
 Per determinare se una riga è condivisa, utilizzare il <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> metodo per recuperare l'oggetto riga e quindi selezionare l'oggetto <xref:System.Windows.Forms.DataGridViewBand.Index%2A> proprietà. Righe condivise hanno sempre un <xref:System.Windows.Forms.DataGridViewBand.Index%2A> valore della proprietà di – 1.  
  
## <a name="preventing-rows-from-becoming-unshared"></a>Impedisce la rimozione della condivisione di righe  
 Righe condivise può essere rimossa in seguito a un'azione utente o di codice. Per evitare un impatto sulle prestazioni, è necessario evitare che le righe verrà annullata. Durante lo sviluppo di applicazioni, è possibile gestire il <xref:System.Windows.Forms.DataGridView.RowUnshared> evento per determinare quando le righe diventano non condivise. Ciò è utile quando il debug di problemi di condivisione delle righe.  
  
 Per impedire la rimozione della condivisione di righe, utilizzare le linee guida seguenti:  
  
-   Evitare l'indicizzazione di <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta o l'iterazione con un `foreach` ciclo. In genere non è necessario accedere direttamente alle righe. <xref:System.Windows.Forms.DataGridView> i metodi che operano sulle righe accettano gli argomenti di indice di riga invece istanze della riga. Inoltre, gestori di eventi relativi alle righe ricevono oggetti di argomento dell'evento con le proprietà di riga che è possibile utilizzare per modificare le righe senza che ne venga annullata.  
  
-   Se è necessario accedere a un oggetto riga, utilizzare il <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> (metodo) e passare di indice effettivo la riga. Si noti tuttavia che la modifica di un oggetto riga condivisa recuperato mediante questo metodo modificare tutte le righe che condividono questo oggetto. La riga per nuovi record non è condivisa con altre righe, tuttavia, in modo che non sarà interessata quando si modifica qualsiasi altra riga. Si noti inoltre che il menu di scelta rapida diversi possono disporre di diverse righe rappresentata da una riga condivisa. Per recuperare il menu di scelta rapida corretto dall'istanza di una riga condivisa, utilizzare il <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> (metodo) e passare di indice effettivo la riga. Se si accede della riga condivisa <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> proprietà, invece, verrà utilizzato l'indice di riga condivisa di -1 e non verrà recuperato il menu di scelta rapida corretto.  
  
-   Evitare l'indicizzazione di <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> insieme. Accesso diretto a una cella provocherà la riga padre e la rimozione della condivisione, creare un'istanza di un nuovo <xref:System.Windows.Forms.DataGridViewRow>. Gestori di eventi correlati alla cella ricevono oggetti di argomento dell'evento con le proprietà di cella che è possibile utilizzare per modificare le celle senza causare righe venga rimossa. È inoltre possibile utilizzare il <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> proprietà per recuperare gli indici di riga e di colonna della cella corrente senza accedere direttamente alla cella.  
  
-   Evitare le modalità di selezione basata sulla cella. Queste modalità provocano righe non condivise. Al contrario, impostare il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> proprietà <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
-   Non gestire la <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> eventi. Questi eventi provocano righe non condivise. Inoltre, non chiamare il <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> metodi, la generazione di questi eventi.  
  
-   Non accedere il <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> raccolta quando il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> valore della proprietà è <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>, o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>. In questo modo tutte le righe selezionate verrà annullata.  
  
-   Non chiamare il <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> metodo. Questo metodo può causare righe venga rimossa.  
  
-   Non chiamare il <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> metodo quando il <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> valore della proprietà è <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>. In questo modo tutte le righe per la rimozione della condivisione.  
  
-   Non impostare il <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> o <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> proprietà di una cella per `false` quando è impostata la proprietà corrispondente nella colonna `true`. In questo modo tutte le righe per la rimozione della condivisione.  
  
-   Non accedere il <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> proprietà. In questo modo tutte le righe per la rimozione della condivisione.  
  
-   Non chiamare il `Sort(IComparer)` overload di <xref:System.Windows.Forms.DataGridView.Sort%2A> metodo. Ordinamento con un operatore di confronto personalizzato fa sì che tutte le righe per la rimozione della condivisione.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Modo virtuale nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Modalità di visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 [Stili delle celle nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Opzioni di ridimensionamento nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)
