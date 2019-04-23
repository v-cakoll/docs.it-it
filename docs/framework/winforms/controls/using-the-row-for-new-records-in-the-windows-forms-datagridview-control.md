---
title: Utilizzo della riga per i nuovi record del controllo DataGridView di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 67c87b28f04b028f329663d6cf8215370a00ef2f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59184821"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Utilizzo della riga per i nuovi record del controllo DataGridView di Windows Form
Quando si usa un <xref:System.Windows.Forms.DataGridView> per la modifica dei dati nell'applicazione, spesso si desidera offrire agli utenti la possibilità di aggiungere nuove righe di dati nell'archivio dati. Il <xref:System.Windows.Forms.DataGridView> controllo supporta questa funzionalità, fornendo una riga per i nuovi record, che viene sempre visualizzata come ultima riga. È contrassegnato con un simbolo di asterisco (*) l'intestazione di riga. Le sezioni seguenti illustrano alcune delle attività che è necessario considerare quando si programma con la riga per i nuovi record abilitato.  
  
## <a name="displaying-the-row-for-new-records"></a>Visualizzazione della riga per i nuovi record  
 Usare il <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> proprietà che indica se viene visualizzata la riga per i nuovi record. Il valore predefinito di questa proprietà è `true`.  
  
 Per i dati associati, la riga per i nuovi record verrà visualizzata se il <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> proprietà del controllo e il <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> proprietà dell'origine dati sono entrambi `true`. Se si verifica una `false` quindi la riga non verrà visualizzata.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Compilazione della riga per i nuovi record con i dati predefiniti  
 Quando l'utente seleziona la riga per i nuovi record della riga corrente, il <xref:System.Windows.Forms.DataGridView> controllare genera il <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.  
  
 Questo evento fornisce l'accesso al nuovo <xref:System.Windows.Forms.DataGridViewRow> e consente all'utente popolare la nuova riga con i dati predefiniti. Per altre informazioni, vedere [Procedura: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView Windows Form](specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>La raccolta di righe  
 La riga per i nuovi record è contenuta nel <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta ma si comporta in modo diverso per due aspetti:  
  
-   Impossibile rimuovere la riga per i nuovi record dal <xref:System.Windows.Forms.DataGridView.Rows%2A> insieme a livello di codice. Un <xref:System.InvalidOperationException> viene generata se questo tentativo. L'utente non è possibile anche eliminare la riga per i nuovi record. Il <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> metodo non rimuove questa riga dal <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta.  
  
-   È possibile aggiungere alcuna riga dopo la riga per i nuovi record. Un <xref:System.InvalidOperationException> viene generato se si tenta. Di conseguenza, la riga per i nuovi record è sempre l'ultima riga il <xref:System.Windows.Forms.DataGridView> controllo. I metodi sul <xref:System.Windows.Forms.DataGridViewRowCollection> che aggiungono righe, ovvero<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, e <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, ovvero tutti chiamano metodi di inserimento internamente quando è presente la riga per i nuovi record.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Personalizzazione della visualizzazione della riga per i nuovi record  
 Quando viene creata la riga per i nuovi record, si basa sulla riga specificata per il <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> proprietà. Gli stili delle celle che non sono specificati per questa riga vengono ereditati da altre proprietà. Per altre informazioni sull'ereditarietà, vedere [stili della cella nel controllo DataGridView Windows Form](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 I valori iniziali visualizzati dalle celle nella riga per nuovi record vengono recuperati da ogni cella <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> proprietà. Per le celle di tipo <xref:System.Windows.Forms.DataGridViewImageCell>, questa proprietà restituisce un'immagine segnaposto. In caso contrario la proprietà restituisce `null`. È possibile eseguire l'override di questa proprietà per restituire un valore personalizzato. Tuttavia, i valori iniziali possono essere sostituiti da un <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> gestore dell'evento quando lo stato attivo viene spostato la riga per i nuovi record.  
  
 Le icone standard per l'intestazione della riga, ovvero una freccia o un asterisco, non sono esposte pubblicamente. Se si desidera personalizzare le icone, è necessario creare un oggetto personalizzato <xref:System.Windows.Forms.DataGridViewRowHeaderCell> classe.  
  
 Le icone standard utilizzano la <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> proprietà del <xref:System.Windows.Forms.DataGridViewCellStyle> in uso nella cella di intestazione di riga. Le icone standard non viene eseguite se non c'è spazio sufficiente per visualizzarle completamente.  
  
 Se la cella di intestazione di riga ha un valore stringa impostato e se non c'è spazio sufficiente per il testo e l'icona, è prima eliminato l'icona.  
  
## <a name="sorting"></a>Ordinamento  
 In modalità non associata, nuovi record vengono sempre aggiunti alla fine della <xref:System.Windows.Forms.DataGridView> anche se l'utente ha ordinato il contenuto del <xref:System.Windows.Forms.DataGridView>. L'utente dovrà applicare nuovamente l'ordinamento per ordinare la riga nella posizione corretta; Questo comportamento è simile a quella del <xref:System.Windows.Forms.ListView> controllo.  
  
 Nei dati di modalità associata e virtuale, il comportamento di inserimento quando viene applicato un ordinamento sarà dipende dall'implementazione del modello di dati. Per [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], la riga viene immediatamente ordinata nella posizione corretta.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Altre note sulla riga per i nuovi record  
 Non è possibile impostare il <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> proprietà di questa riga a `false`. Un <xref:System.InvalidOperationException> viene generato se si tenta.  
  
 La riga per i nuovi record viene sempre creata nello stato deselezionato.  
  
## <a name="virtual-mode"></a>Modalità virtuale  
 Se si implementa la modalità virtuale, è necessario tenere traccia di quando è necessaria una riga per i nuovi record nel modello di dati e quando il rollback dell'aggiunta della riga. L'implementazione esatta di questa funzionalità dipende dall'implementazione del modello di dati e la relativa semantica di transazione, ad esempio, se il commit ambito è a livello di riga o cella. Per altre informazioni, vedere [modalità virtuale nel controllo DataGridView Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Immissione di dati nel controllo DataGridView di Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedura: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView Windows Form](specify-default-values-for-new-rows-in-the-datagrid.md)
