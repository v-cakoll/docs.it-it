---
title: Download di database di esempio (LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
ms.openlocfilehash: a98dd4e3d2ff113d3a5374d97fe30cec9524c095
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2018
ms.locfileid: "53125561"
---
# <a name="downloading-sample-databases-linq-to-dataset"></a><span data-ttu-id="b418b-102">Download di database di esempio (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="b418b-102">Downloading Sample Databases (LINQ to DataSet)</span></span>
<span data-ttu-id="b418b-103">Gli esempi e procedure dettagliate di [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentazione usano il database di esempio AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="b418b-103">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use the AdventureWorks sample database.</span></span> <span data-ttu-id="b418b-104">È possibile scaricare gratuitamente questo prodotto dal sito di download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b418b-104">You can download this product free of charge from the Microsoft download site.</span></span> <span data-ttu-id="b418b-105">Negli esempi e nelle procedure dettagliate riportate nella documentazione di [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] viene utilizzato SQL Server come archivio dati.</span><span class="sxs-lookup"><span data-stu-id="b418b-105">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] documentation use SQL Server as the data store.</span></span> <span data-ttu-id="b418b-106">Anziché SQL Server è tuttavia possibile usare come archivio dati SQL Server Express Edition, disponibile gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="b418b-106">SQL Server Express Edition, which is available without charge, can also be used as the data store instead of SQL Server.</span></span>  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a><span data-ttu-id="b418b-107">Download e installazione del database AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="b418b-107">Downloading and Installing the AdventureWorks Database</span></span>  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a><span data-ttu-id="b418b-108">Per scaricare e installare il database di esempio AdventureWorks per SQL Server</span><span class="sxs-lookup"><span data-stu-id="b418b-108">To download and install the AdventureWorks sample database for SQL Server</span></span>  
  
1.  <span data-ttu-id="b418b-109">Aprire Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b418b-109">Open Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="b418b-110">Andare alla [SQL Server 2005 Samples and Sample Databases](https://go.microsoft.com/fwlink/?linkid=31046) sito Web.</span><span class="sxs-lookup"><span data-stu-id="b418b-110">Go to the [SQL Server 2005 Samples and Sample Databases](https://go.microsoft.com/fwlink/?linkid=31046) Web site.</span></span>  
  
3.  <span data-ttu-id="b418b-111">Attenersi alle istruzioni per scaricare il database di esempio AdventureWorks corretto per il tipo di processore in utilizzo, ad esempio AdventureWorksDB.msi, quindi salvare il file MSI nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="b418b-111">Follow the instructions for downloading the AdventureWorks sample database for your processor type (such as AdventureWorksDB.msi), and save the .MSI file to your local computer.</span></span>  
  
4.  <span data-ttu-id="b418b-112">Se è già stata installata una versione precedente di AdventureWorks, tramite download o durante l'installazione di SQL Server, è necessario rimuoverla prima di eseguire AdventureWorks.msi.</span><span class="sxs-lookup"><span data-stu-id="b418b-112">If you have a previous version of AdventureWorks installed from the download or during the SQL Server setup, you must remove it before running AdventureWorks.msi.</span></span>  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a><span data-ttu-id="b418b-113">Per rimuovere un download precedente di un database di esempio AdventureWorks</span><span class="sxs-lookup"><span data-stu-id="b418b-113">To remove a previous download of an AdventureWorks sample database</span></span>  
  
1.  <span data-ttu-id="b418b-114">Rilasciare il database AdventureWorks o AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="b418b-114">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2.  <span data-ttu-id="b418b-115">Dal **Aggiungi / Rimuovi programmi**, selezionare **AdventureWorksDB** oppure **AdventureWorksBI** e fare clic su **rimuovere**.</span><span class="sxs-lookup"><span data-stu-id="b418b-115">From **Add or Remove Programs**, select **AdventureWorksDB** or **AdventureWorksBI** and click **Remove**.</span></span>  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a><span data-ttu-id="b418b-116">Per rimuovere un database di esempio AdventureWorks installato in precedenza tramite il programma di installazione</span><span class="sxs-lookup"><span data-stu-id="b418b-116">To remove an AdventureWorks sample database previously installed using Setup</span></span>  
  
1.  <span data-ttu-id="b418b-117">Rilasciare il database AdventureWorks o AdventureWorksDW.</span><span class="sxs-lookup"><span data-stu-id="b418b-117">Drop the AdventureWorks or AdventureWorksDW database.</span></span>  
  
2.  <span data-ttu-id="b418b-118">Dal **Aggiungi / Rimuovi programmi**, selezionare **Microsoft SQL Server 2005** e fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="b418b-118">From **Add or Remove Programs**, select **Microsoft SQL Server 2005** and click **Change**.</span></span>  
  
3.  <span data-ttu-id="b418b-119">Dal **componenti selezionati**, selezionare **componenti Workstation** e quindi fare clic su **Next**.</span><span class="sxs-lookup"><span data-stu-id="b418b-119">From **Component Selection**, select **Workstation Components** and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="b418b-120">Dal **l'installazione guidata di SQL Server**, fare clic su **successivo**.</span><span class="sxs-lookup"><span data-stu-id="b418b-120">From **Welcome to the SQL Server Installation Wizard**, click **Next**.</span></span>  
  
5.  <span data-ttu-id="b418b-121">Dal **controllo configurazione sistema**, fare clic su **successivo**.</span><span class="sxs-lookup"><span data-stu-id="b418b-121">From **System Configuration Check**, click **Next**.</span></span>  
  
6.  <span data-ttu-id="b418b-122">Dal **cambia o Rimuovi istanza**, fare clic su **modifica componenti installati**.</span><span class="sxs-lookup"><span data-stu-id="b418b-122">From **Change or Remove Instance**, click **Change Installed Components**.</span></span>  
  
7.  <span data-ttu-id="b418b-123">Dal **selezione delle caratteristiche**, espandere il **documentazione, esempi e database di esempio** nodo.</span><span class="sxs-lookup"><span data-stu-id="b418b-123">From **Feature Selection**, expand the **Documentation, Samples, and Sample Databases** node.</span></span>  
  
8.  <span data-ttu-id="b418b-124">Selezionare **codice e applicazioni di esempio**.</span><span class="sxs-lookup"><span data-stu-id="b418b-124">Select **Sample Code and Applications**.</span></span> <span data-ttu-id="b418b-125">Espandere **Sample Databases**, selezionare il database di esempio da rimuovere, quindi scegliere **funzionalità completa non sarà disponibile**.</span><span class="sxs-lookup"><span data-stu-id="b418b-125">Expand **Sample Databases**, select the sample database to be removed, and select **Entire feature will be unavailable**.</span></span> <span data-ttu-id="b418b-126">Scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b418b-126">Click **Next**.</span></span>  
  
9. <span data-ttu-id="b418b-127">Fare clic su **installare** e completare l'installazione guidata.</span><span class="sxs-lookup"><span data-stu-id="b418b-127">Click **Install** and finish the installation wizard.</span></span>  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a><span data-ttu-id="b418b-128">Per collegare i file del database di esempio AdventureWorks a un'istanza di SQL Server</span><span class="sxs-lookup"><span data-stu-id="b418b-128">To attach the AdventureWorks sample database files to an instance of SQL Server</span></span>  
  
1.  <span data-ttu-id="b418b-129">Dopo aver scaricato il file di programma di installazione database di esempio di file, fare doppio clic il **AdventureWorksDB. msi** file (o il file scaricato) per installare il database.</span><span class="sxs-lookup"><span data-stu-id="b418b-129">After the file sample database installer file has downloaded, double-click the **AdventureWorksDB.msi** file (or the file you downloaded) to install the database.</span></span> <span data-ttu-id="b418b-130">Per impostazione predefinita, il database viene installato in C:\Programmi\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="b418b-130">By default, the database is installed at c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="b418b-131">Per collegare il file del database AdventureWorks a un'istanza di SQL Server, eseguire il seguente script SQLCMD o SQL Server Management Studio:</span><span class="sxs-lookup"><span data-stu-id="b418b-131">Attach the AdventureWorks database files to an instance of SQL Server by executing the following script SQLCMD or SQL Server Management Studio:</span></span>  
  
    ```sql
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     <span data-ttu-id="b418b-132">Se i file sono stati installati in un'unità o una directory diversa, è necessario modificare i percorsi prima di eseguire la stored procedure `sp_attach_db`.</span><span class="sxs-lookup"><span data-stu-id="b418b-132">If you have installed these files to a different drive or directory, you must revise the paths appropriately before you execute the `sp_attach_db` stored procedure.</span></span>  
  
## <a name="downloading-sql-server-express-edition"></a><span data-ttu-id="b418b-133">Download di SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="b418b-133">Downloading SQL Server Express Edition</span></span>  
 <span data-ttu-id="b418b-134">Gli esempi e procedure dettagliate di [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] sezione utilizzare SQL Server 2005 come archivio dati, ma può essere modificato per usare SQL Server Express Edition, invece.</span><span class="sxs-lookup"><span data-stu-id="b418b-134">The samples and walkthroughs in the [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] section use SQL Server 2005 as the data store but can be modified to use SQL Server Express Edition, instead.</span></span> <span data-ttu-id="b418b-135">SQL Server Express Edition è disponibile gratuitamente e può essere ridistribuito con le applicazioni.</span><span class="sxs-lookup"><span data-stu-id="b418b-135">SQL Server Express Edition is available without charge, and you can redistribute it with applications.</span></span> <span data-ttu-id="b418b-136">Se si usa Visual Studio, SQL Server Express Edition è incluso nelle edizioni Pro e superiori.</span><span class="sxs-lookup"><span data-stu-id="b418b-136">If you are using Visual Studio, SQL Server Express Edition is included in the Pro and higher editions.</span></span>  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a><span data-ttu-id="b418b-137">Per scaricare e installare SQL Server Express Edition</span><span class="sxs-lookup"><span data-stu-id="b418b-137">To download and install SQL Server Express Edition</span></span>  
  
1.  <span data-ttu-id="b418b-138">Avviare Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="b418b-138">Start Internet Explorer.</span></span>  
  
2.  <span data-ttu-id="b418b-139">Andare alla [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) pagina di download.</span><span class="sxs-lookup"><span data-stu-id="b418b-139">Go to the  [Microsoft SQL Server 2005 Express Edition](https://go.microsoft.com/fwlink/?LinkID=31070) download page.</span></span>  
  
3.  <span data-ttu-id="b418b-140">Attenersi alle istruzioni di installazione visualizzate nel sito Web.</span><span class="sxs-lookup"><span data-stu-id="b418b-140">Follow the installation instructions on the Web site.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b418b-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b418b-141">See Also</span></span>  
 [<span data-ttu-id="b418b-142">Introduzione</span><span class="sxs-lookup"><span data-stu-id="b418b-142">Getting Started</span></span>](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
