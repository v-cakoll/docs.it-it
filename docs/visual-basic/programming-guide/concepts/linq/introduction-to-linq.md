---
title: Introduzione a LINQ
ms.date: 07/20/2015
ms.assetid: c6339c12-9b2d-433e-961c-0d2b7f0091c2
ms.openlocfilehash: b0fa27fd81b85eb89712f9e81f42e06505878f86
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397558"
---
# <a name="introduction-to-linq-visual-basic"></a><span data-ttu-id="f0515-102">Introduzione a LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0515-102">Introduction to LINQ (Visual Basic)</span></span>
<span data-ttu-id="f0515-103">LINQ (Language-Integrated Query) rappresenta una novità introdotta in .NET Framework versione 3.5 che colma il divario tra il mondo degli oggetti e il mondo dei dati.</span><span class="sxs-lookup"><span data-stu-id="f0515-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="f0515-104">In genere, le query sui dati vengono espresse come stringhe semplici senza il controllo dei tipi in fase di compilazione o il supporto IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="f0515-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="f0515-105">È anche necessario imparare un linguaggio di query diverso per ogni tipo di origine dati: database SQL, documenti XML, svariati servizi Web e così via.</span><span class="sxs-lookup"><span data-stu-id="f0515-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="f0515-106">LINQ esegue una *query* in un costrutto di linguaggio di prima classe in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="f0515-106">LINQ makes a *query* a first-class language construct in Visual Basic.</span></span> <span data-ttu-id="f0515-107">È possibile scrivere query su insiemi di oggetti fortemente tipizzati usando le parole chiave del linguaggio e gli operatori comuni.</span><span class="sxs-lookup"><span data-stu-id="f0515-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="f0515-108">È possibile scrivere query LINQ in Visual Basic per database SQL Server, documenti XML, set di dati ADO.NET e qualsiasi raccolta di oggetti che supporta <xref:System.Collections.IEnumerable> o l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601> .</span><span class="sxs-lookup"><span data-stu-id="f0515-108">You can write LINQ queries in Visual Basic for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="f0515-109">Il supporto per LINQ viene anche offerto da terze parti per numerosi servizi Web e altre implementazioni di database.</span><span class="sxs-lookup"><span data-stu-id="f0515-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="f0515-110">È possibile usare le query LINQ nei nuovi progetti o insieme alle query non LINQ nei progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="f0515-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="f0515-111">L'unico requisito è che il progetto sia destinato a .NET Framework 3.5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="f0515-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="f0515-112">Nella figura seguente presa da Visual Studio viene illustrata una query LINQ parzialmente completata per un database di SQL Server in C# e Visual Basic con controllo completo del tipo e supporto IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="f0515-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support.</span></span>  
  
 ![Diagramma che illustra una query LINQ con Intellisense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="f0515-114">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="f0515-114">Next Steps</span></span>  
 <span data-ttu-id="f0515-115">Per ulteriori informazioni su LINQ, iniziare acquisendo familiarità con alcuni concetti di base nella sezione Introduzione [Introduzione con LINQ in Visual Basic](getting-started-with-linq.md), quindi leggere la documentazione per la tecnologia LINQ a cui si è interessati:</span><span class="sxs-lookup"><span data-stu-id="f0515-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in Visual Basic](getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
- <span data-ttu-id="f0515-116">Database SQL Server: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="f0515-116">SQL Server databases: [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)</span></span>  
  
- <span data-ttu-id="f0515-117">Documenti XML: [LINQ to XML (Visual Basic)](linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="f0515-117">XML documents: [LINQ to XML (Visual Basic)](linq-to-xml.md)</span></span>  
  
- <span data-ttu-id="f0515-118">Set di dati ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="f0515-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
- <span data-ttu-id="f0515-119">Raccolte .NET, file, stringhe e così via: [LINQ to Objects (Visual Basic)](linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="f0515-119">.NET collections, files, strings and so on: [LINQ to Objects (Visual Basic)](linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0515-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f0515-120">See also</span></span>

- [<span data-ttu-id="f0515-121">LINQ (Language-Integrated Query) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0515-121">Language-Integrated Query (LINQ) (Visual Basic)</span></span>](index.md)
