---
title: 'Procedura: generare codice personalizzato modificando un file DBML'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 743e938df0b9c7f12a9c3a11a4b5558137add529
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="b18e3-102">Procedura: generare codice personalizzato modificando un file DBML</span><span class="sxs-lookup"><span data-stu-id="b18e3-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="b18e3-103">È possibile generare [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o il codice sorgente c# da un file di metadati di database markup language (. dbml).</span><span class="sxs-lookup"><span data-stu-id="b18e3-103">You can generate [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="b18e3-104">Questo approccio consente di personalizzare il file DBML predefinito prima di generare il codice di mapping dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b18e3-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="b18e3-105">Si tratta di una funzionalità avanzata.</span><span class="sxs-lookup"><span data-stu-id="b18e3-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="b18e3-106">Di seguito sono elencati i passaggi di questo processo.</span><span class="sxs-lookup"><span data-stu-id="b18e3-106">The steps in this process are as follows:</span></span>  
  
1.  <span data-ttu-id="b18e3-107">Generare un file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="b18e3-107">Generate a .dbml file.</span></span>  
  
2.  <span data-ttu-id="b18e3-108">Usare un editor per modificare il file con estensione dbml,</span><span class="sxs-lookup"><span data-stu-id="b18e3-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="b18e3-109">Si noti che il file. dbml deve convalidare il file di schema definition (XSD) per [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] file. dbml.</span><span class="sxs-lookup"><span data-stu-id="b18e3-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="b18e3-110">Per ulteriori informazioni, vedere [generazione di codice in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="b18e3-110">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
3.  <span data-ttu-id="b18e3-111">Generare il codice sorgente [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o C#.</span><span class="sxs-lookup"><span data-stu-id="b18e3-111">Generate the [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code.</span></span>  
  
 <span data-ttu-id="b18e3-112">Negli esempi seguenti viene usato lo strumento della riga di comando SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="b18e3-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="b18e3-113">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="b18e3-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b18e3-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="b18e3-114">Example</span></span>  
 <span data-ttu-id="b18e3-115">Nel codice seguente viene generato un file con estensione dbml dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="b18e3-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="b18e3-116">Come origine per i metadati del database è possibile usare il nome del database o il nome del file con estensione mdf.</span><span class="sxs-lookup"><span data-stu-id="b18e3-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="b18e3-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="b18e3-117">Example</span></span>  
 <span data-ttu-id="b18e3-118">Nel codice seguente viene generato file di codice sorgente [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o C# da un file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="b18e3-118">The following code generates [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code file from a .dbml file.</span></span>  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="b18e3-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b18e3-119">See Also</span></span>  
 [<span data-ttu-id="b18e3-120">Generazione di codice in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="b18e3-120">Code Generation in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="b18e3-121">SqlMetal.exe (strumento per la generazione del codice)</span><span class="sxs-lookup"><span data-stu-id="b18e3-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [<span data-ttu-id="b18e3-122">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="b18e3-122">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
