---
title: Introduzione a LINQ (C#)
ms.date: 07/20/2015
ms.assetid: 54874feb-55e5-4ca8-a9d6-1c1127fd7fb1
ms.openlocfilehash: b8a577c7f1cb89df5534ae0eca893f4db434301e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596581"
---
# <a name="introduction-to-linq-c"></a><span data-ttu-id="b3193-102">Introduzione a LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="b3193-102">Introduction to LINQ (C#)</span></span>
<span data-ttu-id="b3193-103">LINQ (Language-Integrated Query) rappresenta una novità introdotta in .NET Framework versione 3.5 che colma il divario tra il mondo degli oggetti e il mondo dei dati.</span><span class="sxs-lookup"><span data-stu-id="b3193-103">Language-Integrated Query (LINQ) is an innovation introduced in the .NET Framework version 3.5 that bridges the gap between the world of objects and the world of data.</span></span>  
  
 <span data-ttu-id="b3193-104">In genere, le query sui dati vengono espresse come stringhe semplici senza il controllo dei tipi in fase di compilazione o il supporto di IntelliSense.</span><span class="sxs-lookup"><span data-stu-id="b3193-104">Traditionally, queries against data are expressed as simple strings without type checking at compile time or IntelliSense support.</span></span> <span data-ttu-id="b3193-105">È anche necessario apprendere un linguaggio di query diverso per ogni tipo di origine dati: database SQL, documenti XML, vari servizi Web e così via.</span><span class="sxs-lookup"><span data-stu-id="b3193-105">Furthermore, you have to learn a different query language for each type of data source: SQL databases, XML documents, various Web services, and so on.</span></span> <span data-ttu-id="b3193-106">LINQ rende una *query* un costrutto di linguaggio di prima categoria in C#.</span><span class="sxs-lookup"><span data-stu-id="b3193-106">LINQ makes a *query* a first-class language construct in C#.</span></span> <span data-ttu-id="b3193-107">È possibile scrivere query su insiemi di oggetti fortemente tipizzati usando le parole chiave del linguaggio e gli operatori comuni.</span><span class="sxs-lookup"><span data-stu-id="b3193-107">You write queries against strongly typed collections of objects by using language keywords and familiar operators.</span></span>  
  
 <span data-ttu-id="b3193-108">È possibile scrivere query LINQ in C# per database SQL Server, documenti XML, set di dati ADO.NET e qualsiasi raccolta di oggetti che supporta <xref:System.Collections.IEnumerable> o l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> generica.</span><span class="sxs-lookup"><span data-stu-id="b3193-108">You can write LINQ queries in C# for SQL Server databases, XML documents, ADO.NET Datasets, and any collection of objects that supports <xref:System.Collections.IEnumerable> or the generic <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="b3193-109">Il supporto per LINQ viene anche offerto da terze parti per numerosi servizi Web e altre implementazioni di database.</span><span class="sxs-lookup"><span data-stu-id="b3193-109">LINQ support is also provided by third parties for many Web services and other database implementations.</span></span>  
  
 <span data-ttu-id="b3193-110">È possibile usare le query LINQ nei nuovi progetti o insieme alle query non LINQ nei progetti esistenti.</span><span class="sxs-lookup"><span data-stu-id="b3193-110">You can use LINQ queries in new projects, or alongside non-LINQ queries in existing projects.</span></span> <span data-ttu-id="b3193-111">L'unico requisito è che il progetto sia destinato a .NET Framework 3.5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="b3193-111">The only requirement is that the project target .NET Framework 3.5 or later.</span></span>  
  
 <span data-ttu-id="b3193-112">Nella figura seguente presa da Visual Studio viene illustrata una query LINQ completata parzialmente su un database di SQL Server in C# e Visual Basic con controllo completo del tipo e supporto IntelliSense:</span><span class="sxs-lookup"><span data-stu-id="b3193-112">The following illustration from Visual Studio shows a partially-completed LINQ query against a SQL Server database in both C# and Visual Basic with full type checking and IntelliSense support:</span></span>  
  
 ![Diagramma che illustra una query LINQ con Intellisense.](./media/introduction-to-linq/linq-query-intellisense.png)  
  
## <a name="next-steps"></a><span data-ttu-id="b3193-114">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="b3193-114">Next Steps</span></span>  
 <span data-ttu-id="b3193-115">Per altre informazioni dettagliate su LINQ, iniziare ad acquisire dimestichezza con alcuni concetti di base nella sezione introduttiva [Introduzione all'uso di LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md) e quindi leggere la documentazione per la tecnologia LINQ a cui si è interessati:</span><span class="sxs-lookup"><span data-stu-id="b3193-115">To learn more details about LINQ, start by becoming familiar with some basic concepts in the Getting Started section [Getting Started with LINQ in C#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md), and then read the documentation for the LINQ technology in which you are interested:</span></span>  
  
- <span data-ttu-id="b3193-116">Database SQL Server: [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)</span><span class="sxs-lookup"><span data-stu-id="b3193-116">SQL Server databases: [LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)</span></span>  
  
- <span data-ttu-id="b3193-117">Documenti XML: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="b3193-117">XML documents: [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)</span></span>  
  
- <span data-ttu-id="b3193-118">Set di dati ADO.NET: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span><span class="sxs-lookup"><span data-stu-id="b3193-118">ADO.NET Datasets: [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)</span></span>  
  
- <span data-ttu-id="b3193-119">Raccolte, file e stringhe .NET e così via: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span><span class="sxs-lookup"><span data-stu-id="b3193-119">.NET collections, files, strings and so on: [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3193-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b3193-120">See also</span></span>

- [<span data-ttu-id="b3193-121">Language-Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="b3193-121">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
