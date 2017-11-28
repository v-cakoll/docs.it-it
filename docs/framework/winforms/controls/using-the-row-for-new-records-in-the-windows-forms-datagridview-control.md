---
title: Utilizzo della riga per i nuovi record del controllo DataGridView di Windows Form
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], adding rows for new records
- rows [Windows Forms], new records
- DataGridView control [Windows Forms], data entry
ms.assetid: 6110f1ea-9794-442c-a98a-f104a1feeaf4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4633a70f6c3d010e6cc75236778cf2fd59c0e05
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-row-for-new-records-in-the-windows-forms-datagridview-control"></a>Utilizzo della riga per i nuovi record del controllo DataGridView di Windows Form
Quando si utilizza un <xref:System.Windows.Forms.DataGridView> per la modifica dei dati nell'applicazione, spesso si desidera offrire agli utenti la possibilità di aggiungere nuove righe di dati nell'archivio dati. Il <xref:System.Windows.Forms.DataGridView> controllo supporta questa funzionalità fornendo una riga per nuovi record, che viene sempre visualizzata come ultima riga. È contrassegnato con un asterisco (*) nella relativa intestazione di riga. Le sezioni seguenti illustrano alcune delle operazioni che è necessario considerare quando si programma con la riga per nuovi record abilitato.  
  
## <a name="displaying-the-row-for-new-records"></a>Visualizzazione della riga per nuovi record  
 Utilizzare il <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> proprietà che indica se viene visualizzata la riga per nuovi record. Il valore predefinito di questa proprietà è `true`.  
  
 Per i dati associati, la riga per nuovi record viene visualizzata se il <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> proprietà del controllo e <xref:System.ComponentModel.IBindingList.AllowNew%2A?displayProperty=nameWithType> proprietà dell'origine dati sono entrambi `true`. Se si verifica una `false` quindi non verrà visualizzata la riga.  
  
## <a name="populating-the-row-for-new-records-with-default-data"></a>Compilazione della riga per nuovi record con dati predefiniti  
 Quando l'utente seleziona la riga per nuovi record come riga corrente, il <xref:System.Windows.Forms.DataGridView> controllo genera il <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> evento.  
  
 Questo evento fornisce l'accesso al nuovo <xref:System.Windows.Forms.DataGridViewRow> e consente di popolare la nuova riga con dati predefiniti. Per ulteriori informazioni, vedere [procedura: specificare i valori predefiniti per le nuove righe nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)  
  
## <a name="the-rows-collection"></a>Raccolta delle righe  
 La riga per nuovi record è contenuta nel <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.Rows%2A> insieme ma si comporta in modo diverso in due aspetti:  
  
-   Impossibile rimuovere la riga per nuovi record dal <xref:System.Windows.Forms.DataGridView.Rows%2A> insieme a livello di codice. Un <xref:System.InvalidOperationException> viene generata se questo viene eseguito un tentativo. L'utente inoltre è possibile eliminare la riga per nuovi record. Il <xref:System.Windows.Forms.DataGridViewRowCollection.Clear%2A?displayProperty=nameWithType> metodo non rimuove la riga dal <xref:System.Windows.Forms.DataGridView.Rows%2A> insieme.  
  
-   È non possibile aggiungere alcuna riga dopo la riga per nuovi record. Un <xref:System.InvalidOperationException> viene generato se questo viene eseguito un tentativo. Di conseguenza, la riga per nuovi record è sempre l'ultima riga di <xref:System.Windows.Forms.DataGridView> controllo. I metodi di <xref:System.Windows.Forms.DataGridViewRowCollection> che aggiungono righe:<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, e <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>: chiamano tutti internamente i metodi di inserimento quando è presente la riga per nuovi record.  
  
## <a name="visual-customization-of-the-row-for-new-records"></a>Personalizzazione della visualizzazione della riga per nuovi record  
 Quando viene creata la riga per nuovi record, è basata la riga specificata per il <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> proprietà. Tutti gli stili di cella che non sono specificati per questa riga vengono ereditati da altre proprietà. Per ulteriori informazioni sull'ereditarietà, vedere [stili della cella nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 I valori iniziali visualizzati dalle celle nella riga per nuovi record vengono recuperati da ogni cella <xref:System.Windows.Forms.DataGridViewCell.DefaultNewRowValue%2A> proprietà. Per le celle di tipo <xref:System.Windows.Forms.DataGridViewImageCell>, questa proprietà restituisce un'immagine segnaposto. In caso contrario la proprietà restituisce `null`. È possibile eseguire l'override di questa proprietà per restituire un valore personalizzato. Tuttavia, i valori iniziali possono essere sostituiti da un <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded> gestore dell'evento quando lo stato attivo passa la riga per nuovi record.  
  
 Le icone standard per l'intestazione della riga, che sono una freccia o un asterisco, non vengono esposte pubblicamente. Se si desidera personalizzare le icone, sarà necessario creare una classe personalizzata <xref:System.Windows.Forms.DataGridViewRowHeaderCell> classe.  
  
 Icone standard utilizzano la <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> proprietà del <xref:System.Windows.Forms.DataGridViewCellStyle> in uso nella cella di intestazione di riga. Icone standard non viene eseguite se non c'è spazio sufficiente per visualizzarli completamente.  
  
 Se la cella di intestazione di riga è un valore stringa impostato e se non c'è spazio sufficiente per il testo e l'icona, è prima eliminato l'icona.  
  
## <a name="sorting"></a>Ordinamento  
 In modalità non associata, nuovi record vengono sempre aggiunti alla fine del <xref:System.Windows.Forms.DataGridView> anche se l'utente è stato ordinato il contenuto del <xref:System.Windows.Forms.DataGridView>. L'utente sarà necessario applicare nuovamente l'ordinamento per ordinare la riga nella posizione corretta; Questo comportamento è simile a quello del <xref:System.Windows.Forms.ListView> controllo.  
  
 Nei dati di modalità associata e virtuale, il comportamento di inserimento quando viene applicato un ordinamento sarà dipende dall'implementazione del modello di dati. Per [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], la riga viene immediatamente ordinata nella posizione corretta.  
  
## <a name="other-notes-on-the-row-for-new-records"></a>Altre note nella riga per nuovi record  
 Non è possibile impostare il <xref:System.Windows.Forms.DataGridViewRow.Visible%2A> proprietà di questa riga per `false`. Un <xref:System.InvalidOperationException> viene generato se questo viene eseguito un tentativo.  
  
 La riga per nuovi record viene sempre creata nello stato non selezionato.  
  
## <a name="virtual-mode"></a>Modalità virtuale  
 Se si implementa la modalità virtuale, è necessario tenere traccia di quando è necessaria una riga per nuovi record nel modello di dati e quando il rollback dell'aggiunta della riga. L'implementazione esatta di questa funzionalità dipende dall'implementazione del modello di dati e la semantica delle transazioni, ad esempio, se l'ambito di commit è a livello di cella o riga. Per ulteriori informazioni, vedere [modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DefaultValuesNeeded?displayProperty=nameWithType>  
 [Immissione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Specificare i valori predefiniti per le nuove righe nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/specify-default-values-for-new-rows-in-the-datagrid.md)
