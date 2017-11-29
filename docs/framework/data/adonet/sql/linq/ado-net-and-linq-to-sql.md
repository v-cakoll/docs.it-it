---
title: ADO.NET e LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 97cf55419c6e13a497264bcbaa3a546eac37f982
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="626e9-102">ADO.NET e LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="626e9-102">ADO.NET and LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="626e9-103">fa parte di [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] famiglia di tecnologie.</span><span class="sxs-lookup"><span data-stu-id="626e9-103"> is part of the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] family of technologies.</span></span> <span data-ttu-id="626e9-104">e si basa sui servizi forniti dal modello provider [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)].</span><span class="sxs-lookup"><span data-stu-id="626e9-104">It is based on services provided by the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] provider model.</span></span> <span data-ttu-id="626e9-105">È pertanto possibile combinare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] codice con esistente [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] applicazioni ed eseguire la migrazione corrente [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] soluzioni a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="626e9-105">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] applications and migrate current [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="626e9-106">Nell'illustrazione seguente viene fornita una panoramica della relazione.</span><span class="sxs-lookup"><span data-stu-id="626e9-106">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="626e9-107">![LINQ to SQL e ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="626e9-107">![LINQ to SQL and ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="626e9-108">Connessioni</span><span class="sxs-lookup"><span data-stu-id="626e9-108">Connections</span></span>  
 <span data-ttu-id="626e9-109">È possibile fornire un oggetto esistente [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] connessione quando si crea un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="626e9-109">You can supply an existing [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="626e9-110">Tutte le operazioni di base di <xref:System.Data.Linq.DataContext> (incluse le query), utilizzare la connessione specificata.</span><span class="sxs-lookup"><span data-stu-id="626e9-110">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="626e9-111">Se la connessione è già aperta, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] lascia come quando è terminato con esso.</span><span class="sxs-lookup"><span data-stu-id="626e9-111">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="626e9-112">È comunque possibile accedere alla connessione e chiuderla usando la proprietà <xref:System.Data.Linq.DataContext.Connection%2A>, come nel codice seguente:</span><span class="sxs-lookup"><span data-stu-id="626e9-112">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="626e9-113">Transazioni</span><span class="sxs-lookup"><span data-stu-id="626e9-113">Transactions</span></span>  
 <span data-ttu-id="626e9-114">È possibile fornire l'oggetto <xref:System.Data.Linq.DataContext> con la transazione di database personalizzata qualora l'applicazione abbia già avviato la transazione e si desideri che venga usato anche <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="626e9-114">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="626e9-115">Il metodo preferito per creare transazioni con [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] consiste nell'usare l'oggetto <xref:System.Transactions.TransactionScope>.</span><span class="sxs-lookup"><span data-stu-id="626e9-115">The preferred method of doing transactions with the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="626e9-116">Usando questo approccio, è possibile creare transazioni distribuite che potranno essere usate sia con database che con altri gestori di risorse residenti in memoria.</span><span class="sxs-lookup"><span data-stu-id="626e9-116">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="626e9-117">Gli ambiti della transazione richiedono alcune risorse per il riavvio.</span><span class="sxs-lookup"><span data-stu-id="626e9-117">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="626e9-118">Vengono promossi a transazioni distribuite solo quando sono presenti più connessioni all'interno dell'ambito della transazione.</span><span class="sxs-lookup"><span data-stu-id="626e9-118">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="626e9-119">Non è possibile usare questo approccio per tutti i database.</span><span class="sxs-lookup"><span data-stu-id="626e9-119">You cannot use this approach for all databases.</span></span> <span data-ttu-id="626e9-120">Ad esempio, la connessione di SqlClient non consente di promuovere transazioni di sistema quando viene usata con un server [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)].</span><span class="sxs-lookup"><span data-stu-id="626e9-120">For example, the SqlClient connection cannot promote system transactions when it works against a [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)] server.</span></span> <span data-ttu-id="626e9-121">Al contrario, viene inserita automaticamente in una transazione distribuita completa quando viene rilevato l'uso di un ambito della transazione.</span><span class="sxs-lookup"><span data-stu-id="626e9-121">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="626e9-122">Comandi SQL diretti</span><span class="sxs-lookup"><span data-stu-id="626e9-122">Direct SQL Commands</span></span>  
 <span data-ttu-id="626e9-123">In alcune situazioni la capacità di <xref:System.Data.Linq.DataContext> di eseguire query o inviare modifiche è insufficiente per l'attività specifica che si desidera eseguire.</span><span class="sxs-lookup"><span data-stu-id="626e9-123">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="626e9-124">In queste circostanze è possibile usare il metodo <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> per inviare comandi SQL al database e convertire i risultati della query in oggetti.</span><span class="sxs-lookup"><span data-stu-id="626e9-124">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="626e9-125">Ad esempio, si supponga che i dati per la classe `Customer` siano distribuiti in due tabelle (customer1 e customer2).</span><span class="sxs-lookup"><span data-stu-id="626e9-125">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="626e9-126">La query seguente consente di restituire una sequenza di oggetti `Customer`:</span><span class="sxs-lookup"><span data-stu-id="626e9-126">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="626e9-127">Purché i nomi di colonna nei risultati tabulari corrispondano alle proprietà di colonna della classe di entità, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea gli oggetti da qualsiasi query SQL.</span><span class="sxs-lookup"><span data-stu-id="626e9-127">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="626e9-128">Parametri</span><span class="sxs-lookup"><span data-stu-id="626e9-128">Parameters</span></span>  
 <span data-ttu-id="626e9-129">Il metodo <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> accetta l'uso di parametri.</span><span class="sxs-lookup"><span data-stu-id="626e9-129">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="626e9-130">Nel codice seguente viene eseguita una query con parametri:</span><span class="sxs-lookup"><span data-stu-id="626e9-130">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
>  <span data-ttu-id="626e9-131">I parametri sono espressi nel testo della query usando la stessa notazione con parentesi graffe usata da `Console.WriteLine()` e `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="626e9-131">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="626e9-132">`String.Format()` sostituisce quindi i parametri con parentesi graffe presenti nella stringa fornita con nomi di parametro generati, ad esempio `@p0`, `@p1` …, `@p(n)`.</span><span class="sxs-lookup"><span data-stu-id="626e9-132">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="626e9-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="626e9-133">See Also</span></span>  
 [<span data-ttu-id="626e9-134">Informazioni generali</span><span class="sxs-lookup"><span data-stu-id="626e9-134">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [<span data-ttu-id="626e9-135">Procedura: riutilizzare una connessione tra un comando ADO.NET e un oggetto DataContext</span><span class="sxs-lookup"><span data-stu-id="626e9-135">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
