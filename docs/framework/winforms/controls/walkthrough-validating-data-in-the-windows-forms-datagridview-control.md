---
title: 'Procedura dettagliata: convalida di dati nel controllo DataGridView Windows Form'
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
ms.openlocfilehash: 8ad8caef5db13b1f917a6c27da523d3ded915d84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540963"
---
# <a name="walkthrough-validating-data-in-the-windows-forms-datagridview-control"></a>Procedura dettagliata: convalida di dati nel controllo DataGridView Windows Form
Quando si visualizza la funzionalità di immissione di dati agli utenti, è spesso necessario convalidare i dati immessi nel form. La <xref:System.Windows.Forms.DataGridView> classe fornisce un modo pratico per eseguire la convalida prima di dati vengono eseguito il commit nell'archivio dati. È possibile convalidare i dati mediante la gestione di <xref:System.Windows.Forms.DataGridView.CellValidating> evento, viene generato dal <xref:System.Windows.Forms.DataGridView> quando cambia la cella corrente.  
  
 In questa procedura dettagliata, si recupererà le righe di `Customers` tabella nel database di esempio Northwind e visualizzarli in un <xref:System.Windows.Forms.DataGridView> controllo. Quando un utente modifica una cella di `CompanyName` colonna e cerca di lasciare la cella, il <xref:System.Windows.Forms.DataGridView.CellValidating> gestore eventi esaminerà la nuova stringa del nome della società per assicurarsi che sia non vuoto; se il nuovo valore è una stringa vuota, il <xref:System.Windows.Forms.DataGridView> impedirà il cursore dell'utente di lasciare la cella fino a quando non viene inserita una stringa non vuota.  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: convalidare dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Accesso a un server con il database di esempio Northwind di SQL Server.  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-validate-data-entered-in-a-datagridview"></a>Per convalidare i dati immessi in un controllo DataGridView  
  
1.  Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un <xref:System.Windows.Forms.DataGridView> controllo e un <xref:System.Windows.Forms.BindingSource> componente.  
  
     Esempio di codice seguente fornisce l'inizializzazione di base e include un `Main` metodo.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewDataValidation#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#02)]  
  
2.  Implementare un metodo nella definizione di classe del form per gestire i dettagli della connessione al database.  
  
     Nell'esempio viene utilizzata una `GetData` metodo che restituisce un insieme <xref:System.Data.DataTable> oggetto. Accertarsi di impostare il `connectionString` variabile su un valore appropriato per il database.  
  
    > [!IMPORTANT]
    >  L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. Windows autenticazione, noto anche come sicurezza integrata, costituisce un modo più sicuro per controllare l'accesso a un database. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#30)]  
  
3.  Implementare un gestore per il modulo <xref:System.Windows.Forms.Form.Load> evento che inizializza il <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.BindingSource> e impostare l'associazione dati.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#10)]  
  
4.  Implementare i gestori per il <xref:System.Windows.Forms.DataGridView> del controllo <xref:System.Windows.Forms.DataGridView.CellValidating> e <xref:System.Windows.Forms.DataGridView.CellEndEdit> eventi.  
  
     Il <xref:System.Windows.Forms.DataGridView.CellValidating> gestore eventi è che consente di determinare se il valore di una cella di `CompanyName` colonna è vuota. Se il valore di cella non viene convalidato, impostare il <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> proprietà del <xref:System.Windows.Forms.DataGridViewCellValidatingEventArgs?displayProperty=nameWithType> classe `true`. In questo modo il <xref:System.Windows.Forms.DataGridView> controllo per impedire che il cursore di lasciare la cella. Impostare il <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> proprietà della riga su una stringa descrittiva. Verrà visualizzata un'icona di errore con una descrizione comando contenente il testo dell'errore. Nel <xref:System.Windows.Forms.DataGridView.CellEndEdit> gestore dell'evento, impostare il <xref:System.Windows.Forms.DataGridViewRow.ErrorText%2A> proprietà della riga su una stringa vuota. Il <xref:System.Windows.Forms.DataGridView.CellEndEdit> evento si verifica solo quando la cella esce dalla modalità di modifica, non è possibile eseguire in caso di convalida.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewDataValidation#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#20)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.  
  
#### <a name="to-test-the-form"></a>Per verificare il modulo  
  
-   Compilare l'applicazione ed eseguirla.  
  
     Verrà visualizzato un <xref:System.Windows.Forms.DataGridView> inseriti i dati di `Customers` tabella. Quando si fa doppio clic su una cella di `CompanyName` colonna, è possibile modificare il valore. Se si elimina tutti i caratteri e premere il tasto TAB per uscire dalla cella, il <xref:System.Windows.Forms.DataGridView> impedisce l'uscita. Quando si digita una stringa non vuota nella cella, il <xref:System.Windows.Forms.DataGridView> controllo consente di uscire dalla cella.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione fornisce una conoscenza di base di <xref:System.Windows.Forms.DataGridView> funzionalità del controllo. È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:  
  
-   Modificare gli stili del bordo e intestazione. Per ulteriori informazioni, vedere [procedura: modificare il bordo e gli stili delle linee della griglia nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Abilitare o limitare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per ulteriori informazioni, vedere [procedura: impedire l'aggiunta delle righe e eliminazione nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), e [come: rendere sola lettura di colonne nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Controllare l'input dell'utente per errori correlati al database. Per ulteriori informazioni, vedere [procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
-   Gestire grandi set di dati utilizzando la modalità virtuale. Per ulteriori informazioni, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizzare l'aspetto delle celle. Per ulteriori informazioni, vedere [procedura: personalizzare l'aspetto di celle nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) e [procedura: impostare tipo di carattere e stili di colore nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Immissione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Convalidare dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/how-to-validate-data-in-the-windows-forms-datagridview-control.md)  
 [Procedura dettagliata: Gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/handling-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md)
