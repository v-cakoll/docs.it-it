---
title: "Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Forms"
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
ms.openlocfilehash: cee6fe3b049378fa7bbe2585a3607049eaf231bc
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046082"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Forms

La gestione degli errori dall'archivio dati sottostante è una funzionalità obbligatoria per un'applicazione di immissione dati. Il controllo <xref:System.Windows.Forms.DataGridView> Windows Forms semplifica questa operazione esponendo l' <xref:System.Windows.Forms.DataGridView.DataError> evento, che viene generato quando l'archivio dati rileva una violazione del vincolo o una regola business interruppe.

In questa procedura dettagliata vengono recuperate le righe dalla `Customers` tabella nel database di esempio Northwind e visualizzate in un <xref:System.Windows.Forms.DataGridView> controllo. Quando viene rilevato `CustomerID` un valore duplicato in una nuova riga o in una riga esistente modificata <xref:System.Windows.Forms.DataGridView.DataError> , l'evento si verificherà, che verrà gestito visualizzando <xref:System.Windows.Forms.MessageBox> un oggetto che descrive l'eccezione.

Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Gestire gli errori che si verificano durante l'immissione di dati](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)nel controllo DataGridView Windows Forms.

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario:

- Accesso a un server in cui è presente il database di esempio Northwind SQL Server.

## <a name="creating-the-form"></a>Creazione del form

#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Per gestire gli errori di immissione dei dati nel controllo DataGridView

1. Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un <xref:System.Windows.Forms.DataGridView> controllo e un <xref:System.Windows.Forms.BindingSource> componente.

    Nell'esempio di codice seguente viene fornita l'inizializzazione `Main` di base e viene incluso un metodo.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]

2. Implementare un metodo nella definizione di classe del modulo per la gestione dei dettagli della connessione al database.

    Questo esempio di codice usa `GetData` un metodo che restituisce un <xref:System.Data.DataTable> oggetto popolato. Assicurarsi di impostare la `connectionString` variabile su un valore appropriato per il database.

    > [!IMPORTANT]
    > L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]

3. Implementare un gestore per l' <xref:System.Windows.Forms.Form.Load> evento del form che <xref:System.Windows.Forms.DataGridView> Inizializza e <xref:System.Windows.Forms.BindingSource> imposta il data binding.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]

4. Gestire l' <xref:System.Windows.Forms.DataGridView.DataError> evento <xref:System.Windows.Forms.DataGridView>su.

    Se il contesto per l'errore è un'operazione di commit, visualizzare l'errore in <xref:System.Windows.Forms.MessageBox>un oggetto.

    [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]

## <a name="testing-the-application"></a>Verifica dell'applicazione

È ora possibile testare il form per assicurarsi che si comportano come previsto.

#### <a name="to-test-the-form"></a>Per testare il modulo

- Premere F5 per eseguire l'applicazione.

  Viene visualizzato un <xref:System.Windows.Forms.DataGridView> controllo compilato con i dati della tabella Customers. Se si immette un valore duplicato `CustomerID` per e si esegue il commit della modifica, il valore della cella verrà ripristinato <xref:System.Windows.Forms.MessageBox> automaticamente e verrà visualizzato un messaggio in cui viene visualizzato l'errore di immissione dati.

## <a name="next-steps"></a>Fasi successive

Questa applicazione offre una conoscenza di base delle <xref:System.Windows.Forms.DataGridView> funzionalità del controllo. È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:

- Modificare gli stili del bordo e dell'intestazione. Per altre informazioni, vedere [Procedura: Modificare gli stili dei bordi e della griglia nel controllo](change-the-border-and-gridline-styles-in-the-datagrid.md)DataGridView Windows Forms.

- Abilitare o limitare l'input dell'utente <xref:System.Windows.Forms.DataGridView> per il controllo. Per altre informazioni, vedere [Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo](prevent-row-addition-and-deletion-datagridview.md)Windows Forms DataGridView [e procedura: Rendere le colonne di sola lettura nel controllo](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

- Convalidare l'input <xref:System.Windows.Forms.DataGridView> dell'utente per il controllo. Per altre informazioni, vedere [Procedura dettagliata: Convalida dei dati nel controllo](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

- Gestire set di dati di grandi dimensioni usando la modalità virtuale. Per altre informazioni, vedere [Procedura dettagliata: Implementazione della modalità virtuale nel controllo](implementing-virtual-mode-wf-datagridview-control.md)DataGridView Windows Forms.

- Personalizzare l'aspetto delle celle. Per altre informazioni, vedere [Procedura: Personalizzare l'aspetto delle celle nel controllo](customize-the-appearance-of-cells-in-the-datagrid.md) DataGridView Windows Forms e [procedura: Impostare gli stili di cella predefiniti per il controllo](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Immissione di dati nel controllo DataGridView di Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedura: Gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Forms](handle-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Procedura dettagliata: Convalida dei dati nel controllo DataGridView Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
