---
title: Introduzione a LINQ (Visual Basic)
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: 2900cade8bc4166cccb62baf4381cb926cdff5f8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58822323"
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="3ea10-102">Introduzione a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ea10-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="3ea10-103">LINQ (Language-Integrated Query) rappresenta una novità introdotta in .NET Framework versione 3.5 che colma il divario tra il mondo degli oggetti e il mondo dei dati.</span><span class="sxs-lookup"><span data-stu-id="3ea10-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="3ea10-104">In genere, le query sui dati vengono espresse come stringhe semplici senza il controllo dei tipi in fase di compilazione o il supporto di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="3ea10-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="3ea10-105">È anche necessario apprendere un linguaggio di query diverso per ogni tipo di origine dati: database SQL, documenti XML, vari servizi Web e così via.</span><span class="sxs-lookup"><span data-stu-id="3ea10-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="3ea10-106">LINQ rende una *query* un costrutto di linguaggio di prima classe in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="3ea10-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="3ea10-107">È possibile scrivere query su insiemi di oggetti fortemente tipizzati usando le parole chiave del linguaggio e gli operatori comuni.</span><span class="sxs-lookup"><span data-stu-id="3ea10-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="3ea10-108">È possibile scrivere query LINQ in Visual Basic per database SQL Server, documenti XML, i dataset ADO.NET e qualsiasi raccolta di oggetti che supporta <xref:System.Collections.IEnumerable> o il generico <xref:System.Collections.Generic.IEnumerable%601> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="3ea10-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="3ea10-109">Il supporto per LINQ viene anche offerto da terze parti per numerosi servizi Web e altre implementazioni di database.</span><span class="sxs-lookup"><span data-stu-id="3ea10-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="3ea10-110">È possibile usare le query LINQ nei nuovi progetti o insieme alle query non LINQ nei progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="3ea10-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="3ea10-111">L'unico requisito è che il progetto sia destinato a .NET Framework 3.5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="3ea10-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="3ea10-112">Nella figura seguente presa da Visual Studio viene illustrata una query LINQ parzialmente completata per un database di SQL Server in C# e Visual Basic con controllo completo del tipo e supporto IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="3ea10-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 ![Diagramma che shwos una query LINQ con Intellisense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="3ea10-114">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="3ea10-114">Next Steps</span></span>  
 <span data-ttu-id="3ea10-115">Per altre informazioni dettagliate su LINQ, iniziare ad acquisire dimestichezza con alcuni concetti di base nella sezione attività iniziali [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), e quindi leggere la documentazione per la tecnologia LINQ a cui si è sei interessato:</span><span class="sxs-lookup"><span data-stu-id="3ea10-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
-   <span data-ttu-id="3ea10-116">Database SQL Server: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="3ea10-116">SQL Server databases: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span></span>  
  
-   <span data-ttu-id="3ea10-117">Documenti XML: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="3ea10-117">XML documents: [LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
-   <span data-ttu-id="3ea10-118">Set di dati ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="3ea10-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
-   <span data-ttu-id="3ea10-119">Raccolte, file e stringhe .NET e così via: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="3ea10-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ea10-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3ea10-120">See also</span></span>

- [<span data-ttu-id="3ea10-121">LINQ (Language-Integrated Query) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ea10-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/index.md)
