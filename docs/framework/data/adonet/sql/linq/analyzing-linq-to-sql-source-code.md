---
title: Analisi del codice sorgente in LINQ to SQL
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 01191e36c71b2f6ac9844f6af2d57b1cb3ed2573
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="a80cd-102">Analisi del codice sorgente in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="a80cd-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="a80cd-103">Usando i passaggi seguenti, è possibile produrre codice sorgente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="a80cd-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="a80cd-104">Gli elementi del modello a oggetti possono essere confrontati con gli elementi del database per verificare come viene eseguito il mapping dei diversi elementi.</span><span class="sxs-lookup"><span data-stu-id="a80cd-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a80cd-105">Gli sviluppatori che usano Visual Studio è possono utilizzare il [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] per produrre il codice.</span><span class="sxs-lookup"><span data-stu-id="a80cd-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to produce this code.</span></span>  
  
1.  <span data-ttu-id="a80cd-106">Se nel computer di sviluppo non è già disponibile il database di esempio Northwind, è possibile scaricarlo gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="a80cd-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="a80cd-107">Per ulteriori informazioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="a80cd-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2.  <span data-ttu-id="a80cd-108">Usare lo strumento della riga di comando SqlMetal per generare un file di origine di Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="a80cd-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="a80cd-109">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="a80cd-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="a80cd-110">Digitando i comandi seguenti al prompt dei comandi, è possibile generare file di origine di Visual Basic e C# contenenti stored procedure e funzioni:</span><span class="sxs-lookup"><span data-stu-id="a80cd-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="a80cd-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a80cd-111">See Also</span></span>  
 [<span data-ttu-id="a80cd-112">Riferimento</span><span class="sxs-lookup"><span data-stu-id="a80cd-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [<span data-ttu-id="a80cd-113">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="a80cd-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
