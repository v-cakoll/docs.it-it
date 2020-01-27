---
title: Uso della riga per i nuovi record nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
ms.openlocfilehash: 2fcd35f8c4d04909cdbc26f6a4293fdd570385b8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728343"
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Utilizzo della riga per i nuovi record del controllo DataGridView di Windows Form
Quando si usa un <xref:System.Windows.Forms.DataGridView> per la modifica dei dati nell'applicazione, spesso si vuole offrire agli utenti la possibilità di aggiungere nuove righe di dati all'archivio dati. Il controllo <xref:System.Windows.Forms.DataGridView> supporta questa funzionalità fornendo una riga per i nuovi record, che viene sempre visualizzata come ultima riga. È contrassegnato con un asterisco (*) nell'intestazione di riga. Le sezioni seguenti illustrano alcuni aspetti da considerare quando si programma con la riga per i nuovi record abilitati.  
  
## <a name="displaying-the-row-for-new-records"></a>Visualizzazione della riga per i nuovi record  
 Utilizzare la proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> per indicare se viene visualizzata la riga per i nuovi record. Il valore predefinito di questa proprietà è `true`.  
  
 Per il caso di associazione dati, la riga per i nuovi record verrà visualizzata se la proprietà <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> del controllo e la proprietà <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> dell'origine dati sono entrambe `true`. Se è `false`, la riga non verrà visualizzata.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Popolamento della riga per i nuovi record con dati predefiniti  
 Quando l'utente seleziona la riga per i nuovi record come riga corrente, il controllo <xref:System.Windows.Forms.DataGridView> genera l'evento <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded>.  
  
 Questo evento consente di accedere al nuovo <xref:System.Windows.Forms.DataGridViewRow> e di popolare la nuova riga con i dati predefiniti. Per altre informazioni, vedere [procedura: specificare i valori predefiniti per le nuove righe nel controllo DataGridView Windows Forms](specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>Raccolta Rows  
 La riga per i nuovi record è contenuta nella raccolta <xref:System.Windows.Forms.DataGridView.Rows%2A> del controllo <xref:System.Windows.Forms.DataGridView> ma si comporta in modo diverso in due punti:  
  
- Non è possibile rimuovere la riga per i nuovi record dalla raccolta <xref:System.Windows.Forms.DataGridView.Rows%2A> a livello di codice. Se si tenta di eseguire un'<xref:System.InvalidOperationException>, viene generata un'eccezione. L'utente non può inoltre eliminare la riga per i nuovi record. Il metodo <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> non rimuove questa riga dalla raccolta di <xref:System.Windows.Forms.DataGridView.Rows%2A>.  
  
- Non è possibile aggiungere alcuna riga dopo la riga per i nuovi record. Se si tenta di eseguire un <xref:System.InvalidOperationException>, viene generata un'eccezione. Di conseguenza, la riga per i nuovi record è sempre l'ultima riga nel controllo <xref:System.Windows.Forms.DataGridView>. I metodi su <xref:System.Windows.Forms.DataGridViewRowCollection> che aggiungono righe, ovvero<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>e <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, chiamano tutti i metodi di inserimento internamente quando è presente la riga per i nuovi record.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Personalizzazione visiva della riga per i nuovi record  
 Quando viene creata la riga per i nuovi record, si basa sulla riga specificata dalla proprietà <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>. Gli stili di cella non specificati per questa riga vengono ereditati da altre proprietà. Per ulteriori informazioni sull'ereditarietà dello stile della cella, vedere la pagina relativa agli [stili delle celle nel controllo DataGridView Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 I valori iniziali visualizzati dalle celle della riga per i nuovi record vengono recuperati dalla proprietà <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> della cella. Per le celle di tipo <xref:System.Windows.Forms.DataGridViewImageCell>, questa proprietà restituisce un'immagine segnaposto. In caso contrario la proprietà restituisce `null`. È possibile eseguire l'override di questa proprietà per restituire un valore personalizzato. Tuttavia, questi valori iniziali possono essere sostituiti da un gestore dell'evento <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> quando lo stato attivo immette la riga per i nuovi record.  
  
 Le icone standard per l'intestazione di questa riga, ovvero una freccia o un asterisco, non vengono esposte pubblicamente. Se si desidera personalizzare le icone, sarà necessario creare una classe di <xref:System.Windows.Forms.DataGridViewRowHeaderCell> personalizzata.  
  
 Le icone standard utilizzano la proprietà <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> della <xref:System.Windows.Forms.DataGridViewCellStyle> utilizzata dalla cella di intestazione di riga. Non viene eseguito il rendering delle icone standard se lo spazio disponibile non è sufficiente per visualizzarli completamente.  
  
 Se per la cella dell'intestazione di riga è impostato un valore di stringa e lo spazio disponibile non è sufficiente per il testo e l'icona, l'icona viene eliminata per prima.  
  
## <a name="sorting"></a>Ordinamento  
 In modalità non associata, i nuovi record verranno sempre aggiunti alla fine del <xref:System.Windows.Forms.DataGridView> anche se l'utente ha ordinato il contenuto della <xref:System.Windows.Forms.DataGridView>. L'utente dovrà applicare nuovamente l'ordinamento per ordinare la riga nella posizione corretta; Questo comportamento è simile a quello del controllo <xref:System.Windows.Forms.ListView>.  
  
 Nelle modalità di associazione dati e virtuali, il comportamento di inserimento quando viene applicato un ordinamento dipende dall'implementazione del modello di dati. Per ADO.NET, la riga viene immediatamente ordinata nella posizione corretta.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Altre note sulla riga per i nuovi record  
 Non è possibile impostare la proprietà <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> di questa riga su `false`. Se si tenta di eseguire un <xref:System.InvalidOperationException>, viene generata un'eccezione.  
  
 La riga per i nuovi record viene sempre creata con lo stato deselezionato.  
  
## <a name="virtual-mode"></a>Modalità virtuale  
 Se si implementa la modalità virtuale, sarà necessario tenere traccia del momento in cui è necessaria una riga per i nuovi record nel modello di dati e quando eseguire il rollback dell'aggiunta della riga. L'implementazione esatta di questa funzionalità dipende dall'implementazione del modello di dati e dalla relativa semantica di transazione, ad esempio se l'ambito del commit è a livello di cella o di riga. Per ulteriori informazioni, vedere [modalità virtuale nel controllo DataGridView Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>
- [Immissione di dati nel controllo DataGridView di Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedura: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView di Windows Form](specify-default-values-for-new-rows-in-the-datagrid.md)
