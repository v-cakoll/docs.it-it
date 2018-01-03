---
title: Transazioni e concorrenza
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 4301a232e2b38d44ecb288e76439742f7fe4d58f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="f7885-102">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="f7885-102">Transactions and Concurrency</span></span>
<span data-ttu-id="f7885-103">Una transazione è costituita da un singolo comando o da un gruppo di comandi che vengono eseguiti come un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="f7885-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="f7885-104">Le transazioni consentono di combinare più operazioni in un'unica unità di lavoro.</span><span class="sxs-lookup"><span data-stu-id="f7885-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="f7885-105">Se si verifica un problema in un determinato punto della transazione, sarà possibile annullare tutti gli aggiornamenti ripristinando la condizione antecedente all'inizio della transazione.</span><span class="sxs-lookup"><span data-stu-id="f7885-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="f7885-106">Per poter garantire la coerenza dei dati, una transazione deve essere conforme alle proprietà ACID, ovvero atomicità, coerenza, isolamento e durabilità.</span><span class="sxs-lookup"><span data-stu-id="f7885-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="f7885-107">La maggioranza dei sistemi di database relazionale, ad esempio Microsoft SQL Server, supportano le transazioni fornendo funzionalità di blocco, di registrazione e di gestione delle transazioni volta che un'applicazione client esegue un'operazione di aggiornamento, inserimento o eliminazione.</span><span class="sxs-lookup"><span data-stu-id="f7885-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7885-108">Le transazioni che implicano l'uso di più risorse possono abbassare la concorrenza se i blocchi vengono mantenuti troppo a lungo.</span><span class="sxs-lookup"><span data-stu-id="f7885-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="f7885-109">Mantenere pertanto le transazioni per il minor tempo possibile.</span><span class="sxs-lookup"><span data-stu-id="f7885-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="f7885-110">Se una transazione implica l'uso di più tabelle nello stesso database o server, è spesso preferibile usare transazioni esplicite nelle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="f7885-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="f7885-111">È possibile creare transazioni in stored procedure SQL Server usando le istruzioni Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION` e `ROLLBACK TRANSACTION`.</span><span class="sxs-lookup"><span data-stu-id="f7885-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="f7885-112">Per altre informazioni, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f7885-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="f7885-113">Per le transazioni che implicano l'uso di gestori di risorse diversi, ad esempio una transazione tra [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] e Oracle, è necessaria una transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="f7885-113">Transactions involving different resource managers, such as a transaction between [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7885-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="f7885-114">In This Section</span></span>  
 [<span data-ttu-id="f7885-115">Transazioni locali</span><span class="sxs-lookup"><span data-stu-id="f7885-115">Local Transactions</span></span>](../../../../docs/framework/data/adonet/local-transactions.md)  
 <span data-ttu-id="f7885-116">Viene illustrato come eseguire transazioni su un database.</span><span class="sxs-lookup"><span data-stu-id="f7885-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="f7885-117">Transazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="f7885-117">Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 <span data-ttu-id="f7885-118">Viene descritto come eseguire transazioni distribuite in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f7885-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="f7885-119">Integrazione di System.Transactions con SQL Server</span><span class="sxs-lookup"><span data-stu-id="f7885-119">System.Transactions Integration with SQL Server</span></span>](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="f7885-120">Viene descritta l'integrazione di <xref:System.Transactions> con [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] per l'uso di transazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="f7885-120">Describes <xref:System.Transactions> integration with [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="f7885-121">Concorrenza ottimistica</span><span class="sxs-lookup"><span data-stu-id="f7885-121">Optimistic Concurrency</span></span>](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 <span data-ttu-id="f7885-122">Vengono descritte la concorrenza ottimistica e la concorrenza pessimistica e come è possibile verificare le violazioni della concorrenza.</span><span class="sxs-lookup"><span data-stu-id="f7885-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7885-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7885-123">See Also</span></span>  
 [<span data-ttu-id="f7885-124">Nozioni fondamentali sulle transazioni</span><span class="sxs-lookup"><span data-stu-id="f7885-124">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)  
 [<span data-ttu-id="f7885-125">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="f7885-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)  
 [<span data-ttu-id="f7885-126">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="f7885-126">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)  
 [<span data-ttu-id="f7885-127">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="f7885-127">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="f7885-128">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="f7885-128">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 [<span data-ttu-id="f7885-129">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="f7885-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
