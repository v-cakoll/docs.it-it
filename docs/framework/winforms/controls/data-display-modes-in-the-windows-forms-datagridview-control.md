---
title: Modalità di visualizzazione dei dati nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], display modes
- data grids [Windows Forms], display modes
- DataGridView control [Windows Forms], display modes
ms.assetid: 9755a030-3f3f-4705-a661-ba5a48a81875
ms.openlocfilehash: ad6be647e3a36904b055fd6771f539df28938fab
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744012"
---
# <a name="data-display-modes-in-the-windows-forms-datagridview-control"></a>Modalità di visualizzazione dati nel controllo DataGridView di Windows Form
Il controllo <xref:System.Windows.Forms.DataGridView> è in grado di visualizzare i dati in tre modalità distinte, ovvero binding, non associato e virtuale. Scegliere la modalità più adatta in base alle esigenze.  
  
## <a name="unbound"></a>Svincolato  
 La modalità non associata è adatta per la visualizzazione di quantità relativamente piccole di dati gestiti a livello di codice. Non è possibile associare il controllo <xref:System.Windows.Forms.DataGridView> direttamente a un'origine dati in modalità di associazione. È invece necessario popolare il controllo autonomamente, in genere utilizzando il metodo <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType>.  
  
 La modalità non associata può essere particolarmente utile per i dati statici di sola lettura o quando si desidera fornire codice personalizzato che interagisce con un archivio dati esterno. Quando si desidera che gli utenti interagisca con un'origine dati esterna, tuttavia, in genere si utilizzerà la modalità associata.  
  
 Per un esempio in cui viene usato un <xref:System.Windows.Forms.DataGridView>di sola lettura non associato, vedere [procedura: creare un controllo DataGridView Windows Forms non associato](how-to-create-an-unbound-windows-forms-datagridview-control.md).  
  
## <a name="bound"></a>Associato  
 La modalità associata è adatta per la gestione dei dati tramite l'interazione automatica con l'archivio dati. È possibile alleghi il controllo <xref:System.Windows.Forms.DataGridView> direttamente alla relativa origine dati impostando la proprietà <xref:System.Windows.Forms.DataGridView.DataSource%2A>. Quando il controllo è associato ai dati, viene effettuato il push e il pull delle righe di dati senza che sia necessaria una gestione esplicita da parte dell'utente. Quando la proprietà <xref:System.Windows.Forms.DataGridView.AutoGenerateColumns%2A> è `true`, ogni colonna nell'origine dati provocherà la creazione di una colonna corrispondente nel controllo. Se si preferisce creare colonne personalizzate, è possibile impostare questa proprietà su `false` e utilizzare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A> per associare ogni colonna quando viene configurata. Questa operazione è utile quando si desidera utilizzare un tipo di colonna diverso dai tipi generati per impostazione predefinita. Per ulteriori informazioni, vedere la pagina relativa ai [tipi di colonna nel controllo DataGridView Windows Forms](column-types-in-the-windows-forms-datagridview-control.md).  
  
 Per un esempio in cui viene usato un controllo <xref:System.Windows.Forms.DataGridView> associato, vedere [procedura dettagliata: convalida dei dati nel controllo DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
 È anche possibile aggiungere colonne non vincolate a un controllo <xref:System.Windows.Forms.DataGridView> in modalità di associazione. Questa opzione è utile quando si desidera visualizzare una colonna di pulsanti o collegamenti che consentono agli utenti di eseguire azioni su righe specifiche. È inoltre utile visualizzare le colonne con valori calcolati dalle colonne associate. È possibile popolare i valori delle celle per le colonne calcolate in un gestore per l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting>. Se si utilizza un <xref:System.Data.DataSet> o <xref:System.Data.DataTable> come origine dati, tuttavia, potrebbe essere necessario utilizzare la proprietà <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType> per creare una colonna calcolata. In questo caso, il controllo <xref:System.Windows.Forms.DataGridView> considererà la colonna calcolata come qualsiasi altra colonna nell'origine dati.  
  
 L'ordinamento in base a colonne non vincolate in modalità di associazione non è supportato. Se si crea una colonna non associata in modalità associata che contiene valori modificabili dall'utente, è necessario implementare la modalità virtuale per mantenere questi valori quando il controllo è ordinato in base a una colonna associata.  
  
## <a name="virtual"></a>Virtuale  
 Con la modalità virtuale è possibile implementare le proprie operazioni di gestione dei dati. Questa operazione è necessaria per mantenere i valori delle colonne non vincolate in modalità di associazione quando il controllo è ordinato in base alle colonne di associazione. L'uso principale della modalità virtuale, tuttavia, consiste nell'ottimizzare le prestazioni quando si interagisce con grandi quantità di dati.  
  
 Il controllo <xref:System.Windows.Forms.DataGridView> viene collegato a una cache gestita e il codice controlla quando viene eseguito il push e il pull delle righe di dati. Per ridurre il footprint di memoria, è necessario che le dimensioni della cache siano simili al numero di righe attualmente visualizzate. Quando l'utente scorre le nuove righe nella visualizzazione, il codice richiede nuovi dati dalla cache e, facoltativamente, Scarica i dati obsoleti dalla memoria.  
  
 Quando si implementa la modalità virtuale, sarà necessario tenere traccia del momento in cui è necessaria una nuova riga nel modello di dati e quando eseguire il rollback dell'aggiunta della nuova riga. L'implementazione esatta di questa funzionalità dipende dall'implementazione del modello di dati e dalla semantica delle transazioni del modello di dati. indica se l'ambito del commit è a livello di cella o di riga.  
  
 Per ulteriori informazioni sulla modalità virtuale, vedere la pagina relativa alla [modalità virtuale nel controllo DataGridView Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md). Per un esempio che illustra come usare gli eventi in modalità virtuale, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.VirtualMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridViewColumn.DataPropertyName%2A?displayProperty=nameWithType>
- [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Tipi di colonne nel controllo DataGridView di Windows Form](column-types-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Creazione di un controllo DataGridView di Windows Form non associato](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [Procedura: Associare dati al controllo DataGridView di Windows Form](how-to-bind-data-to-the-windows-forms-datagridview-control.md)
- [Modo virtuale nel controllo DataGridView di Windows Form](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Implementazione della modalità virtuale nel controllo DataGridView di Windows Form](implementing-virtual-mode-wf-datagridview-control.md)
