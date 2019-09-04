---
title: Analisi del codice sorgente in LINQ to SQL
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: dda19800a9aea0d644740c5378f6d5065181993e
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248074"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="2daa5-102">Analisi del codice sorgente in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2daa5-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="2daa5-103">Usando i passaggi seguenti, è possibile produrre codice sorgente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="2daa5-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="2daa5-104">Gli elementi del modello a oggetti possono essere confrontati con gli elementi del database per verificare come viene eseguito il mapping dei diversi elementi.</span><span class="sxs-lookup"><span data-stu-id="2daa5-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2daa5-105">Gli sviluppatori che usano Visual Studio possono usare la finestra di progettazione relazionale oggetti per produrre questo codice.</span><span class="sxs-lookup"><span data-stu-id="2daa5-105">Developers using Visual Studio can use the O/R Designer to produce this code.</span></span>  
  
1. <span data-ttu-id="2daa5-106">Se nel computer di sviluppo non è già disponibile il database di esempio Northwind, è possibile scaricarlo gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="2daa5-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="2daa5-107">Per ulteriori informazioni, vedere [download di database di esempio](downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2daa5-107">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
2. <span data-ttu-id="2daa5-108">Usare lo strumento della riga di comando SqlMetal per generare un file di origine di Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="2daa5-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="2daa5-109">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2daa5-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="2daa5-110">Digitando i comandi seguenti al prompt dei comandi, è possibile generare file di origine di Visual Basic e C# contenenti stored procedure e funzioni:</span><span class="sxs-lookup"><span data-stu-id="2daa5-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    - `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    - `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="2daa5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2daa5-111">See also</span></span>

- [<span data-ttu-id="2daa5-112">Riferimento</span><span class="sxs-lookup"><span data-stu-id="2daa5-112">Reference</span></span>](reference.md)
- [<span data-ttu-id="2daa5-113">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="2daa5-113">Background Information</span></span>](background-information.md)
