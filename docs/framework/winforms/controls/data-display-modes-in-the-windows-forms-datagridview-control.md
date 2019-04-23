---
title: Modalità di visualizzazione dati nel controllo DataGridView di Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: 673780909f6d66168548893e99d79bbfec70a0e0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079695"
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Modalità di visualizzazione dati nel controllo DataGridView di Windows Form
Il <xref:System.Windows.Forms.DataGridView> controllo può visualizzare i dati in tre diverse modalità: associato, non associato e virtuali. Scegliere la modalità più adatta in base alle esigenze.  
  
## <a name="unbound"></a>Non associato  
 Modalità non associata è adatta per la visualizzazione delle quantità relativamente piccole di dati gestiti a livello di codice. Non collegare il <xref:System.Windows.Forms.DataGridView> controllo direttamente a un'origine dati come modalità di associazione. In alternativa, è necessario popolare il controllo manualmente, in genere usando il <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> (metodo).  
  
 Modalità non associata può essere particolarmente utile per i dati statici di sola lettura, o quando si desidera fornire il proprio codice che interagisce con un archivio dati esterno. Quando si desidera che gli utenti interagiscono con un'origine dati esterna, tuttavia, si useranno la modalità associata.  
  
 Per un esempio che usa una proprietà di sola lettura unbound <xref:System.Windows.Forms.DataGridView>, vedere [come: Creare un controllo DataGridView di Windows non associato form](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="bound"></a>Associato  
 Modalità di associazione è adatta per la gestione dei dati mediante l'interazione automatica con l'archivio dati. È possibile collegare il <xref:System.Windows.Forms.DataGridView> controllo direttamente all'origine dati impostando il <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà. Quando il controllo è associato a dati, le righe di dati vengono effettuato il push e pull senza la necessità di gestione esplicita da parte dell'utente. Quando la <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> è di proprietà `true`, ogni colonna nell'origine dati causerà una colonna corrispondente deve essere creato nel controllo. Se si preferisce creare colonne personalizzate, è possibile impostare questa proprietà `false` e usare il <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> proprietà alla quale associare ogni colonna al momento della configurazione. Ciò è utile quando si vuole usare un tipo di colonna diversi da quelli generati per impostazione predefinita. Per altre informazioni, vedere [tipi di colonne nel controllo DataGridView Windows Form](column-types-in-the-windows-forms-datagridview-control.md).  
  
 Per un esempio che usa un oggetto associato <xref:System.Windows.Forms.DataGridView> controllano, vedere [procedura dettagliata: Convalida dei dati in di Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 È anche possibile aggiungere colonne non associate a un <xref:System.Windows.Forms.DataGridView> controllo in modalità di associazione. Ciò è utile quando si desidera visualizzare una colonna di pulsanti o collegamenti che consentono agli utenti di eseguire azioni su righe specifiche. È anche utile visualizzare le colonne con i valori calcolati dalle colonne associate. È possibile popolare i valori delle celle per le colonne calcolate in un gestore per il <xref:System.Windows.Forms.DataGridView.CellFormatting> evento. Se si usa un' <xref:System.Data.DataSet> oppure <xref:System.Data.DataTable> come origine dati, tuttavia, si potrebbe voler usare il <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> proprietà per creare invece una colonna calcolata. In questo caso, il <xref:System.Windows.Forms.DataGridView> controllo considera la colonna calcolata esattamente come qualsiasi altra colonna nell'origine dati.  
  
 Ordinamento in base a colonne non associate in modalità di associazione non è supportato. Se si crea una colonna non associata in modalità di associazione che contiene i valori modificabili dall'utente, è necessario implementare modalità virtuale per gestire questi valori quando il controllo viene ordinato in base a una colonna associata.  
  
## <a name="virtual"></a>Virtuale  
 La modalità virtuale, è possibile implementare il proprio operazioni di gestione dati. Ciò è necessario mantenere i valori delle colonne non associate in modalità di associazione quando il controllo viene ordinato in base a colonne associate. L'utilizzo principale della modalità virtuale, tuttavia, consiste nell'ottimizzare le prestazioni durante l'interazione con grandi quantità di dati.  
  
 Si collega il <xref:System.Windows.Forms.DataGridView> controllo a una cache gestita dall'utente e i controlli di codice quando le righe di dati vengono effettuato il push e pull. Per ridurre il footprint di memoria, la cache deve essere simile al numero di righe attualmente visualizzate. Quando l'utente scorre nuove righe all'interno della visualizzazione, il codice richiede nuovi dati dalla cache e, facoltativamente, Elimina i dati obsoleti dalla memoria.  
  
 Quando si implementa la modalità virtuale, è necessario rilevare quando una nuova riga è necessaria nel modello di dati e quando eseguire il rollback, l'aggiunta della nuova riga. L'implementazione esatta di questa funzionalità variano in base l'implementazione del modello di dati e la semantica delle transazioni del modello di dati; indica se l'ambito di commit è a livello di cella o riga.  
  
 Per altre informazioni sulla modalità virtuale, vedere [modalità virtuale nel controllo DataGridView Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md). Per un esempio che illustra come usare eventi in modalità virtuale, vedere [procedura dettagliata: Implementazione della modalità virtuale in Windows il controllo DataGridView form](implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>
- [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Tipi di colonne nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Creazione di una cornice di Windows Form controllo DataGridView](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Procedura: Associare dati al controllo DataGridView Windows Form](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
- [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView Windows Form](implementing-virtual-mode-wf-datagridview-control.md)
