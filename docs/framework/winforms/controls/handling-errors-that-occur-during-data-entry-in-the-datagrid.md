---
title: "Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: 30a68b85-d3af-4946-83c1-1e2d010d0511
ms.openlocfilehash: a8eb4584060924684eacc99d46b88408451f1c82
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708236"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form
Gestione degli errori dall'archivio dati sottostante è una funzionalità necessaria per un'applicazione di immissione dati. I moduli di Windows <xref:System.Windows.Forms.DataGridView> controllo semplifica questa attività tramite l'esposizione di <xref:System.Windows.Forms.DataGridView.DataError> evento, che viene generato quando l'archivio dati rileva una violazione del vincolo o una regola business.  
  
 In questa procedura dettagliata, si recupererà le righe di `Customers` tabella nel database di esempio Northwind e visualizzarli in un <xref:System.Windows.Forms.DataGridView> controllo. Quando un duplicato `CustomerID` viene rilevato in una nuova riga o una riga esistente modificata, il <xref:System.Windows.Forms.DataGridView.DataError> evento verrà generato, che verrà gestito visualizzando un <xref:System.Windows.Forms.MessageBox> che descrive l'eccezione.  
  
 Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Gestire gli errori che si verificano durante l'immissione di dati nella finestra di Windows Forms DataGridView Control](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Accesso a un server con il database di esempio Northwind di SQL Server.  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Per gestire gli errori di immissione di dati nel controllo DataGridView  
  
1.  Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene una <xref:System.Windows.Forms.DataGridView> controllo e un <xref:System.Windows.Forms.BindingSource> componente.  
  
     Esempio di codice seguente fornisce l'inizializzazione di base e include un `Main` (metodo).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  Implementare un metodo nella definizione di classe del form per gestire i dettagli della connessione al database.  
  
     Questo esempio di codice Usa un `GetData` metodo che restituisce un popolato <xref:System.Data.DataTable> oggetto. Assicurarsi di impostare il `connectionString` variabile su un valore appropriato per il database.  
  
    > [!IMPORTANT]
    >  L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  Implementare un gestore per il modulo <xref:System.Windows.Forms.Form.Load> evento che inizializza il <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.BindingSource> e configura il data binding.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  Gestire le <xref:System.Windows.Forms.DataGridView.DataError> evento sul <xref:System.Windows.Forms.DataGridView>.  
  
     Se il contesto dell'errore è un'operazione di commit, visualizzare l'errore in un <xref:System.Windows.Forms.MessageBox>.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.  
  
#### <a name="to-test-the-form"></a>Per testare il form  
  
-   Premere F5 per eseguire l'applicazione.  
  
     Verrà visualizzato un <xref:System.Windows.Forms.DataGridView> controllo occupata dai dati della tabella Customers. Se si immette un valore duplicato per `CustomerID` e il commit della modifica, il valore della cella verrà ripristinato automaticamente e verrà visualizzato un <xref:System.Windows.Forms.MessageBox> che viene visualizzato l'errore di immissione dati.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione fornisce una conoscenza di base di <xref:System.Windows.Forms.DataGridView> funzionalità del controllo. È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:  
  
-   Modificare gli stili del bordo e l'intestazione. Per altre informazioni, vedere [Procedura: Modificare il bordo e gli stili delle linee della griglia nella finestra di Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Abilitare o limitare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per altre informazioni, vedere [Procedura: Impedire l'aggiunta di riga o eliminazione in di Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), e [come: Rendere le colonne di sola lettura nella finestra di Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Convalidare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per altre informazioni, vedere [Procedura dettagliata: Convalida dei dati in di Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Gestire set di dati molto grandi usando la modalità virtuale. Per altre informazioni, vedere [Procedura dettagliata: Implementazione della modalità virtuale in Windows il controllo DataGridView form](implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizzare l'aspetto delle celle. Per altre informazioni, vedere [Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView Windows Form](customize-the-appearance-of-cells-in-the-datagrid.md) e [come: Impostare stili di cella predefiniti per i Windows Form controllo DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Immissione di dati nel controllo DataGridView di Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedura: Gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Procedura dettagliata: La convalida dei dati nel controllo DataGridView Windows Form](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
