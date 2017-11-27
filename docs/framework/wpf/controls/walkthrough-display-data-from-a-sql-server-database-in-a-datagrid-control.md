---
title: 'Procedura dettagliata: aggiunta di dati di un database di SQL Server in un controllo DataGrid'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGrid [WPF], displaying data from SQL Server
- controls [WPF], DataGrid
ms.assetid: 6810b048-0a23-4f86-bfa5-97f92b3cfab4
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c89ed9425920602f80a2407b7529b3eb215a2e3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-display-data-from-a-sql-server-database-in-a-datagrid-control"></a>Procedura dettagliata: aggiunta di dati di un database di SQL Server in un controllo DataGrid
In questa procedura dettagliata, si recuperano dati da un database di SQL Server e visualizzarli in un <xref:System.Windows.Controls.DataGrid> controllo. Utilizzare ADO.NET Entity Framework per creare le classi di entità che rappresentano i dati e utilizzano LINQ per scrivere una query che recupera i dati specificati da una classe di entità.  
  
## <a name="prerequisites"></a>Prerequisiti  
 Per completare la procedura dettagliata, è necessario disporre dei componenti seguenti:  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)].  
  
-   Accesso a un'istanza di SQL Server o SQL Server Express con il database di esempio AdventureWorks associato in esecuzione. È possibile scaricare il database AdventureWorks dal [GitHub](https://github.com/Microsoft/sql-server-samples/releases).  
  
### <a name="to-create-entity-classes"></a>Per creare classi di entità  
  
1.  Creare un nuovo progetto applicazione WPF in Visual Basic o c# e denominarlo `DataGridSQLExample`.  
  
2.  In Esplora soluzioni, fare clic sul progetto, scegliere **Aggiungi**, quindi selezionare **nuovo elemento**.  
  
     Verrà visualizzata la finestra di dialogo Aggiungi nuovo elemento.  
  
3.  Nel riquadro dei modelli installati, selezionare **dati** e nell'elenco dei modelli, selezionare **ADO.NET Entity Data Model**l.  
  
     ![Selezionare ADO.NET Entity Data Model](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step1.png "DataGrid_SQL_EF_Step1")  
  
4.  Nome del file `AdventureWorksModel.edmx` e quindi fare clic su **Aggiungi**.  
  
     Verrà visualizzata la procedura guidata Entity Data Model.  
  
5.  Nella schermata, Scegli contenuto Model selezionare **genera da database** e quindi fare clic su **Avanti**.  
  
     ![Selezionare l'opzione di database genera](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step2.png "DataGrid_SQL_EF_Step2")  
  
6.  Nella schermata di connessione dati, specificare la connessione al database AdventureWorksLT2008. Per ulteriori informazioni, vedere [dialogo scegliere la connessione dati](http://go.microsoft.com/fwlink/?LinkId=160190).  
  
     ![Fornire una connessione al database](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step3.png "DataGrid_SQL_EF_Step3")  
  
7.  Assicurarsi che il nome sia `AdventureWorksLT2008Entities` e che il **Salva entità di impostazioni di connessione in App. config come** casella di controllo è selezionata e quindi fare clic su **Avanti**.  
  
8.  Nella schermata Seleziona oggetti di Database, espandere il nodo tabelle e selezionare il **prodotto** e **ProductCategory** tabelle.  
  
     È possibile generare le classi di entità per tutte le tabelle. Tuttavia, in questo esempio è solo recuperare dati da queste due tabelle.  
  
     ![Selezionare Product e ProductCategory dalle tabelle](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step4.png "DataGrid_SQL_EF_Step4")  
  
9. Scegliere **Fine**.  
  
     Le entità Product e ProductCategory vengono visualizzate in Entity Designer.  
  
     ![I modelli di entità Product e ProductCategory](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step5.png "DataGrid_SQL_EF_Step5")  
  
### <a name="to-retrieve-and-present-the-data"></a>Per recuperare e presentare i dati  
  
1.  Aprire il file MainWindow. Xaml.  
  
2.  Impostare il <xref:System.Windows.FrameworkElement.Width%2A> proprietà il <xref:System.Windows.Window> a 450.  
  
3.  Nell'editor XAML, aggiungere le seguenti <xref:System.Windows.Controls.DataGrid> tag tra il `<Grid>` e `</Grid>` tag per aggiungere un <xref:System.Windows.Controls.DataGrid> denominato `dataGrid1`.  
  
     [!code-xaml[DataGrid_SQL_EF_Walkthrough#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#3)]  
  
     ![Finestra con DataGrid](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step6.png "DataGrid_SQL_EF_Step6")  
  
4.  Selezionare <xref:System.Windows.Window>.  
  
5.  Utilizzando la finestra proprietà o un editor XAML, creare un gestore eventi per il <xref:System.Windows.Window> denominato `Window_Loaded` per il <xref:System.Windows.FrameworkElement.Loaded> evento. Per ulteriori informazioni, vedere [procedura: creare un semplice gestore](http://msdn.microsoft.com/en-us/b1456e07-9dec-4354-99cf-18666b64f480).  
  
     Di seguito viene illustrato il codice XAML per MainWindow. Xaml.  
  
    > [!NOTE]
    >  Se si utilizza Visual Basic, nella prima riga di MainWindow. XAML, sostituire `x:Class="DataGridSQLExample.MainWindow"` con `x:Class="MainWindow"`.  
  
     [!code-xaml[DataGrid_SQL_EF_Walkthrough#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml#1)]  
  
6.  Aprire il file code-behind (VB o MainWindow.xaml.cs) per il <xref:System.Windows.Window>.  
  
7.  Aggiungere il codice seguente per recuperare solo i valori specifici da tabelle unite in join e impostare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> proprietà del <xref:System.Windows.Controls.DataGrid> ai risultati della query.  
  
     [!code-csharp[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/CS/MainWindow.xaml.cs#2)]
     [!code-vb[DataGrid_SQL_EF_Walkthrough#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataGrid_SQL_EF_Walkthrough/VB/MainWindow.xaml.vb#2)]  
  
8.  Eseguire l'esempio.  
  
     Verrà visualizzato un <xref:System.Windows.Controls.DataGrid> che visualizza i dati.  
  
     ![DataGrid con dati da database SQL](../../../../docs/framework/wpf/controls/media/datagrid-sql-ef-step7.png "DataGrid_SQL_EF_Step7")  
  
## <a name="next-steps"></a>Passaggi successivi  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.DataGrid>  
 [Come ricerca per categorie: Introduzione a Entity Framework nelle applicazioni WPF?](http://go.microsoft.com/fwlink/?LinkId=159868)
