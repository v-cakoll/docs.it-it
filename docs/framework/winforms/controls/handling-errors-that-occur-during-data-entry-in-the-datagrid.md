---
title: "Procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView"
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
ms.openlocfilehash: 77a4dcd9cf069ed8bbee6c49aa41db619c8e12ff
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738731"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form

La gestione degli errori dall'archivio dati sottostante è una funzionalità obbligatoria per un'applicazione di immissione dati. Il controllo Windows Forms <xref:System.Windows.Forms.DataGridView> semplifica questa operazione esponendo l'evento <xref:System.Windows.Forms.DataGridView.DataError>, che viene generato quando l'archivio dati rileva una violazione del vincolo o una regola business interruppe.

In questa procedura dettagliata vengono recuperate le righe dalla tabella `Customers` nel database di esempio Northwind e visualizzate in un controllo <xref:System.Windows.Forms.DataGridView>. Quando viene rilevato un valore `CustomerID` duplicato in una nuova riga o in una riga esistente modificata, si verificherà l'evento <xref:System.Windows.Forms.DataGridView.DataError>, che verrà gestito visualizzando un <xref:System.Windows.Forms.MessageBox> che descrive l'eccezione.

Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Forms](handle-errors-that-occur-during-data-entry-in-the-datagrid.md).

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario:

- Accesso a un server in cui è presente il database di esempio Northwind SQL Server.

## <a name="creating-the-form"></a>Creazione del form

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Per gestire gli errori di immissione dei dati nel controllo DataGridView

1. Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un controllo <xref:System.Windows.Forms.DataGridView> e un componente <xref:System.Windows.Forms.BindingSource>.

    Nell'esempio di codice seguente viene fornita l'inizializzazione di base e viene incluso un `Main` metodo.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. Implementare un metodo nella definizione di classe del modulo per la gestione dei dettagli della connessione al database.

    Questo esempio di codice usa un metodo di `GetData` che restituisce un oggetto <xref:System.Data.DataTable> popolato. Assicurarsi di impostare la variabile di `connectionString` su un valore appropriato per il database.

    > [!IMPORTANT]
    > L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. Implementare un gestore per l'evento <xref:System.Windows.Forms.Form.Load> del form che Inizializza i <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.BindingSource> e imposta il data binding.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. Gestire l'evento <xref:System.Windows.Forms.DataGridView.DataError> nel <xref:System.Windows.Forms.DataGridView>.

    Se il contesto per l'errore è un'operazione di commit, visualizzare l'errore in un <xref:System.Windows.Forms.MessageBox>.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a>Test dell'applicazione

È ora possibile testare il form per assicurarsi che si comportano come previsto.

#### <a name="to-test-the-form"></a>Per testare il modulo

- Premere F5 per eseguire l'applicazione.

  Viene visualizzato un controllo <xref:System.Windows.Forms.DataGridView> riempito con i dati della tabella Customers. Se si immette un valore duplicato per `CustomerID` e si esegue il commit della modifica, il valore della cella verrà ripristinato automaticamente e verrà visualizzato un <xref:System.Windows.Forms.MessageBox> in cui viene visualizzato l'errore di immissione dati.

## <a name="next-steps"></a>Passaggi successivi

Questa applicazione offre una conoscenza di base delle funzionalità del controllo <xref:System.Windows.Forms.DataGridView>. È possibile personalizzare l'aspetto e il comportamento del controllo <xref:System.Windows.Forms.DataGridView> in diversi modi:

- Modificare gli stili del bordo e dell'intestazione. Per altre informazioni, vedere [procedura: modificare gli stili dei bordi e della griglia nel controllo DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).

- Abilitare o limitare l'input dell'utente per il controllo <xref:System.Windows.Forms.DataGridView>. Per altre informazioni, vedere [procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md)e [procedura: rendere le colonne di sola lettura nel controllo DataGridView Windows Forms](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).

- Convalidare l'input dell'utente per il controllo <xref:System.Windows.Forms.DataGridView>. Per ulteriori informazioni, vedere [procedura dettagliata: convalida dei dati nel controllo DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).

- Gestire set di dati di grandi dimensioni usando la modalità virtuale. Per ulteriori informazioni, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).

- Personalizzare l'aspetto delle celle. Per altre informazioni, vedere [procedura: personalizzare l'aspetto delle celle nel controllo Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md) e [procedura: impostare stili di cella predefiniti per il controllo DataGridView di Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Immissione di dati nel controllo DataGridView di Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedura: Gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Form](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
