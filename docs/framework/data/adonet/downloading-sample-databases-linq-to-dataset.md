---
title: Download di database di esempio (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: f2488b0e1bfc578679a2a2802c332439f374a341
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>Download di database di esempio (LINQ to DataSet)
Gli esempi e procedure dettagliate di [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentazione utilizzano il database di esempio AdventureWorks. È possibile scaricare gratuitamente questo prodotto dal sito di download Microsoft. Negli esempi e nelle procedure dettagliate riportate nella documentazione di [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] viene utilizzato SQL Server come archivio dati. Anziché SQL Server è tuttavia possibile usare come archivio dati SQL Server Express Edition, disponibile gratuitamente.  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>Download e installazione del database AdventureWorks  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>Per scaricare e installare il database di esempio AdventureWorks per SQL Server  
  
1.  Aprire Internet Explorer.  
  
2.  Passare al [esempi di SQL Server 2005 e database di esempio](http://go.microsoft.com/fwlink/?linkid=31046) sito Web.  
  
3.  Attenersi alle istruzioni per scaricare il database di esempio AdventureWorks corretto per il tipo di processore in utilizzo, ad esempio AdventureWorksDB.msi, quindi salvare il file MSI nel computer locale.  
  
4.  Se è già stata installata una versione precedente di AdventureWorks, tramite download o durante l'installazione di SQL Server, è necessario rimuoverla prima di eseguire AdventureWorks.msi.  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>Per rimuovere un download precedente di un database di esempio AdventureWorks  
  
1.  Rilasciare il database AdventureWorks o AdventureWorksDW.  
  
2.  Da **Aggiungi / Rimuovi programmi**selezionare **AdventureWorksDB** o **AdventureWorksBI** e fare clic su **rimuovere**.  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>Per rimuovere un database di esempio AdventureWorks installato in precedenza tramite il programma di installazione  
  
1.  Rilasciare il database AdventureWorks o AdventureWorksDW.  
  
2.  Da **Aggiungi / Rimuovi programmi**selezionare **Microsoft SQL Server 2005** e fare clic su **modifica**.  
  
3.  Da **Selezione componenti**selezionare **componenti Workstation** e quindi fare clic su **Avanti**.  
  
4.  Da **iniziale per l'installazione guidata di SQL Server**, fare clic su **Avanti**.  
  
5.  Da **controllo configurazione sistema**, fare clic su **Avanti**.  
  
6.  Da **cambia o Rimuovi istanza**, fare clic su **modifica componenti installati**.  
  
7.  Da **Selezione funzionalità**, espandere il **documentazione, esempi e database di esempio** nodo.  
  
8.  Selezionare **codice e applicazioni di esempio**. Espandere **database di esempio**, selezionare il database di esempio da rimuovere, quindi scegliere **la funzionalità completa non sarà disponibile**. Scegliere **Avanti**.  
  
9. Fare clic su **installare** e completare l'installazione guidata.  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>Per collegare i file del database di esempio AdventureWorks a un'istanza di SQL Server  
  
1.  Dopo aver scaricato il file di programma di installazione database di esempio file, fare doppio clic su di **AdventureWorksDB.msi** file (o il file scaricato) per installare il database. Per impostazione predefinita, il database viene installato in C:\Programmi\Microsoft SQL Server\MSSQL.1\MSSQL\Data.  
  
2.  Per collegare il file del database AdventureWorks a un'istanza di SQL Server, eseguire il seguente script SQLCMD o SQL Server Management Studio:  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Se i file sono stati installati in un'unità o una directory diversa, è necessario modificare i percorsi prima di eseguire la stored procedure `sp_attach_db`.  
  
## <a name="downloading-sql-server-express-edition"></a>Download di SQL Server Express Edition  
 Gli esempi e procedure dettagliate di [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] sezione utilizzare SQL Server 2005 come archivio dati, ma può essere modificato per utilizzare invece SQL Server Express Edition. SQL Server Express Edition è disponibile gratuitamente e può essere ridistribuito con le applicazioni. Se si utilizza Visual Studio, SQL Server Express Edition è incluso nelle edizioni Pro e superiori.  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>Per scaricare e installare SQL Server Express Edition  
  
1.  Avviare Internet Explorer.  
  
2.  Passare al [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) pagina di download.  
  
3.  Attenersi alle istruzioni di installazione visualizzate nel sito Web.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
