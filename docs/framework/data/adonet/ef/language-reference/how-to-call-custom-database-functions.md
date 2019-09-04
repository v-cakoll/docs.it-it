---
title: 'Procedura: Chiamare funzioni di database personalizzate'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4354e5eb-dd45-469d-97fb-1c495705ee59
ms.openlocfilehash: b7f483d8dc7c6d0160ec211140726c9d732f0268
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250802"
---
# <a name="how-to-call-custom-database-functions"></a><span data-ttu-id="b7faa-102">Procedura: Chiamare funzioni di database personalizzate</span><span class="sxs-lookup"><span data-stu-id="b7faa-102">How to: Call Custom Database Functions</span></span>
<span data-ttu-id="b7faa-103">In questo argomento viene descritto come chiamare funzioni personalizzate definite nel database dall'interno di query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="b7faa-103">This topic describes how to call custom functions that are defined in the database from within LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="b7faa-104">Le funzioni di database che sono chiamate dalle query LINQ to Entities vengono eseguite nel database.</span><span class="sxs-lookup"><span data-stu-id="b7faa-104">Database functions that are called from LINQ to Entities queries are executed in the database.</span></span> <span data-ttu-id="b7faa-105">L'esecuzione di funzioni nel database può migliorare le prestazioni dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b7faa-105">Executing functions in the database can improve application performance.</span></span>  
  
 <span data-ttu-id="b7faa-106">La procedura descritta di seguito fornisce una struttura di alto livello per la chiamata di una funzione di database personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b7faa-106">The procedure below provides a high-level outline for calling a custom database function.</span></span> <span data-ttu-id="b7faa-107">Nell'esempio che segue vengono forniti dettagli aggiuntivi sui passaggi della procedura.</span><span class="sxs-lookup"><span data-stu-id="b7faa-107">The example that follows provides more detail about the steps in the procedure.</span></span>  
  
### <a name="to-call-custom-functions-that-are-defined-in-the-database"></a><span data-ttu-id="b7faa-108">Per chiamare funzioni personalizzate definite nel database</span><span class="sxs-lookup"><span data-stu-id="b7faa-108">To call custom functions that are defined in the database</span></span>  
  
1. <span data-ttu-id="b7faa-109">Creare una funzione personalizzata nel database.</span><span class="sxs-lookup"><span data-stu-id="b7faa-109">Create a custom function in your database.</span></span>  
  
     <span data-ttu-id="b7faa-110">Per ulteriori informazioni sulla creazione di funzioni personalizzate in SQL Server, vedere [create function (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span><span class="sxs-lookup"><span data-stu-id="b7faa-110">For more information about creating custom functions in SQL Server, see [CREATE FUNCTION (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkID=139871).</span></span>  
  
2. <span data-ttu-id="b7faa-111">Dichiarare una funzione nel linguaggio Store Schema Definition Language (SSDL) del file .edmx.</span><span class="sxs-lookup"><span data-stu-id="b7faa-111">Declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="b7faa-112">Il nome della funzione deve essere identico a quello della funzione dichiarata nel database.</span><span class="sxs-lookup"><span data-stu-id="b7faa-112">The name of the function must be the same as the name of the function declared in the database.</span></span>  
  
     <span data-ttu-id="b7faa-113">Per ulteriori informazioni, vedere [elemento Function (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span><span class="sxs-lookup"><span data-stu-id="b7faa-113">For more information, see [Function Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#function-element-ssdl).</span></span>  
  
3. <span data-ttu-id="b7faa-114">Aggiungere un metodo corrispondente a una classe nel codice dell'applicazione e applicare un <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> al metodo. Si noti che i parametri <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> e <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> dell'attributo sono rispettivamente il nome dello spazio dei nomi del modello concettuale e il nome della funzione nel modello concettuale.</span><span class="sxs-lookup"><span data-stu-id="b7faa-114">Add a corresponding method to a class in your application code and apply a <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute> to the method Note that the <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.NamespaceName%2A> and <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute.FunctionName%2A> parameters of the attribute are the namespace name of the conceptual model and the function name in the conceptual model respectively.</span></span> <span data-ttu-id="b7faa-115">La risoluzione del nome della funzione per LINQ rileva la distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="b7faa-115">Function name resolution for LINQ is case sensitive.</span></span>  
  
4. <span data-ttu-id="b7faa-116">Chiamare il metodo in una query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="b7faa-116">Call the method in a LINQ to Entities query.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7faa-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7faa-117">Example</span></span>  
 <span data-ttu-id="b7faa-118">Nell'esempio seguente viene mostrato come chiamare una funzione di database personalizzata dall'interno una query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="b7faa-118">The following example demonstrates how to call a custom database function from within a LINQ to Entities query.</span></span> <span data-ttu-id="b7faa-119">Nell'esempio viene usato il modello School.</span><span class="sxs-lookup"><span data-stu-id="b7faa-119">The example uses the School model.</span></span> <span data-ttu-id="b7faa-120">Per informazioni sul modello School, vedere [creazione del database di esempio School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) e [generazione del file School. edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b7faa-120">For information about the School model, see [Creating the School Sample Database](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)) and [Generating the School .edmx File](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399739(v=vs.100)).</span></span>  
  
 <span data-ttu-id="b7faa-121">Nel codice seguente viene aggiunta la funzione `AvgStudentGrade` al database di esempio School.</span><span class="sxs-lookup"><span data-stu-id="b7faa-121">The following code adds the `AvgStudentGrade` function to the School sample database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7faa-122">I passaggi per la chiamata di una funzione di database personalizzata sono gli stessi indipendentemente dal server database.</span><span class="sxs-lookup"><span data-stu-id="b7faa-122">The steps for calling a custom database function are the same regardless of the database server.</span></span> <span data-ttu-id="b7faa-123">Tuttavia, il codice seguente è specifico per la creazione di una funzione in un database SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b7faa-123">However, the code below is specific to creating a function in a SQL Server database.</span></span> <span data-ttu-id="b7faa-124">Il codice per la creazione di una funzione personalizzata in altri server database potrebbe essere differente.</span><span class="sxs-lookup"><span data-stu-id="b7faa-124">The code for creating a custom function in other database servers might differ.</span></span>  
  
 [!code-sql[DP L2E MapToDBFunction#1](../../../../../../samples/snippets/tsql/VS_Snippets_Data/dp l2e maptodbfunction/tsql/create_avgstudentgrade.sql#1)]  
  
## <a name="example"></a><span data-ttu-id="b7faa-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7faa-125">Example</span></span>  
 <span data-ttu-id="b7faa-126">Dichiarare una funzione nel linguaggio Store Schema Definition Language (SSDL) del file .edmx.</span><span class="sxs-lookup"><span data-stu-id="b7faa-126">Next, declare a function in the store schema definition language (SSDL) of your .edmx file.</span></span> <span data-ttu-id="b7faa-127">Nel codice seguente viene dichiarata la funzione `AvgStudentGrade` in SSDL:</span><span class="sxs-lookup"><span data-stu-id="b7faa-127">the following code declares the `AvgStudentGrade` function in SSDL:</span></span>  
  
 [!code-xml[DP L2E MapToDBFunction#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/school.edmx#2)]  
  
## <a name="example"></a><span data-ttu-id="b7faa-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7faa-128">Example</span></span>  
 <span data-ttu-id="b7faa-129">A questo punto creare un metodo ed eseguirne il mapping alla funzione dichiarata in SSDL.</span><span class="sxs-lookup"><span data-stu-id="b7faa-129">Now create a method and map it to the function declared in the SSDL.</span></span> <span data-ttu-id="b7faa-130">Il metodo nella classe seguente viene mappato alla funzione definita in SSDL (sopra) tramite un oggetto <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="b7faa-130">The method in the following class is mapped to the function defined in the SSDL (above) by using an <xref:System.Data.Objects.DataClasses.EdmFunctionAttribute>.</span></span> <span data-ttu-id="b7faa-131">Quando il metodo viene chiamato, viene eseguita la funzione corrispondente nel database.</span><span class="sxs-lookup"><span data-stu-id="b7faa-131">When this method is called, the corresponding function in the database is executed.</span></span>  
  
 [!code-csharp[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#3)]
 [!code-vb[DP L2E MapToDBFunction#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="b7faa-132">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7faa-132">Example</span></span>  
 <span data-ttu-id="b7faa-133">Chiamare infine il metodo in una query LINQ to Entities.</span><span class="sxs-lookup"><span data-stu-id="b7faa-133">Finally, call the method in a LINQ to Entities query.</span></span> <span data-ttu-id="b7faa-134">Nel codice seguente vengono visualizzati i cognomi di studenti e le medie dei voti alla console:</span><span class="sxs-lookup"><span data-stu-id="b7faa-134">The following code displays students' last names and average grades to the console:</span></span>  
  
 [!code-csharp[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e maptodbfunction/cs/program.cs#4)]
 [!code-vb[DP L2E MapToDBFunction#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e maptodbfunction/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="b7faa-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7faa-135">See also</span></span>

- <span data-ttu-id="b7faa-136">[Panoramica del file con estensione edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b7faa-136">[.edmx File Overview](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))</span></span>
- [<span data-ttu-id="b7faa-137">Query in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b7faa-137">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
