---
title: Analisi del codice sorgente in LINQ to SQL
ms.date: 03/30/2017
ms.assetid: cba3eef8-e108-4478-b588-ad59580e133e
ms.openlocfilehash: 1110e64d16a6c2790939cc695ecd67e37ec109e4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203288"
---
# <a name="analyzing-linq-to-sql-source-code"></a><span data-ttu-id="2e620-102">Analisi del codice sorgente in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="2e620-102">Analyzing LINQ to SQL Source Code</span></span>
<span data-ttu-id="2e620-103">Usando i passaggi seguenti, è possibile produrre codice sorgente [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="2e620-103">By using the following steps, you can produce [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] source code from the Northwind sample database.</span></span> <span data-ttu-id="2e620-104">Gli elementi del modello a oggetti possono essere confrontati con gli elementi del database per verificare come viene eseguito il mapping dei diversi elementi.</span><span class="sxs-lookup"><span data-stu-id="2e620-104">You can compare elements of the object model with elements of the database to better see how different items are mapped.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e620-105">Gli sviluppatori che usano Visual Studio è possono usare il [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] per produrre il codice.</span><span class="sxs-lookup"><span data-stu-id="2e620-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] to produce this code.</span></span>  
  
1.  <span data-ttu-id="2e620-106">Se nel computer di sviluppo non è già disponibile il database di esempio Northwind, è possibile scaricarlo gratuitamente.</span><span class="sxs-lookup"><span data-stu-id="2e620-106">If you do not already have the Northwind sample database on your development computer, you can download it free of charge.</span></span> <span data-ttu-id="2e620-107">Per altre informazioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="2e620-107">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
2.  <span data-ttu-id="2e620-108">Usare lo strumento della riga di comando SqlMetal per generare un file di origine di Visual Basic o C#.</span><span class="sxs-lookup"><span data-stu-id="2e620-108">Use the SqlMetal command-line tool to generate a Visual Basic or C# source file.</span></span> <span data-ttu-id="2e620-109">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="2e620-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span> <span data-ttu-id="2e620-110">Digitando i comandi seguenti al prompt dei comandi, è possibile generare file di origine di Visual Basic e C# contenenti stored procedure e funzioni:</span><span class="sxs-lookup"><span data-stu-id="2e620-110">By typing the following commands at a command prompt, you can generate Visual Basic and C# source files that include stored procedures and functions:</span></span>  
  
    -   `sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
    -   `sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize`  
  
## <a name="see-also"></a><span data-ttu-id="2e620-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e620-111">See also</span></span>

- [<span data-ttu-id="2e620-112">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="2e620-112">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
- [<span data-ttu-id="2e620-113">Informazioni di base</span><span class="sxs-lookup"><span data-stu-id="2e620-113">Background Information</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
