---
title: 'Procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data [Windows Forms], managing large data sets
- DataGridView control [Windows Forms], virtual mode
- virtual mode [Windows Forms], walkthroughs
- DataGridView control [Windows Forms], large data sets
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 74eb5276-5ab8-4ce0-8005-dae751d85f7c
ms.openlocfilehash: 52e93ebe0b2903fdf2fe97f4ce812331e740f8b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-implementing-virtual-mode-in-the-windows-forms-datagridview-control"></a>Procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Form
Quando si desidera visualizzare grandi quantità di dati tabulari in un <xref:System.Windows.Forms.DataGridView> (controllo), è possibile impostare il <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> proprietà `true` e gestire in modo esplicito l'interazione del controllo con il relativo archivio dati. Ciò consente di ottimizzare le prestazioni del controllo in questa situazione.  
  
 Il <xref:System.Windows.Forms.DataGridView> controllo fornisce diversi eventi che è possibile gestire per interagire con un archivio dati personalizzato. In questa procedura dettagliata è illustrato il processo di implementazione di questi gestori eventi. L'esempio di codice in questo argomento utilizza un'origine dati molto semplice a scopo illustrativo. In un ambiente di produzione, viene in genere verrà caricato solo le righe necessarie per visualizzare in una cache e gestire <xref:System.Windows.Forms.DataGridView> gli eventi di interagire con e aggiornare la cache. Per altre informazioni, vedere [implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: implementare la modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md).  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-implement-virtual-mode"></a>Per implementare la modalità virtuale  
  
1.  Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un <xref:System.Windows.Forms.DataGridView> controllo.  
  
     Il codice seguente contiene l'inizializzazione di base. Dichiara alcune variabili da utilizzare nei passaggi successivi, si fornisce un `Main` (metodo) e fornisce un layout in formato semplice nel costruttore della classe.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#001)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#001)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#001](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#001)]  
    [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#002)]
    [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#002)]
    [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#002](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#002)]  
  
2.  Implementare un gestore per il modulo <xref:System.Windows.Forms.Form.Load> evento che inizializza il <xref:System.Windows.Forms.DataGridView> controllo e popola l'archivio dati con valori di esempio.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#110)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#110)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#110)]  
  
3.  Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.CellValueNeeded> evento che recupera il valore di cella dall'archivio dati o `Customer` oggetto attualmente in modalità di modifica.  
  
     Questo evento si verifica ogni volta che il <xref:System.Windows.Forms.DataGridView> controllo necessario disegnare una cella.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#120)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#120)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#120](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#120)]  
  
4.  Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.CellValuePushed> evento che archivia un valore di cella modificata la `Customer` oggetto che rappresenta la riga modificata. Questo evento si verifica ogni volta che l'utente esegue il commit di una modifica del valore della cella.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#130)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#130](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#130)]  
  
5.  Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.NewRowNeeded> evento che crea un nuovo `Customer` oggetto che rappresenta una riga appena creata.  
  
     Questo evento si verifica ogni volta che l'utente immette la riga per nuovi record.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#140)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#140)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#140)]  
  
6.  Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.RowValidated> evento che salva righe nuove o modificate per l'archivio dati.  
  
     Questo evento si verifica ogni volta che l'utente modifica la riga corrente.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#150)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#150)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#150](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#150)]  
  
7.  Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> evento che indica se il <xref:System.Windows.Forms.DataGridView.CancelRowEdit> evento si verifica quando l'utente segnala l'annullamento della riga premendo ESC due volte nella modalità di modifica o di una volta di fuori di modalità di modifica.  
  
     Per impostazione predefinita, <xref:System.Windows.Forms.DataGridView.CancelRowEdit> viene generato al momento dell'annullamento della riga, quando tutte le celle nella riga corrente sono state modificate, a meno che il <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> è impostata su `true` nel <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> gestore dell'evento. Questo evento è utile quando l'ambito di commit è determinato in fase di esecuzione.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#160)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#160)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#160](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#160)]  
  
8.  Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.CancelRowEdit> evento che rimuove i valori del `Customer` oggetto che rappresenta la riga corrente.  
  
     Questo evento si verifica quando l'utente segnala l'annullamento della riga premendo ESC due volte nella modalità di modifica o di una volta di fuori di modalità di modifica. Questo evento si verifica se non è stata modificata alcuna cella nella riga corrente o se il valore della <xref:System.Windows.Forms.QuestionEventArgs.Response%2A?displayProperty=nameWithType> è impostata su `false` in un <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded> gestore dell'evento.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#170)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#170)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#170](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#170)]  
  
9. Implementare un gestore per il <xref:System.Windows.Forms.DataGridView.UserDeletingRow> evento che elimina un oggetto esistente `Customer` oggetto dall'archivio dati o elimina un non salvate `Customer` oggetto che rappresenta una riga appena creata.  
  
     Questo evento si verifica ogni volta che l'utente elimina una riga facendo clic su un'intestazione di riga e premere il tasto CANC.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#180)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#180)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#180](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#180)]  
  
10. Implementare una semplice `Customers` classe per rappresentare gli elementi di dati utilizzati in questo esempio di codice.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CPP/virtualmode.cpp#200)]
     [!code-csharp[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/CS/virtualmode.cs#200)]
     [!code-vb[System.Windows.Forms.DataGridView.VirtualMode#200](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.VirtualMode/VB/virtualmode.vb#200)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.  
  
#### <a name="to-test-the-form"></a>Per verificare il modulo  
  
-   Compilare l'applicazione ed eseguirla.  
  
     Verrà visualizzato un <xref:System.Windows.Forms.DataGridView> controllo popolato con tre record cliente. È possibile modificare i valori di più celle in una riga e premere ESC due volte nella modalità di modifica e una volta di fuori di tale modalità per ripristinare l'intera riga per i valori originali. Quando si modifica, aggiungere o eliminare righe nel controllo `Customer` modificati, aggiunti o eliminati anche gli oggetti nell'archivio dati.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione fornisce una conoscenza di base degli eventi per implementare la modalità virtuale in cui è necessario gestire il <xref:System.Windows.Forms.DataGridView> controllo. È possibile migliorare l'applicazione di base in diversi modi:  
  
-   Implementare un archivio dati che memorizza nella cache i valori da un database esterno. La cache deve recuperare e rimuovere i valori in base alle esigenze in modo che contenga solo ciò che è necessario per la visualizzazione durante l'utilizzo di una piccola quantità di memoria nel computer client.  
  
-   Ottimizzare le prestazioni dell'archivio dati in base alle esigenze. È ad esempio compensare le connessioni di rete lenta rispetto a limiti di memoria dei computer client utilizzando una dimensione della cache maggiore e riducendo il numero di query di database.  
  
 Per ulteriori informazioni sulla memorizzazione nella cache i valori da un database esterno, vedere [procedura: implementare la modalità virtuale con caricamento dati JIT nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/virtual-mode-with-just-in-time-data-loading-in-the-datagrid.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>  
 <xref:System.Windows.Forms.DataGridView.CellValueNeeded>  
 <xref:System.Windows.Forms.DataGridView.CellValuePushed>  
 <xref:System.Windows.Forms.DataGridView.NewRowNeeded>  
 <xref:System.Windows.Forms.DataGridView.RowValidated>  
 <xref:System.Windows.Forms.DataGridView.RowDirtyStateNeeded>  
 <xref:System.Windows.Forms.DataGridView.CancelRowEdit>  
 <xref:System.Windows.Forms.DataGridView.UserDeletingRow>  
 [Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Procedure consigliate per ridimensionare il controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)  
 [Implementazione del modo virtuale con caricamento dati JIT nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-jit-data-loading-in-the-datagrid.md)  
 [Procedura: Implementare il modo virtuale nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)
