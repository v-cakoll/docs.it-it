---
title: Download di database di esempio (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: c67ee699cf594f476a728c7345b47b0c32dea7ff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795172"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>Download di database di esempio (LINQ to DataSet)
Negli esempi e nelle procedure dettagliate della documentazione LINQ to DataSet viene utilizzato il database di esempio AdventureWorks. È possibile scaricare gratuitamente questo prodotto dal sito di download Microsoft. Gli esempi e le procedure dettagliate nella documentazione di LINQ to DataSet usano SQL Server come archivio dati. Anziché SQL Server è tuttavia possibile usare come archivio dati SQL Server Express Edition, disponibile gratuitamente.  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>Download e installazione del database AdventureWorks  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>Per scaricare e installare il database di esempio AdventureWorks per SQL Server  
  
1. Aprire Internet Explorer.  
  
2. Passare al sito Web di [esempio SQL Server 2005 Samples e database di esempio](https://go.microsoft.com/fwlink/?linkid=31046) .  
  
3. Attenersi alle istruzioni per scaricare il database di esempio AdventureWorks corretto per il tipo di processore in utilizzo, ad esempio AdventureWorksDB.msi, quindi salvare il file MSI nel computer locale.  
  
4. Se è già stata installata una versione precedente di AdventureWorks, tramite download o durante l'installazione di SQL Server, è necessario rimuoverla prima di eseguire AdventureWorks.msi.  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>Per rimuovere un download precedente di un database di esempio AdventureWorks  
  
1. Rilasciare il database AdventureWorks o AdventureWorksDW.  
  
2. Da **Installazione applicazioni**selezionare **AdventureWorksDB** o **AdventureWorksBI** e fare clic su **Rimuovi**.  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>Per rimuovere un database di esempio AdventureWorks installato in precedenza tramite il programma di installazione  
  
1. Rilasciare il database AdventureWorks o AdventureWorksDW.  
  
2. Da **Installazione applicazioni**selezionare **Microsoft SQL Server 2005** e fare clic su **Cambia**.  
  
3. In **selezione**componenti selezionare **componenti workstation** e quindi fare clic su **Avanti**.  
  
4. Da **Benvenuti all'installazione guidata di SQL Server**fare clic su **Avanti**.  
  
5. In **controllo configurazione sistema**fare clic su **Avanti**.  
  
6. In **Cambia o Rimuovi istanza**fare clic su **modifica componenti installati**.  
  
7. In **Selezione funzionalità**espandere il nodo **documentazione, esempi e database di esempio** .  
  
8. Selezionare il **codice di esempio e le applicazioni**. Espandere **database di esempio**, selezionare il database di esempio da rimuovere e selezionare la **funzionalità completa**non sarà disponibile. Fare clic su **Avanti**.  
  
9. Fare clic su **Installa** e terminare l'installazione guidata.  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>Per collegare i file del database di esempio AdventureWorks a un'istanza di SQL Server  
  
1. Dopo aver scaricato il file del programma di installazione del database di esempio, fare doppio clic sul file **AdventureWorksDB. msi** (o sul file scaricato) per installare il database. Per impostazione predefinita, il database viene installato in C:\Programmi\Microsoft SQL Server\MSSQL.1\MSSQL\Data.  
  
2. Per collegare il file del database AdventureWorks a un'istanza di SQL Server, eseguire il seguente script SQLCMD o SQL Server Management Studio:  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     Se i file sono stati installati in un'unità o una directory diversa, è necessario modificare i percorsi prima di eseguire la stored procedure `sp_attach_db`.  
  
## <a name="downloading-sql-server-express-edition"></a>Download di SQL Server Express Edition  
 Gli esempi e le procedure dettagliate nella sezione LINQ to DataSet usano SQL Server 2005 come archivio dati, ma possono essere modificati per usare SQL Server Express Edition. SQL Server Express Edition è disponibile gratuitamente e può essere ridistribuito con le applicazioni. Se si usa Visual Studio, SQL Server Express Edition è incluso nelle edizioni Pro e versioni successive.  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>Per scaricare e installare SQL Server Express Edition  
  
1. Avviare Internet Explorer.  
  
2. Visitare la pagina di download di [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) .  
  
3. Attenersi alle istruzioni di installazione visualizzate nel sito Web.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione](getting-started-linq-to-dataset.md)
