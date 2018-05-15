---
title: LINQ to SQL esempio
ms.date: 03/30/2017
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
ms.openlocfilehash: 3cfcaf3de1a22b8bb5505083f127a9888b99dbd8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2018
---
# <a name="linq-to-sql-sample"></a><span data-ttu-id="08cf9-102">LINQ to SQL esempio</span><span class="sxs-lookup"><span data-stu-id="08cf9-102">LINQ to SQL Sample</span></span>
<span data-ttu-id="08cf9-103">In questo esempio viene illustrato come creare un'attività per l'uso di entità di query LINQ to SQL da tabelle nei database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="08cf9-103">This sample demonstrates how to create an activity to use LINQ to SQL query entities from tables in SQL Server databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="08cf9-104">Gli esempi WCF siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="08cf9-104">The WCF samples may already be installed on your machine.</span></span> <span data-ttu-id="08cf9-105">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="08cf9-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  <span data-ttu-id="08cf9-106">Se questa directory non esiste, fare clic sul collegamento per il download di esempi nella parte superiore di questa pagina.</span><span class="sxs-lookup"><span data-stu-id="08cf9-106">If this directory does not exist, click the download sample link at the top of this page.</span></span> <span data-ttu-id="08cf9-107">Si noti che questo collegamento Scarica e installa tutti i [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, e [!INCLUDE[infocard](../../../../includes/infocard-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="08cf9-107">Note that this link downloads and installs all of the [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF, and [!INCLUDE[infocard](../../../../includes/infocard-md.md)] samples.</span></span> <span data-ttu-id="08cf9-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="08cf9-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a><span data-ttu-id="08cf9-109">Dettagli dell'attività per FindInSqlTable</span><span class="sxs-lookup"><span data-stu-id="08cf9-109">Activity details for FindInSqlTable</span></span>  
 <span data-ttu-id="08cf9-110">Questa attività consente agli utenti di eseguire query su entità di tabelle in un database usando LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="08cf9-110">This activity allows users to query entities from tables in a database using LINQ to SQL.</span></span> <span data-ttu-id="08cf9-111">Gli utenti dell'attività devono inoltre fornire un predicato LINQ nel formato di un'espressione lambda per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="08cf9-111">Users of the activity can also provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="08cf9-112">Se non è fornito alcun predicato, viene restituita l'intera tabella.</span><span class="sxs-lookup"><span data-stu-id="08cf9-112">If no predicate is provided, the entire table is returned.</span></span> <span data-ttu-id="08cf9-113">Nella tabella seguente viene descritta la proprietà e i valori restituiti per l'attività.</span><span class="sxs-lookup"><span data-stu-id="08cf9-113">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="08cf9-114">Proprietà o valore restituito</span><span class="sxs-lookup"><span data-stu-id="08cf9-114">Property or Return Value</span></span>|<span data-ttu-id="08cf9-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="08cf9-115">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="08cf9-116">Proprietà `Collection`</span><span class="sxs-lookup"><span data-stu-id="08cf9-116">`Collection` property</span></span>|<span data-ttu-id="08cf9-117">Proprietà obbligatoria che specifica la raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="08cf9-117">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="08cf9-118">Proprietà `Predicate`</span><span class="sxs-lookup"><span data-stu-id="08cf9-118">`Predicate` property</span></span>|<span data-ttu-id="08cf9-119">Proprietà obbligatoria che specifica il filtro per la raccolta nel formato di un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="08cf9-119">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="08cf9-120">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="08cf9-120">Return Value</span></span>|<span data-ttu-id="08cf9-121">La raccolta filtrata.</span><span class="sxs-lookup"><span data-stu-id="08cf9-121">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="08cf9-122">Esempio di codice che usa l'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="08cf9-122">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="08cf9-123">Nell'esempio di codice seguente viene usata l'attività personalizzata `FindInSqlTable` per trovare tutte le righe in una tabella di SQL Server denominata `Employee` dove la colonna `Role` è uguale a `SDE`.</span><span class="sxs-lookup"><span data-stu-id="08cf9-123">The following code example uses the `FindInSqlTable` custom activity to find all rows in a SQL Server table named `Employee` where the `Role` column is equal to `SDE`.</span></span>  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="08cf9-124">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="08cf9-124">To use this sample</span></span>  
  
1.  <span data-ttu-id="08cf9-125">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="08cf9-125">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="08cf9-126">Passare alla cartella contenente questo esempio.</span><span class="sxs-lookup"><span data-stu-id="08cf9-126">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="08cf9-127">Eseguire il file di comando Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="08cf9-127">Run the Setup.cmd command file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="08cf9-128">Lo script Setup.cmd tenta di installare il database di esempio in SQL Server Express nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="08cf9-128">The Setup.cmd script attempts to install the sample database in your local machine SQL Server Express.</span></span> <span data-ttu-id="08cf9-129">Se si desidera installarlo nell'altra istanza del server SQL, modificare Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="08cf9-129">If you want to install it in other SQL server instance, edit Setup.cmd.</span></span>  
  
     <span data-ttu-id="08cf9-130">Lo script Setup.cmd esegue le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="08cf9-130">The Setup.cmd script does the following actions.:</span></span>  
  
    -   <span data-ttu-id="08cf9-131">Crea un database denominato LinqToSqlSample.</span><span class="sxs-lookup"><span data-stu-id="08cf9-131">Creates a database called LinqToSqlSample.</span></span>  
  
    -   <span data-ttu-id="08cf9-132">Crea una tabella Ruoli.</span><span class="sxs-lookup"><span data-stu-id="08cf9-132">Creates a Roles table.</span></span>  
  
    -   <span data-ttu-id="08cf9-133">Crea una tabella Employees.</span><span class="sxs-lookup"><span data-stu-id="08cf9-133">Creates an Employees table.</span></span>  
  
    -   <span data-ttu-id="08cf9-134">Inserisce 3 record nella tabella Ruoli.</span><span class="sxs-lookup"><span data-stu-id="08cf9-134">Inserts 3 records into the Roles table.</span></span>  
  
    -   <span data-ttu-id="08cf9-135">Inserisce 12 record nella tabella Employees.</span><span class="sxs-lookup"><span data-stu-id="08cf9-135">Inserts 12 records into the Employees table.</span></span>  
  
4.  <span data-ttu-id="08cf9-136">Usando [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], aprire il file della soluzione LinqToSQL.sln.</span><span class="sxs-lookup"><span data-stu-id="08cf9-136">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToSQL.sln solution file.</span></span>  
  
5.  <span data-ttu-id="08cf9-137">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="08cf9-137">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="08cf9-138">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="08cf9-138">To run the solution, press F5.</span></span>  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a><span data-ttu-id="08cf9-139">Per disinstallare il database di esempio LinqToSql</span><span class="sxs-lookup"><span data-stu-id="08cf9-139">To uninstall the LinqToSql sample database</span></span>  
  
1.  <span data-ttu-id="08cf9-140">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="08cf9-140">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="08cf9-141">Passare alla cartella contenente questo esempio.</span><span class="sxs-lookup"><span data-stu-id="08cf9-141">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="08cf9-142">Eseguire il file di comando Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="08cf9-142">Run the Cleanup.cmd command file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="08cf9-143">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="08cf9-143">The samples may already be installed on your machine.</span></span> <span data-ttu-id="08cf9-144">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="08cf9-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="08cf9-145">Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi.</span><span class="sxs-lookup"><span data-stu-id="08cf9-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="08cf9-146">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="08cf9-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a><span data-ttu-id="08cf9-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="08cf9-147">See Also</span></span>  
 [<span data-ttu-id="08cf9-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="08cf9-148">LINQ to SQL</span></span>](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [<span data-ttu-id="08cf9-149">Introduzione (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="08cf9-149">Getting Started (LINQ to SQL)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150377)
