---
title: 'Procedura dettagliata: convalida dei dati nel controllo DataGridView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating data [Windows Forms], Windows Forms
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: a4f1d015-2969-430c-8ea2-b612d179c290
ms.openlocfilehash: 45753fb206ad58616c9a727bd81bd2458db6053e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740099"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Procedura dettagliata: convalida di dati nel controllo DataGridView Windows Form

Quando si visualizzano le funzionalità di immissione dati per gli utenti, è spesso necessario convalidare i dati immessi nel form. La classe <xref:System.Windows.Forms.DataGridView> fornisce un modo pratico per eseguire la convalida prima del commit dei dati nell'archivio dati. È possibile convalidare i dati gestendo l'evento <xref:System.Windows.Forms.DataGridView.CellValidating>, generato dall'<xref:System.Windows.Forms.DataGridView> quando la cella corrente viene modificata.

In questa procedura dettagliata vengono recuperate le righe dalla tabella `Customers` nel database di esempio Northwind e visualizzate in un controllo <xref:System.Windows.Forms.DataGridView>. Quando un utente modifica una cella nella colonna `CompanyName` e tenta di uscire dalla cella, il gestore dell'evento <xref:System.Windows.Forms.DataGridView.CellValidating> esaminerà la nuova stringa del nome della società per assicurarsi che non sia vuota. Se il nuovo valore è una stringa vuota, il <xref:System.Windows.Forms.DataGridView> impedisce al cursore dell'utente di uscire dalla cella fino a quando non viene immessa una stringa non vuota.

Per copiare il codice in questo argomento come singolo elenco, vedere [procedura: convalidare i dati nel controllo DataGridView Windows Forms](how-to-validate-data-in-the-windows-forms-datagridview-control.md).

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario:

- Accesso a un server in cui è presente il database di esempio Northwind SQL Server.

## <a name="creating-the-form"></a>Creazione del form

#### <a name="to-validate-data-entered-in-a-datagridview"></a>Per convalidare i dati immessi in un DataGridView

1. Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un controllo <xref:System.Windows.Forms.DataGridView> e un componente <xref:System.Windows.Forms.BindingSource>.

    Nell'esempio di codice seguente viene fornita l'inizializzazione di base e viene incluso un `Main` metodo.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. Implementare un metodo nella definizione di classe del modulo per la gestione dei dettagli della connessione al database.

    Questo esempio di codice usa un metodo di `GetData` che restituisce un oggetto <xref:System.Data.DataTable> popolato. Assicurarsi di impostare la variabile di `connectionString` su un valore appropriato per il database.

    > [!IMPORTANT]
    > L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'uso dell'autenticazione di Windows, nota anche come sicurezza integrata, è un modo più sicuro per controllare l'accesso a un database. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. Implementare un gestore per l'evento <xref:System.Windows.Forms.Form.Load> del form che Inizializza i <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.BindingSource> e imposta il data binding.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. Implementare i gestori per gli eventi <xref:System.Windows.Forms.DataGridView.CellValidating> e <xref:System.Windows.Forms.DataGridView.CellEndEdit> del controllo <xref:System.Windows.Forms.DataGridView>.

    Il gestore dell'evento <xref:System.Windows.Forms.DataGridView.CellValidating> è il punto in cui si determina se il valore di una cella nella colonna `CompanyName` è vuoto. Se la convalida del valore della cella non riesce, impostare la proprietà <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> della classe <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> su `true`. In questo modo il controllo <xref:System.Windows.Forms.DataGridView> impedisce al cursore di uscire dalla cella. Impostare la proprietà <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> sulla riga su una stringa esplicativa. Viene visualizzata un'icona di errore con una descrizione comando che contiene il testo dell'errore. Nel gestore dell'evento <xref:System.Windows.Forms.DataGridView.CellEndEdit> impostare la proprietà <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> della riga sulla stringa vuota. L'evento <xref:System.Windows.Forms.DataGridView.CellEndEdit> si verifica solo quando la cella esce dalla modalità di modifica, operazione che non può essere eseguita se la convalida ha esito negativo.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a>Verifica dell'applicazione

È ora possibile testare il form per assicurarsi che si comportano come previsto.

#### <a name="to-test-the-form"></a>Per testare il modulo

- Compilare l'applicazione ed eseguirla.

  Viene visualizzato un <xref:System.Windows.Forms.DataGridView> riempito con i dati della tabella `Customers`. Quando si fa doppio clic su una cella nella colonna `CompanyName`, è possibile modificare il valore. Se si eliminano tutti i caratteri e si preme il tasto TAB per uscire dalla cella, il <xref:System.Windows.Forms.DataGridView> impedisce l'uscita. Quando si digita una stringa non vuota nella cella, il controllo <xref:System.Windows.Forms.DataGridView> consente di uscire dalla cella.

## <a name="next-steps"></a>Passaggi successivi

Questa applicazione offre una conoscenza di base delle funzionalità del controllo <xref:System.Windows.Forms.DataGridView>. È possibile personalizzare l'aspetto e il comportamento del controllo <xref:System.Windows.Forms.DataGridView> in diversi modi:

- Modificare gli stili del bordo e dell'intestazione. Per altre informazioni, vedere [procedura: modificare gli stili dei bordi e della griglia nel controllo DataGridView Windows Forms](change-the-border-and-gridline-styles-in-the-datagrid.md).

- Abilitare o limitare l'input dell'utente per il controllo <xref:System.Windows.Forms.DataGridView>. Per altre informazioni, vedere [procedura: impedire l'aggiunta e l'eliminazione di righe nel controllo Windows Forms DataGridView](prevent-row-addition-and-deletion-datagridview.md)e [procedura: rendere le colonne di sola lettura nel controllo DataGridView Windows Forms](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).

- Controllare l'input dell'utente per gli errori correlati al database. Per ulteriori informazioni, vedere [procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).

- Gestire set di dati di grandi dimensioni usando la modalità virtuale. Per ulteriori informazioni, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Forms](implementing-virtual-mode-wf-datagridview-control.md).

- Personalizzare l'aspetto delle celle. Per altre informazioni, vedere [procedura: personalizzare l'aspetto delle celle nel controllo Windows Forms DataGridView](customize-the-appearance-of-cells-in-the-datagrid.md) e [procedura: impostare gli stili di carattere e colore nel controllo DataGridView Windows Forms](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Immissione di dati nel controllo DataGridView di Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedura: Convalidare dati nel controllo DataGridView di Windows Form](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Form](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
