---
title: LINQ to SQL esempio
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 03805d8917d16752cd84838fe210540a68c3f905
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2017
---
# <a name="linq-to-sql-sample"></a><span data-ttu-id="7b13f-102">LINQ to SQL esempio</span><span class="sxs-lookup"><span data-stu-id="7b13f-102">LINQ to SQL Sample</span></span>
<span data-ttu-id="7b13f-103">In questo esempio viene illustrato come creare un'attività per l'uso di entità di query LINQ to SQL da tabelle nei database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="7b13f-103">This sample demonstrates how to create an activity to use LINQ to SQL query entities from tables in SQL Server databases.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7b13f-104">È possibile che gli esempi di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="7b13f-104">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] samples may already be installed on your machine.</span></span> <span data-ttu-id="7b13f-105">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="7b13f-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  <span data-ttu-id="7b13f-106">Se questa directory non esiste, fare clic sul collegamento per il download di esempi nella parte superiore di questa pagina.</span><span class="sxs-lookup"><span data-stu-id="7b13f-106">If this directory does not exist, click the download sample link at the top of this page.</span></span> <span data-ttu-id="7b13f-107">Notare che questo collegamento scarica e installa tutti gli esempi di [!INCLUDE[wf1](../../../../includes/wf1-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] e [!INCLUDE[infocard](../../../../includes/infocard-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7b13f-107">Note that this link downloads and installs all of the [!INCLUDE[wf1](../../../../includes/wf1-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and [!INCLUDE[infocard](../../../../includes/infocard-md.md)] samples.</span></span> <span data-ttu-id="7b13f-108">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="7b13f-108">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a><span data-ttu-id="7b13f-109">Dettagli dell'attività per FindInSqlTable</span><span class="sxs-lookup"><span data-stu-id="7b13f-109">Activity details for FindInSqlTable</span></span>  
 <span data-ttu-id="7b13f-110">Questa attività consente agli utenti di eseguire query su entità di tabelle in un database usando LINQ to SQL.</span><span class="sxs-lookup"><span data-stu-id="7b13f-110">This activity allows users to query entities from tables in a database using LINQ to SQL.</span></span> <span data-ttu-id="7b13f-111">Gli utenti dell'attività devono inoltre fornire un predicato LINQ nel formato di un'espressione lambda per filtrare i risultati.</span><span class="sxs-lookup"><span data-stu-id="7b13f-111">Users of the activity can also provide a LINQ predicate in the form of a lambda expression to filter the results.</span></span> <span data-ttu-id="7b13f-112">Se non è fornito alcun predicato, viene restituita l'intera tabella.</span><span class="sxs-lookup"><span data-stu-id="7b13f-112">If no predicate is provided, the entire table is returned.</span></span> <span data-ttu-id="7b13f-113">Nella tabella seguente viene descritta la proprietà e i valori restituiti per l'attività.</span><span class="sxs-lookup"><span data-stu-id="7b13f-113">The following table details the property and return values for the activity.</span></span>  
  
|<span data-ttu-id="7b13f-114">Proprietà o valore restituito</span><span class="sxs-lookup"><span data-stu-id="7b13f-114">Property or Return Value</span></span>|<span data-ttu-id="7b13f-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7b13f-115">Description</span></span>|  
|------------------------------|-----------------|  
|<span data-ttu-id="7b13f-116">Proprietà `Collection`</span><span class="sxs-lookup"><span data-stu-id="7b13f-116">`Collection` property</span></span>|<span data-ttu-id="7b13f-117">Proprietà obbligatoria che specifica la raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="7b13f-117">A required property that specifies the source collection.</span></span>|  
|<span data-ttu-id="7b13f-118">Proprietà `Predicate`</span><span class="sxs-lookup"><span data-stu-id="7b13f-118">`Predicate` property</span></span>|<span data-ttu-id="7b13f-119">Proprietà obbligatoria che specifica il filtro per la raccolta nel formato di un'espressione lambda.</span><span class="sxs-lookup"><span data-stu-id="7b13f-119">A required property that specifies the filter for the collection in the form of a lambda expression.</span></span>|  
|<span data-ttu-id="7b13f-120">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="7b13f-120">Return Value</span></span>|<span data-ttu-id="7b13f-121">La raccolta filtrata.</span><span class="sxs-lookup"><span data-stu-id="7b13f-121">The filtered collection.</span></span>|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a><span data-ttu-id="7b13f-122">Esempio di codice che usa l'attività personalizzata</span><span class="sxs-lookup"><span data-stu-id="7b13f-122">Code Sample that uses the Custom Activity</span></span>  
 <span data-ttu-id="7b13f-123">Nell'esempio di codice seguente viene usata l'attività personalizzata `FindInSqlTable` per trovare tutte le righe in una tabella di SQL Server denominata `Employee` dove la colonna `Role` è uguale a `SDE`.</span><span class="sxs-lookup"><span data-stu-id="7b13f-123">The following code example uses the `FindInSqlTable` custom activity to find all rows in a SQL Server table named `Employee` where the `Role` column is equal to `SDE`.</span></span>  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="7b13f-124">Per usare questo esempio</span><span class="sxs-lookup"><span data-stu-id="7b13f-124">To use this sample</span></span>  
  
1.  <span data-ttu-id="7b13f-125">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="7b13f-125">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="7b13f-126">Passare alla cartella contenente questo esempio.</span><span class="sxs-lookup"><span data-stu-id="7b13f-126">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="7b13f-127">Eseguire il file di comando Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="7b13f-127">Run the Setup.cmd command file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7b13f-128">Lo script Setup.cmd tenta di installare il database di esempio in SQL Server Express nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="7b13f-128">The Setup.cmd script attempts to install the sample database in your local machine SQL Server Express.</span></span> <span data-ttu-id="7b13f-129">Se si desidera installarlo nell'altra istanza del server SQL, modificare Setup.cmd.</span><span class="sxs-lookup"><span data-stu-id="7b13f-129">If you want to install it in other SQL server instance, edit Setup.cmd.</span></span>  
  
     <span data-ttu-id="7b13f-130">Lo script Setup.cmd esegue le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b13f-130">The Setup.cmd script does the following actions.:</span></span>  
  
    -   <span data-ttu-id="7b13f-131">Crea un database denominato LinqToSqlSample.</span><span class="sxs-lookup"><span data-stu-id="7b13f-131">Creates a database called LinqToSqlSample.</span></span>  
  
    -   <span data-ttu-id="7b13f-132">Crea una tabella Ruoli.</span><span class="sxs-lookup"><span data-stu-id="7b13f-132">Creates a Roles table.</span></span>  
  
    -   <span data-ttu-id="7b13f-133">Crea una tabella Employees.</span><span class="sxs-lookup"><span data-stu-id="7b13f-133">Creates an Employees table.</span></span>  
  
    -   <span data-ttu-id="7b13f-134">Inserisce 3 record nella tabella Ruoli.</span><span class="sxs-lookup"><span data-stu-id="7b13f-134">Inserts 3 records into the Roles table.</span></span>  
  
    -   <span data-ttu-id="7b13f-135">Inserisce 12 record nella tabella Employees.</span><span class="sxs-lookup"><span data-stu-id="7b13f-135">Inserts 12 records into the Employees table.</span></span>  
  
4.  <span data-ttu-id="7b13f-136">Usando [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], aprire il file della soluzione LinqToSQL.sln.</span><span class="sxs-lookup"><span data-stu-id="7b13f-136">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the LinqToSQL.sln solution file.</span></span>  
  
5.  <span data-ttu-id="7b13f-137">Per compilare la soluzione, premere CTRL+MAIUSC+B.</span><span class="sxs-lookup"><span data-stu-id="7b13f-137">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
6.  <span data-ttu-id="7b13f-138">Per eseguire la soluzione, premere F5.</span><span class="sxs-lookup"><span data-stu-id="7b13f-138">To run the solution, press F5.</span></span>  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a><span data-ttu-id="7b13f-139">Per disinstallare il database di esempio LinqToSql</span><span class="sxs-lookup"><span data-stu-id="7b13f-139">To uninstall the LinqToSql sample database</span></span>  
  
1.  <span data-ttu-id="7b13f-140">Aprire un prompt dei comandi.</span><span class="sxs-lookup"><span data-stu-id="7b13f-140">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="7b13f-141">Passare alla cartella contenente questo esempio.</span><span class="sxs-lookup"><span data-stu-id="7b13f-141">Navigate to the folder that contains this sample.</span></span>  
  
3.  <span data-ttu-id="7b13f-142">Eseguire il file di comando Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="7b13f-142">Run the Cleanup.cmd command file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7b13f-143">È possibile che gli esempi siano già installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="7b13f-143">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7b13f-144">Verificare la directory seguente (impostazione predefinita) prima di continuare.</span><span class="sxs-lookup"><span data-stu-id="7b13f-144">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="7b13f-145">Se questa directory non esiste, andare alla sezione relativa agli [esempi di Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti gli esempi di [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7b13f-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7b13f-146">Questo esempio si trova nella directory seguente.</span><span class="sxs-lookup"><span data-stu-id="7b13f-146">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a><span data-ttu-id="7b13f-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b13f-147">See Also</span></span>  
 [<span data-ttu-id="7b13f-148">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="7b13f-148">LINQ to SQL</span></span>](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [<span data-ttu-id="7b13f-149">Introduzione (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="7b13f-149">Getting Started (LINQ to SQL)</span></span>](http://go.microsoft.com/fwlink/?LinkId=150377)
