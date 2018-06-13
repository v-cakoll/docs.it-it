---
title: "Procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form"
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
ms.openlocfilehash: 92525d1818160f5645b95948910547c7d1541897
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529234"
---
# <a name="walkthrough-handling-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a>Procedura dettagliata: gestione degli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form
Gestione degli errori dall'archivio dati sottostante è una funzionalità necessaria per un'applicazione di immissione di dati. Windows Form <xref:System.Windows.Forms.DataGridView> controllo semplifica questa attività esponendo il <xref:System.Windows.Forms.DataGridView.DataError> evento, viene generato quando l'archivio dati rileva una violazione del vincolo o una regola business.  
  
 In questa procedura dettagliata, si recupererà le righe di `Customers` tabella nel database di esempio Northwind e visualizzarli in un <xref:System.Windows.Forms.DataGridView> controllo. Quando un duplicato `CustomerID` viene rilevato in una nuova riga o una riga esistente modificata, il <xref:System.Windows.Forms.DataGridView.DataError> si verifica l'evento, che verrà gestito visualizzando un <xref:System.Windows.Forms.MessageBox> che descrive l'eccezione.  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Accesso a un server con il database di esempio Northwind di SQL Server.  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-handle-data-entry-errors-in-the-datagridview-control"></a>Per gestire gli errori di immissione di dati nel controllo DataGridView  
  
1.  Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene un <xref:System.Windows.Forms.DataGridView> controllo e un <xref:System.Windows.Forms.BindingSource> componente.  
  
     Esempio di codice seguente fornisce l'inizializzazione di base e include un `Main` metodo.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridView.DataError#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#02)]  
  
2.  Implementare un metodo nella definizione di classe del form per gestire i dettagli della connessione al database.  
  
     Nell'esempio viene utilizzata una `GetData` metodo che restituisce un insieme <xref:System.Data.DataTable> oggetto. Accertarsi di impostare il `connectionString` variabile su un valore appropriato per il database.  
  
    > [!IMPORTANT]
    >  L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#30)]  
  
3.  Implementare un gestore per il modulo <xref:System.Windows.Forms.Form.Load> evento che inizializza il <xref:System.Windows.Forms.DataGridView> e <xref:System.Windows.Forms.BindingSource> e impostare l'associazione dati.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#10)]  
  
4.  Gestire il <xref:System.Windows.Forms.DataGridView.DataError> evento il <xref:System.Windows.Forms.DataGridView>.  
  
     Se il contesto per l'errore è un'operazione di commit, visualizzare l'errore in un <xref:System.Windows.Forms.MessageBox>.  
  
     [!code-csharp[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridView.DataError#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#20)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.  
  
#### <a name="to-test-the-form"></a>Per verificare il modulo  
  
-   Premere F5 per eseguire l'applicazione.  
  
     Verrà visualizzato un <xref:System.Windows.Forms.DataGridView> controllo riempito di dati della tabella Customers. Se si immette un valore duplicato per `CustomerID` e il commit della modifica, il valore della cella verrà ripristinato automaticamente e verrà visualizzato un <xref:System.Windows.Forms.MessageBox> che viene visualizzato l'errore di immissione dati.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione fornisce una conoscenza di base di <xref:System.Windows.Forms.DataGridView> funzionalità del controllo. È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:  
  
-   Modificare gli stili del bordo e intestazione. Per ulteriori informazioni, vedere [procedura: modificare il bordo e gli stili delle linee della griglia nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
-   Abilitare o limitare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per ulteriori informazioni, vedere [procedura: impedire l'aggiunta delle righe e eliminazione nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md), e [come: rendere sola lettura di colonne nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
-   Convalidare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per ulteriori informazioni, vedere [procedura dettagliata: convalida di dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
-   Gestire grandi set di dati utilizzando la modalità virtuale. Per ulteriori informazioni, vedere [procedura dettagliata: implementazione della modalità virtuale nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/implementing-virtual-mode-wf-datagridview-control.md).  
  
-   Personalizzare l'aspetto delle celle. Per ulteriori informazioni, vedere [procedura: personalizzare l'aspetto di celle nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md) e [procedura: impostare stili di cella predefiniti per il controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [Immissione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Gestire gli errori che si verificano durante l'immissione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/handle-errors-that-occur-during-data-entry-in-the-datagrid.md)  
 [Procedura dettagliata: convalida di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)  
 [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md)
