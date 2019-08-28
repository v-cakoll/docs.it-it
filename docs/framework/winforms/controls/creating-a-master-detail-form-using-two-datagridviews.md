---
title: 'Procedura dettagliata: Creazione di un form Master-Details con due controlli DataGridView Windows Forms'
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
ms.openlocfilehash: 4212c7223aca6a5e7de3189d5f6b2757453cc438
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046087"
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Procedura dettagliata: Creazione di un modulo Master-Details usando due controlli DataGridView di Windows Forms

Uno degli scenari più comuni per l'utilizzo del <xref:System.Windows.Forms.DataGridView> controllo è costituito dal formato *Master/* Details, in cui viene visualizzata una relazione padre/figlio tra due tabelle di database. La selezione di righe nella tabella master comporta l'aggiornamento della tabella dei dettagli con i dati figlio corrispondenti.

L'implementazione di un form Master-Details semplifica l'utilizzo <xref:System.Windows.Forms.DataGridView> dell'interazione tra <xref:System.Windows.Forms.BindingSource> il controllo e il componente. In questa procedura dettagliata verrà compilato il form utilizzando due <xref:System.Windows.Forms.DataGridView> controlli e due <xref:System.Windows.Forms.BindingSource> componenti. Nel modulo vengono visualizzate due tabelle correlate nel database di esempio Northwind SQL Server: `Customers` e `Orders`. Al termine, sarà presente un modulo che Mostra tutti i clienti del database nel database master <xref:System.Windows.Forms.DataGridView> e tutti gli ordini per il cliente selezionato nei dettagli. <xref:System.Windows.Forms.DataGridView>

Per copiare il codice in questo argomento come singolo listato, vedere [Procedura: Creare un form Master-Details con due controlli](create-a-master-detail-form-using-two-datagridviews.md)DataGridView Windows Forms.

## <a name="prerequisites"></a>Prerequisiti

Per completare questa procedura dettagliata, è necessario:

- Accesso a un server in cui è presente il database di esempio Northwind SQL Server.

## <a name="creating-the-form"></a>Creazione del modulo

#### <a name="to-create-a-masterdetail-form"></a>Per creare un form Master-Details

1. Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene due <xref:System.Windows.Forms.DataGridView> controlli e due <xref:System.Windows.Forms.BindingSource> componenti. Il codice seguente fornisce l'inizializzazione dei form di `Main` base e include un metodo. Se si usa la finestra di progettazione di Visual Studio per creare il form, è possibile usare il codice generato dalla finestra di progettazione anziché questo codice, ma assicurarsi di usare i nomi visualizzati nelle dichiarazioni di variabile qui.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]

2. Implementare un metodo nella definizione di classe del form per gestire i dettagli della connessione al database. In questo esempio viene `GetData` utilizzato un metodo che popola <xref:System.Data.DataSet> un oggetto, aggiunge <xref:System.Data.DataRelation> un oggetto al set di dati e associa i <xref:System.Windows.Forms.BindingSource> componenti. Assicurarsi di impostare la variabile `connectionString` su un valore appropriato per il database.

    > [!IMPORTANT]
    > L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md).

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]

3. Implementare <xref:System.Windows.Forms.Form.Load> un gestore per l'evento del form che associa i <xref:System.Windows.Forms.DataGridView> controlli ai <xref:System.Windows.Forms.BindingSource> componenti e chiama il `GetData` metodo. Nell'esempio seguente viene incluso il codice che ridimensiona <xref:System.Windows.Forms.DataGridView> le colonne per adattarle ai dati visualizzati.

    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]

## <a name="testing-the-application"></a>Verifica dell'applicazione

È ora possibile testare il form per assicurarsi che si comportano come previsto.

#### <a name="to-test-the-form"></a>Per testare il modulo

- Compilare l'applicazione ed eseguirla.

  Vengono visualizzati due <xref:System.Windows.Forms.DataGridView> controlli, uno sopra l'altro. I clienti della tabella Northwind `Customers` sono in primo piano e `Orders` sono nella parte inferiore corrispondente al cliente selezionato. Quando si selezionano righe diverse nella parte <xref:System.Windows.Forms.DataGridView>superiore, il contenuto della modifica <xref:System.Windows.Forms.DataGridView> inferiore di conseguenza.

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
- [Visualizzazione di dati nel controllo DataGridView di Windows Form](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Procedura: Creare un form Master-Details con due controlli DataGridView Windows Forms](create-a-master-detail-form-using-two-datagridviews.md)
- [Protezione delle informazioni di connessione](../../data/adonet/protecting-connection-information.md)
