---
title: 'Procedura dettagliata: Convalida dei dati nel controllo DataGridView di Windows Forms'
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
ms.openlocfilehash: 89569feb0cb741f56d09f4e58154b4eecb5a89d4
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046384"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Procedura dettagliata: Convalida dei dati nel controllo DataGridView di Windows Forms

Quando si visualizzano le funzionalità di immissione dati per gli utenti, è spesso necessario convalidare i dati immessi nel form. La <xref:System.Windows.Forms.DataGridView> classe fornisce un modo pratico per eseguire la convalida prima del commit dei dati nell'archivio dati. È possibile convalidare i dati <xref:System.Windows.Forms.DataGridView.CellValidating> gestendo l'evento, generato <xref:System.Windows.Forms.DataGridView> da quando la cella corrente viene modificata.

In questa procedura dettagliata vengono recuperate le righe dalla `Customers` tabella nel database di esempio Northwind e visualizzate in un <xref:System.Windows.Forms.DataGridView> controllo. Quando un utente modifica una cella nella `CompanyName` colonna e tenta di uscire dalla cella, il <xref:System.Windows.Forms.DataGridView.CellValidating> gestore eventi esamina la nuova stringa del nome della società per assicurarsi che non sia vuota. se il nuovo valore è una stringa vuota, il <xref:System.Windows.Forms.DataGridView> cursore dell'utente verrà impedito da. uscire dalla cella fino a quando non viene immessa una stringa non vuota.

Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Convalidare i dati nel controllo](how-to-validate-data-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario:

- Accesso a un server in cui è presente il database di esempio Northwind SQL Server.

## <a name="creating-the-form"></a>Creazione del form

#### <a name="to-validate-data-entered-in-a-datagridview"></a>Per convalidare i dati immessi in un DataGridView

1. Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un <xref:System.Windows.Forms.DataGridView> controllo e un <xref:System.Windows.Forms.BindingSource> componente.

    Nell'esempio di codice seguente viene fornita l'inizializzazione `Main` di base e viene incluso un metodo.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]

2. Implementare un metodo nella definizione di classe del modulo per la gestione dei dettagli della connessione al database.

    Questo esempio di codice usa `GetData` un metodo che restituisce un <xref:System.Data.DataTable> oggetto popolato. Assicurarsi di impostare la `connectionString` variabile su un valore appropriato per il database.

    > [!IMPORTANT]
    > L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'uso dell'autenticazione di Windows, nota anche come sicurezza integrata, è un modo più sicuro per controllare l'accesso a un database. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]

3. Implementare un gestore per l' <xref:System.Windows.Forms.Form.Load> evento del form che <xref:System.Windows.Forms.DataGridView> Inizializza e <xref:System.Windows.Forms.BindingSource> imposta il data binding.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]

4. Implementare i gestori per gli <xref:System.Windows.Forms.DataGridView> eventi <xref:System.Windows.Forms.DataGridView.CellValidating> e <xref:System.Windows.Forms.DataGridView.CellEndEdit> del controllo.

    Il <xref:System.Windows.Forms.DataGridView.CellValidating> gestore eventi è il punto `CompanyName` in cui si determina se il valore di una cella nella colonna è vuoto. Se la convalida del valore della cella non riesce <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> , impostare la <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> proprietà della `true`classe su. In questo modo <xref:System.Windows.Forms.DataGridView> , il controllo impedisce al cursore di uscire dalla cella. Impostare la <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> proprietà della riga su una stringa esplicativa. Viene visualizzata un'icona di errore con una descrizione comando che contiene il testo dell'errore. <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> Nel gestore <xref:System.Windows.Forms.DataGridView.CellEndEdit> eventi impostare la proprietà della riga sulla stringa vuota. L' <xref:System.Windows.Forms.DataGridView.CellEndEdit> evento si verifica solo quando la cella esce dalla modalità di modifica, operazione che non può essere eseguita se la convalida non riesce.

    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]

## <a name="testing-the-application"></a>Verifica dell'applicazione

È ora possibile testare il form per assicurarsi che si comportano come previsto.

#### <a name="to-test-the-form"></a>Per testare il modulo

- Compilare l'applicazione ed eseguirla.

  Viene visualizzato un oggetto <xref:System.Windows.Forms.DataGridView> compilato con i dati `Customers` della tabella. Quando si fa doppio clic su una cella nella `CompanyName` colonna, è possibile modificare il valore. Se si eliminano tutti i caratteri e si preme il tasto TAB per uscire dalla cella <xref:System.Windows.Forms.DataGridView> , il impedisce l'uscita. Quando si digita una stringa non vuota nella cella, il <xref:System.Windows.Forms.DataGridView> controllo consente di uscire dalla cella.

## <a name="next-steps"></a>Fasi successive

Questa applicazione offre una conoscenza di base delle <xref:System.Windows.Forms.DataGridView> funzionalità del controllo. È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:

- Modificare gli stili del bordo e dell'intestazione. Per altre informazioni, vedere [Procedura: Modificare gli stili dei bordi e della griglia nel controllo](change-the-border-and-gridline-styles-in-the-datagrid.md)DataGridView Windows Forms.

- Abilitare o limitare l'input dell'utente <xref:System.Windows.Forms.DataGridView> per il controllo. Per altre informazioni, vedere [Procedura: Impedire l'aggiunta e l'eliminazione di righe nel controllo](prevent-row-addition-and-deletion-datagridview.md)Windows Forms DataGridView [e procedura: Rendere le colonne di sola lettura nel controllo](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

- Controllare l'input dell'utente per gli errori correlati al database. Per altre informazioni, vedere [Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)nel controllo DataGridView Windows Forms.

- Gestire set di dati di grandi dimensioni usando la modalità virtuale. Per altre informazioni, vedere [Procedura dettagliata: Implementazione della modalità virtuale nel controllo](implementing-virtual-mode-wf-datagridview-control.md)DataGridView Windows Forms.

- Personalizzare l'aspetto delle celle. Per altre informazioni, vedere [Procedura: Personalizzare l'aspetto delle celle nel controllo](customize-the-appearance-of-cells-in-the-datagrid.md) DataGridView Windows Forms e [procedura: Impostare gli stili di carattere e colore nel controllo](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Immissione di dati nel controllo DataGridView di Windows Form](data-entry-in-the-windows-forms-datagridview-control.md)
- [Procedura: Convalidare i dati nel controllo DataGridView Windows Forms](how-to-validate-data-in-the-windows-forms-datagridview-control.md)
- [Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Forms](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
