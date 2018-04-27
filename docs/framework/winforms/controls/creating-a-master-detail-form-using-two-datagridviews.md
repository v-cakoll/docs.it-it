---
title: 'Procedura dettagliata: Creazione di un Form Master-Details mediante due controlli DataGridView di Windows Form'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], displaying on Windows Forms
- walkthroughs [Windows Forms], DataGridView control
ms.assetid: c5fa29e8-47f7-4691-829b-0e697a691f36
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e5c3dfc547fe775b38ad4c2e658755268f791502
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-creating-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a>Procedura dettagliata: creazione di un form Master-Details mediante due controlli DataGridView Windows Form
Uno degli scenari più comuni per l'utilizzo di <xref:System.Windows.Forms.DataGridView> controllo è il *master-Details* form, in cui viene visualizzata una relazione padre-figlio tra due tabelle di database. La selezione di righe nella tabella master, la tabella di dettagli per l'aggiornamento con i dati figlio corrispondente.  
  
 Implementazione di un form master-Details è semplice con l'interazione tra il <xref:System.Windows.Forms.DataGridView> controllo e <xref:System.Windows.Forms.BindingSource> componente. In questa procedura dettagliata, si compilerà il form utilizzando due <xref:System.Windows.Forms.DataGridView> e due controlli <xref:System.Windows.Forms.BindingSource> componenti. Nel form verranno visualizzate due tabelle correlate nel database di esempio Northwind di SQL Server: `Customers` e `Orders`. Al termine, si disporrà di un form che mostra tutti i clienti nel database master <xref:System.Windows.Forms.DataGridView> e tutti gli ordini per il cliente selezionato nei dettagli <xref:System.Windows.Forms.DataGridView>.  
  
 Per copiare il codice in questo argomento come elenco singolo, vedere [procedura: creare un Master-Details Form utilizzando due Windows Form controlli DataGridView](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md).  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare questa procedura dettagliata, è necessario:  
  
-   Accesso a un server con il database di esempio Northwind di SQL Server.  
  
## <a name="creating-the-form"></a>Creazione del form  
  
#### <a name="to-create-a-masterdetail-form"></a>Per creare un form master-details  
  
1.  Creare una classe che deriva da <xref:System.Windows.Forms.Form> e contiene due <xref:System.Windows.Forms.DataGridView> e due controlli <xref:System.Windows.Forms.BindingSource> componenti. Il codice seguente fornisce l'inizializzazione di form di base e include un `Main` metodo. Se si utilizza la finestra di progettazione di Visual Studio per creare il form, è possibile utilizzare il finestra di progettazione codice generato anziché il codice, ma assicurarsi di utilizzare i nomi visualizzati nelle dichiarazioni di variabili qui.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#01)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#01](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#01)]  
    [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#02)]
    [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#02](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#02)]  
  
2.  Implementare un metodo nella definizione di classe del form per la gestione dei dettagli della connessione al database. Questo esempio viene utilizzato un `GetData` metodo che consente di compilare un <xref:System.Data.DataSet> dell'oggetto, aggiunge un <xref:System.Data.DataRelation> oggetto per il set di dati e associa il <xref:System.Windows.Forms.BindingSource> componenti. Assicurarsi di impostare la variabile `connectionString` su un valore appropriato per il database.  
  
    > [!IMPORTANT]
    >  L'archiviazione delle informazioni riservate, ad esempio la password, nella stringa di connessione può avere implicazioni sulla sicurezza dell'applicazione. L'autenticazione di Windows, detta anche sicurezza integrata, consente di controllare l'accesso a un database in modo più sicuro. Per altre informazioni, vedere [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#20)]  
  
3.  Implementare un gestore per il modulo <xref:System.Windows.Forms.Form.Load> evento che associa il <xref:System.Windows.Forms.DataGridView> i controlli al <xref:System.Windows.Forms.BindingSource> componenti e le chiamate di `GetData` (metodo). L'esempio seguente include il codice che ridimensiona <xref:System.Windows.Forms.DataGridView> le colonne per adattarla i dati visualizzati.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#10)]  
  
## <a name="testing-the-application"></a>Verifica dell'applicazione  
 È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.  
  
#### <a name="to-test-the-form"></a>Per verificare il modulo  
  
-   Compilare l'applicazione ed eseguirla.  
  
     Verranno visualizzate due <xref:System.Windows.Forms.DataGridView> controlli, uno sopra l'altro. In primo piano sono i clienti di Northwind `Customers` tabella e nella parte inferiore sono il `Orders` corrispondente al cliente selezionato. Quando si selezionano righe diverse in alto a <xref:System.Windows.Forms.DataGridView>, il contenuto dell'oggetto inferiore <xref:System.Windows.Forms.DataGridView> modificare di conseguenza.  
  
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
 [Visualizzazione di dati nel controllo DataGridView di Windows Form](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Procedura: Creare un form Master-Details con due controlli DataGridView di Windows Form](../../../../docs/framework/winforms/controls/create-a-master-detail-form-using-two-datagridviews.md)  
 [Protezione delle informazioni di connessione](../../../../docs/framework/data/adonet/protecting-connection-information.md)
