---
title: 'Procedura: Eseguire direttamente query SQL'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
ms.openlocfilehash: a4971bc05b22c38790c5fd1493e70cccf5eaae16
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793790"
---
# <a name="how-to-directly-execute-sql-queries"></a><span data-ttu-id="d5eda-102">Procedura: Eseguire direttamente query SQL</span><span class="sxs-lookup"><span data-stu-id="d5eda-102">How to: Directly Execute SQL Queries</span></span>
<span data-ttu-id="d5eda-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query create vengono convertite in query SQL con parametri, in formato testo, e inviate al server SQL per l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="d5eda-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates the queries you write into parameterized SQL queries (in text form) and sends them to the SQL server for processing.</span></span>  
  
 <span data-ttu-id="d5eda-104">Non è possibile eseguire in SQL la varietà di metodi eventualmente disponibili localmente per l'applicazione,</span><span class="sxs-lookup"><span data-stu-id="d5eda-104">SQL cannot execute the variety of methods that might be locally available to your application.</span></span> <span data-ttu-id="d5eda-105">pertanto [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tenta di convertire questi metodi locali nelle operazioni e funzioni equivalenti disponibili nell'ambiente SQL.</span><span class="sxs-lookup"><span data-stu-id="d5eda-105">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] tries to convert these local methods to equivalent operations and functions that are available inside the SQL environment.</span></span> <span data-ttu-id="d5eda-106">La maggior parte dei metodi e degli operatori nei tipi incorporati .NET Framework dispone di traduzioni dirette nei comandi SQL.</span><span class="sxs-lookup"><span data-stu-id="d5eda-106">Most methods and operators on .NET Framework built-in types have direct translations to SQL commands.</span></span> <span data-ttu-id="d5eda-107">Alcuni possono essere prodotti dalle funzioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="d5eda-107">Some can be produced from the functions that are available.</span></span> <span data-ttu-id="d5eda-108">Quelli che non possono essere prodotti generano eccezioni in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="d5eda-108">Those that cannot be produced generate run-time exceptions.</span></span> <span data-ttu-id="d5eda-109">Per ulteriori informazioni, vedere [mapping dei tipi SQL-CLR](sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="d5eda-109">For more information, see [SQL-CLR Type Mapping](sql-clr-type-mapping.md).</span></span>  
  
 <span data-ttu-id="d5eda-110">Nei casi in cui una query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fosse insufficiente per un'attività specializzata, è possibile usare il metodo <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> per eseguire una query SQL, quindi convertire direttamente il risultato della query in oggetti.</span><span class="sxs-lookup"><span data-stu-id="d5eda-110">In cases where a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query is insufficient for a specialized task, you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to execute a SQL query, and then convert the result of your query directly into objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5eda-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5eda-111">Example</span></span>  
 <span data-ttu-id="d5eda-112">Nell'esempio seguente si supponga che i dati per la classe `Customer` siano distribuiti in due tabelle (customer1 e customer2).</span><span class="sxs-lookup"><span data-stu-id="d5eda-112">In the following example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="d5eda-113">La query consente di restituire una sequenza di oggetti `Customer`.</span><span class="sxs-lookup"><span data-stu-id="d5eda-113">The query returns a sequence of `Customer` objects.</span></span>  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 <span data-ttu-id="d5eda-114">Finché i nomi di colonna nei risultati tabulari corrispondono alle proprietà di colonna della classe di entità [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , crea gli oggetti da qualsiasi query SQL.</span><span class="sxs-lookup"><span data-stu-id="d5eda-114">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5eda-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5eda-115">Example</span></span>  
 <span data-ttu-id="d5eda-116">Il metodo <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> accetta anche parametri.</span><span class="sxs-lookup"><span data-stu-id="d5eda-116">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method also allows for parameters.</span></span> <span data-ttu-id="d5eda-117">Per eseguire una query con parametri, usare codice analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="d5eda-117">Use code such as the following to execute a parameterized query.</span></span>  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 <span data-ttu-id="d5eda-118">I parametri sono espressi nel testo della query usando la stessa notazione con parentesi graffe usata da `Console.WriteLine()` e `String.Format()`.</span><span class="sxs-lookup"><span data-stu-id="d5eda-118">The parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="d5eda-119">Infatti, `String.Format()` viene effettivamente chiamato sulla stringa di query fornita, sostituendo i parametri con parentesi graffe con i nomi di parametro generati, @p0ad esempio @p1 ,... @p, (n).</span><span class="sxs-lookup"><span data-stu-id="d5eda-119">In fact, `String.Format()` is actually called on the query string you provide, substituting the curly braced parameters with generated parameter names such as @p0, @p1 …, @p(n).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5eda-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5eda-120">See also</span></span>

- [<span data-ttu-id="d5eda-121">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="d5eda-121">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="d5eda-122">Esecuzione di query sul database</span><span class="sxs-lookup"><span data-stu-id="d5eda-122">Querying the Database</span></span>](querying-the-database.md)
