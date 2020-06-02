---
title: 'Procedura: eseguire direttamente query SQL'
description: Informazioni su come usare ExecuteQuery per eseguire una query e quindi convertire i risultati direttamente in oggetti nei casi in cui una query di LINQ to SQL non è sufficiente.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: 59bd404e41f6be1181d6a625c31ee23358db0df3
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286365"
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="72e6f-103">Procedura: eseguire direttamente query SQL</span><span class="sxs-lookup"><span data-stu-id="72e6f-103">How to: Directly Execute SQL Queries</span></span>
<span data-ttu-id="72e6f-104">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query create vengono convertite in query SQL con parametri, in formato testo, e inviate al server SQL per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="72e6f-104">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="72e6f-105">Non è possibile eseguire in SQL la varietà di metodi eventualmente disponibili localmente per l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="72e6f-105">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> <span data-ttu-id="72e6f-106">pertanto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tenta di convertire questi metodi locali nelle operazioni e funzioni equivalenti disponibili nell'ambiente SQL.</span><span class="sxs-lookup"><span data-stu-id="72e6f-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="72e6f-107">La maggior parte dei metodi e degli operatori nei tipi incorporati .NET Framework dispone di traduzioni dirette nei comandi SQL.</span><span class="sxs-lookup"><span data-stu-id="72e6f-107">Most methods and operators on .NET Framework built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="72e6f-108">Alcuni possono essere prodotti dalle funzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="72e6f-108">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="72e6f-109">Quelli che non possono essere prodotti generano eccezioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="72e6f-109">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="72e6f-110">Per ulteriori informazioni, vedere [mapping dei tipi SQL-CLR](sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="72e6f-110">For more information, see [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="72e6f-111">Nei casi in cui una query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fosse insufficiente per un'attività specializzata, è possibile usare il metodo <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> per eseguire una query SQL, quindi convertire direttamente il risultato della query in oggetti.</span><span class="sxs-lookup"><span data-stu-id="72e6f-111">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72e6f-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="72e6f-112">Example</span></span>  
 <span data-ttu-id="72e6f-113">Nell'esempio seguente si supponga che i dati per la classe `Customer` siano distribuiti in due tabelle (customer1 e customer2).</span><span class="sxs-lookup"><span data-stu-id="72e6f-113">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="72e6f-114">La query consente di restituire una sequenza di oggetti `Customer`.</span><span class="sxs-lookup"><span data-stu-id="72e6f-114">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="72e6f-115">Finché i nomi di colonna nei risultati tabulari corrispondono alle proprietà di colonna della classe di entità, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea gli oggetti da qualsiasi query SQL.</span><span class="sxs-lookup"><span data-stu-id="72e6f-115">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72e6f-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="72e6f-116">Example</span></span>  
 <span data-ttu-id="72e6f-117">Il metodo <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> accetta anche parametri.</span><span class="sxs-lookup"><span data-stu-id="72e6f-117">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="72e6f-118">Per eseguire una query con parametri, usare codice analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="72e6f-118">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="72e6f-119">I parametri sono espressi nel testo della query usando la stessa notazione con parentesi graffe usata da `Console.WriteLine()` e `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="72e6f-119">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="72e6f-120">Infatti, `String.Format()` viene effettivamente chiamato sulla stringa di query fornita, sostituendo i parametri con parentesi graffe con i nomi di parametro generati, ad esempio @p0 , @p1 ..., @p (n).</span><span class="sxs-lookup"><span data-stu-id="72e6f-120">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72e6f-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72e6f-121">See also</span></span>

- [<span data-ttu-id="72e6f-122">Informazioni complementari</span><span class="sxs-lookup"><span data-stu-id="72e6f-122">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="72e6f-123">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="72e6f-123">Querying the Database</span></span>](querying-the-database.md)
