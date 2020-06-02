---
title: 'Procedura: connettersi a un database'
description: Informazioni su come usare DataContext per connettersi a un database di in LINQ to SQL. Vedere questi esempi per usare DataContext per connettersi a un database e ottenere le righe.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: c3320a598cb8407ab584530c615c2e5ef0de53c8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286404"
---
# <a name="how-to-connect-to-a-database"></a><span data-ttu-id="c8bd9-104">Procedura: connettersi a un database</span><span class="sxs-lookup"><span data-stu-id="c8bd9-104">How to: Connect to a Database</span></span>
<span data-ttu-id="c8bd9-105"><xref:System.Data.Linq.DataContext> funge da canale principale per la connessione a un database, il recupero degli oggetti e l'invio delle modifiche.</span><span class="sxs-lookup"><span data-stu-id="c8bd9-105">The <xref:System.Data.Linq.DataContext> is the main conduit by which you connect to a database, retrieve objects from it, and submit changes back to it.</span></span> <span data-ttu-id="c8bd9-106">Usare il <xref:System.Data.Linq.DataContext> proprio come si farebbe con un ADO.NET <xref:System.Data.SqlClient.SqlConnection> .</span><span class="sxs-lookup"><span data-stu-id="c8bd9-106">You use the <xref:System.Data.Linq.DataContext> just as you would use an ADO.NET <xref:System.Data.SqlClient.SqlConnection>.</span></span> <span data-ttu-id="c8bd9-107">L'inizializzazione di <xref:System.Data.Linq.DataContext>, infatti, viene effettuata con una connessione o una stringa di connessione specificata.</span><span class="sxs-lookup"><span data-stu-id="c8bd9-107">In fact, the <xref:System.Data.Linq.DataContext> is initialized with a connection or connection string that you supply.</span></span> <span data-ttu-id="c8bd9-108">Per altre informazioni, vedere [metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span><span class="sxs-lookup"><span data-stu-id="c8bd9-108">For more information, see [DataContext Methods (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).</span></span>  
  
 <span data-ttu-id="c8bd9-109">Lo scopo di <xref:System.Data.Linq.DataContext> consiste nel convertire le richieste di oggetti in query SQL da eseguire sul database, quindi di assemblare gli oggetti dai risultati.</span><span class="sxs-lookup"><span data-stu-id="c8bd9-109">The purpose of the <xref:System.Data.Linq.DataContext> is to translate your requests for objects into SQL queries to be made against the database, and then to assemble objects out of the results.</span></span> <span data-ttu-id="c8bd9-110"><xref:System.Data.Linq.DataContext>Abilita LINQ (Language-Integrated Query) implementando lo stesso modello di operatore degli operatori di query standard, ad esempio `Where` e `Select` .</span><span class="sxs-lookup"><span data-stu-id="c8bd9-110">The <xref:System.Data.Linq.DataContext> enables Language-Integrated Query (LINQ) by implementing the same operator pattern as the Standard Query Operators, such as `Where` and `Select`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c8bd9-111">La gestione di una connessione sicura è della massima importanza.</span><span class="sxs-lookup"><span data-stu-id="c8bd9-111">Maintaining a secure connection is of the highest importance.</span></span> <span data-ttu-id="c8bd9-112">Per ulteriori informazioni, vedere [sicurezza in LINQ to SQL](security-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c8bd9-112">For more information, see [Security in LINQ to SQL](security-in-linq-to-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8bd9-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8bd9-113">Example</span></span>  
 <span data-ttu-id="c8bd9-114">Nell'esempio seguente viene usato <xref:System.Data.Linq.DataContext> per effettuare la connessione al database di esempio Northwind e recuperare le righe dei clienti la cui città di residenza è London.</span><span class="sxs-lookup"><span data-stu-id="c8bd9-114">In the following example, the <xref:System.Data.Linq.DataContext> is used to connect to the Northwind sample database and to retrieve rows of customers whose city is London.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 <span data-ttu-id="c8bd9-115">Ogni tabella di database è rappresentata come una raccolta `Table` disponibile tramite il metodo <xref:System.Data.Linq.DataContext.GetTable%2A> usando la classe di entità per identificarlo.</span><span class="sxs-lookup"><span data-stu-id="c8bd9-115">Each database table is represented as a `Table` collection available by way of the <xref:System.Data.Linq.DataContext.GetTable%2A> method, by using the entity class to identify it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8bd9-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="c8bd9-116">Example</span></span>  
 <span data-ttu-id="c8bd9-117">La procedura consigliata consiste nel dichiarare <xref:System.Data.Linq.DataContext> con una tipizzazione forte anziché basarsi sulla classe <xref:System.Data.Linq.DataContext> di base e sul metodo <xref:System.Data.Linq.DataContext.GetTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="c8bd9-117">Best practice is to declare a strongly typed <xref:System.Data.Linq.DataContext> instead of relying on the basic <xref:System.Data.Linq.DataContext> class and the <xref:System.Data.Linq.DataContext.GetTable%2A> method.</span></span> <span data-ttu-id="c8bd9-118">La tipizzazione forte di<xref:System.Data.Linq.DataContext> consente di dichiarare tutte le raccolte `Table` come membri del contesto, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="c8bd9-118">A strongly typed <xref:System.Data.Linq.DataContext> declares all `Table` collections as members of the context, as in the following example.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 <span data-ttu-id="c8bd9-119">È quindi possibile esprimere la query per i clienti dell'area londinese come:</span><span class="sxs-lookup"><span data-stu-id="c8bd9-119">You can then express the query for customers from London more simply as:</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="c8bd9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8bd9-120">See also</span></span>

- [<span data-ttu-id="c8bd9-121">Comunicazione con il database</span><span class="sxs-lookup"><span data-stu-id="c8bd9-121">Communicating with the Database</span></span>](communicating-with-the-database.md)
