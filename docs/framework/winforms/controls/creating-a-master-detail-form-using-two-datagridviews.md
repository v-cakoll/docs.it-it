---
title: 'Procedura dettagliata: Creazione di un Form Master-Details mediante due controlli DataGridView di Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
ms.openlocfilehash: a887dacfcb83b4b6ea4cb2690ab09b0d1b20b4fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772892"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Procedura dettagliata: Creazione di un modulo Master-Details usando due controlli DataGridView di Windows Forms
Uno degli scenari più comuni per l'uso di <xref:System.Windows.Forms.DataGridView> controllo è il *master/dettaglio* form, in cui viene visualizzata una relazione padre/figlio tra due tabelle di database. La selezione di righe nella tabella master fa sì che la tabella di dettagli da aggiornare con i dati figlio corrispondente.  
  
 Implementazione di un form master-Details è semplice se si utilizza l'interazione tra il <xref:System.Windows.Forms.DataGridView> controllo e il <xref:System.Windows.Forms.BindingSource> componente. In questa procedura dettagliata si compilerà il modulo utilizzando due <xref:System.Windows.Forms.DataGridView> e due controlli <xref:System.Windows.Forms.BindingSource> componenti. Nel modulo verrà visualizzate due tabelle correlate nel database di esempio Northwind di SQL Server: `Customers` e `Orders`. Al termine, si avrà un modulo che vengono visualizzati tutti i clienti del database nel master <xref:System.Windows.Forms.DataGridView> e tutti gli ordini per il cliente selezionato nei dettagli <xref:System.Windows.Forms.DataGridView>.  
  
 Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Creare un Form Master-Details mediante due controlli DataGridView di Windows Form](create-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
- Accesso a un server con il database di esempio Northwind di SQL Server.  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-create-a-masterdetail-form"></a>Per creare un form master-details  
  
1. Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene due <xref:System.Windows.Forms.DataGridView> e due controlli <xref:System.Windows.Forms.BindingSource> componenti. Il codice seguente fornisce l'inizializzazione di form di base e include un `Main` (metodo). Se si usa la finestra di progettazione di Visual Studio per creare il form, è possibile usare il finestra di progettazione codice generato anziché questo codice, ma assicurarsi di usare i nomi visualizzati nelle dichiarazioni di variabili di seguito.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2. Implementare un metodo nella definizione di classe del form per la gestione di dettagli della connessione al database. Questo esempio Usa una `GetData` metodo che consente di popolare un <xref:System.Data.DataSet> dell'oggetto, aggiunge un <xref:System.Data.DataRelation> oggetto per il set di dati e associazioni il <xref:System.Windows.Forms.BindingSource> componenti. Assicurarsi di impostare la variabile `connectionString` su un valore appropriato per il database.  
  
    > [!IMPORTANT]
    >  L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3. Implementare un gestore per il modulo <xref:System.Windows.Forms.Form.Load> evento che si associa il <xref:System.Windows.Forms.DataGridView> controlli al <xref:System.Windows.Forms.BindingSource> componenti e le chiamate di `GetData` (metodo). L'esempio seguente include il codice che ridimensiona <xref:System.Windows.Forms.DataGridView> colonne per rientrare i dati visualizzati.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.  
  
#### <a name="to-test-the-form"></a>Per testare il form  
  
- Compilare l'applicazione ed eseguirla.  
  
     Verranno visualizzate due <xref:System.Windows.Forms.DataGridView> controlli, uno sopra l'altro. In primo piano sono i clienti di Northwind `Customers` tabella e nella parte inferiore sono il `Orders` corrispondente al cliente selezionato. Quando si selezionano righe diverse nella parte superiore <xref:System.Windows.Forms.DataGridView>, il contenuto dell'oggetto inferiore <xref:System.Windows.Forms.DataGridView> modificare di conseguenza.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Questa applicazione fornisce una conoscenza di base di <xref:System.Windows.Forms.DataGridView> funzionalità del controllo. È possibile personalizzare l'aspetto e il comportamento del <xref:System.Windows.Forms.DataGridView> controllo in diversi modi:  
  
- Modificare gli stili del bordo e l'intestazione. Per altre informazioni, vedere [Procedura: Modificare il bordo e gli stili delle linee della griglia nella finestra di Windows Forms DataGridView Control](change-the-border-and-gridline-styles-in-the-datagrid.md).  
  
- Abilitare o limitare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per altre informazioni, vedere [Procedura: Impedire l'aggiunta di riga o eliminazione in di Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md), e [come: Rendere le colonne di sola lettura nella finestra di Windows Forms DataGridView Control](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md).  
  
- Convalidare l'input dell'utente per il <xref:System.Windows.Forms.DataGridView> controllo. Per altre informazioni, vedere [Procedura dettagliata: Convalida dei dati in di Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).  
  
- Gestire set di dati molto grandi usando la modalità virtuale. Per altre informazioni, vedere [Procedura dettagliata: Implementazione della modalità virtuale in Windows il controllo DataGridView form](implementing-virtual-mode-wf-datagridview-control.md).  
  
- Personalizzare l'aspetto delle celle. Per altre informazioni, vedere [Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView Windows Form](customize-the-appearance-of-cells-in-the-datagrid.md) e [come: Impostare stili di cella predefiniti per i Windows Form controllo DataGridView](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Creare un Form Master-Details mediante due controlli DataGridView di Windows Form](create-a-master-detail-form-using-two-datagridviews.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
