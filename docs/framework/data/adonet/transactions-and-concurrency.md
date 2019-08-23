---
title: Transazioni e concorrenza
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: c78031150d9b1209372dece49813dfcf0a03b9d5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965209"
---
# <a name="transactions-and-concurrency"></a><span data-ttu-id="321ae-102">Transazioni e concorrenza</span><span class="sxs-lookup"><span data-stu-id="321ae-102">Transactions and Concurrency</span></span>
<span data-ttu-id="321ae-103">Una transazione è costituita da un singolo comando o da un gruppo di comandi che vengono eseguiti come un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="321ae-103">A transaction consists of a single command or a group of commands that execute as a package.</span></span> <span data-ttu-id="321ae-104">Le transazioni consentono di combinare più operazioni in un'unica unità di lavoro.</span><span class="sxs-lookup"><span data-stu-id="321ae-104">Transactions allow you to combine multiple operations into a single unit of work.</span></span> <span data-ttu-id="321ae-105">Se si verifica un problema in un determinato punto della transazione, sarà possibile annullare tutti gli aggiornamenti ripristinando la condizione antecedente all'inizio della transazione.</span><span class="sxs-lookup"><span data-stu-id="321ae-105">If a failure occurs at one point in the transaction, all of the updates can be rolled back to their pre-transaction state.</span></span>  
  
 <span data-ttu-id="321ae-106">Per poter garantire la coerenza dei dati, una transazione deve essere conforme alle proprietà ACID, ovvero atomicità, coerenza, isolamento e durabilità.</span><span class="sxs-lookup"><span data-stu-id="321ae-106">A transaction must conform to the ACID properties—atomicity, consistency, isolation, and durability—in order to guarantee data consistency.</span></span> <span data-ttu-id="321ae-107">La maggior parte dei sistemi di database relazionale, ad esempio Microsoft SQL Server, supporta le transazioni fornendo funzionalità di blocco, di registrazione e di gestione delle transazioni ogni volta che un'applicazione client esegue un'operazione di aggiornamento, inserimento o eliminazione.</span><span class="sxs-lookup"><span data-stu-id="321ae-107">Most relational database systems, such as Microsoft SQL Server, support transactions by providing locking, logging, and transaction management facilities whenever a client application performs an update, insert, or delete operation.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="321ae-108">Le transazioni che implicano l'uso di più risorse possono abbassare la concorrenza se i blocchi vengono mantenuti troppo a lungo.</span><span class="sxs-lookup"><span data-stu-id="321ae-108">Transactions that involve multiple resources can lower concurrency if locks are held too long.</span></span> <span data-ttu-id="321ae-109">Mantenere pertanto le transazioni per il minor tempo possibile.</span><span class="sxs-lookup"><span data-stu-id="321ae-109">Therefore, keep transactions as short as possible.</span></span>  
  
 <span data-ttu-id="321ae-110">Se una transazione implica l'uso di più tabelle nello stesso database o server, è spesso preferibile usare transazioni esplicite nelle stored procedure.</span><span class="sxs-lookup"><span data-stu-id="321ae-110">If a transaction involves multiple tables in the same database or server, then explicit transactions in stored procedures often perform better.</span></span> <span data-ttu-id="321ae-111">È possibile creare transazioni in stored procedure SQL Server usando le istruzioni Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION` e `ROLLBACK TRANSACTION`.</span><span class="sxs-lookup"><span data-stu-id="321ae-111">You can create transactions in SQL Server stored procedures by using the Transact-SQL `BEGIN TRANSACTION`, `COMMIT TRANSACTION`, and `ROLLBACK TRANSACTION` statements.</span></span> <span data-ttu-id="321ae-112">Per altre informazioni, vedere la documentazione online di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="321ae-112">For more information, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="321ae-113">Le transazioni che coinvolgono diversi gestori di risorse, ad esempio una transazione tra SQL Server e Oracle, richiedono una transazione distribuita.</span><span class="sxs-lookup"><span data-stu-id="321ae-113">Transactions involving different resource managers, such as a transaction between SQL Server and Oracle, require a distributed transaction.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="321ae-114">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="321ae-114">In This Section</span></span>  
 [<span data-ttu-id="321ae-115">Transazioni locali</span><span class="sxs-lookup"><span data-stu-id="321ae-115">Local Transactions</span></span>](../../../../docs/framework/data/adonet/local-transactions.md)  
 <span data-ttu-id="321ae-116">Viene illustrato come eseguire transazioni su un database.</span><span class="sxs-lookup"><span data-stu-id="321ae-116">Demonstrates how to perform transactions against a database.</span></span>  
  
 [<span data-ttu-id="321ae-117">Transazioni distribuite</span><span class="sxs-lookup"><span data-stu-id="321ae-117">Distributed Transactions</span></span>](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 <span data-ttu-id="321ae-118">Viene descritto come eseguire transazioni distribuite in ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="321ae-118">Describes how to perform distributed transactions in ADO.NET.</span></span>  
  
 [<span data-ttu-id="321ae-119">Integrazione di System.Transactions con SQL Server</span><span class="sxs-lookup"><span data-stu-id="321ae-119">System.Transactions Integration with SQL Server</span></span>](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 <span data-ttu-id="321ae-120">Viene <xref:System.Transactions> descritta l'integrazione con SQL Server per l'utilizzo di transazioni distribuite.</span><span class="sxs-lookup"><span data-stu-id="321ae-120">Describes <xref:System.Transactions> integration with SQL Server for working with distributed transactions.</span></span>  
  
 [<span data-ttu-id="321ae-121">Concorrenza ottimistica</span><span class="sxs-lookup"><span data-stu-id="321ae-121">Optimistic Concurrency</span></span>](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 <span data-ttu-id="321ae-122">Vengono descritte la concorrenza ottimistica e la concorrenza pessimistica e come è possibile verificare le violazioni della concorrenza.</span><span class="sxs-lookup"><span data-stu-id="321ae-122">Describes optimistic and pessimistic concurrency, and how you can test for concurrency violations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="321ae-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="321ae-123">See also</span></span>

- [<span data-ttu-id="321ae-124">Nozioni fondamentali sulle transazioni</span><span class="sxs-lookup"><span data-stu-id="321ae-124">Transaction Fundamentals</span></span>](../../../../docs/framework/data/transactions/transaction-fundamentals.md)
- [<span data-ttu-id="321ae-125">Connessione a un'origine dati</span><span class="sxs-lookup"><span data-stu-id="321ae-125">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [<span data-ttu-id="321ae-126">Comandi e parametri</span><span class="sxs-lookup"><span data-stu-id="321ae-126">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="321ae-127">DataAdapter e DataReader</span><span class="sxs-lookup"><span data-stu-id="321ae-127">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="321ae-128">DbProviderFactories</span><span class="sxs-lookup"><span data-stu-id="321ae-128">DbProviderFactories</span></span>](../../../../docs/framework/data/adonet/dbproviderfactories.md)
- [<span data-ttu-id="321ae-129">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="321ae-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
