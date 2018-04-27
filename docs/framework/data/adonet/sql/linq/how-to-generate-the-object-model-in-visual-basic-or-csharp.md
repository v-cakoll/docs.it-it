---
title: 'Procedura: generare il modello a oggetti in Visual Basic o C#'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
caps.latest.revision: 3
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 77d7020a985abb8ed56af4fdd9f50a98bfc478c4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="10fc7-102">Procedura: generare il modello a oggetti in Visual Basic o C#</span><span class="sxs-lookup"><span data-stu-id="10fc7-102">How to: Generate the Object Model in Visual Basic or C#</span></span> #
<span data-ttu-id="10fc7-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping di un modello a oggetti nel linguaggio di programmazione in uso a un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="10fc7-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="10fc7-104">Due strumenti sono disponibili per la generazione automatica di un modello di Visual Basic o c# dai metadati di un database esistente.</span><span class="sxs-lookup"><span data-stu-id="10fc7-104">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
-   <span data-ttu-id="10fc7-105">Se si utilizza Visual Studio, è possibile utilizzare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per generare un modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="10fc7-105">If you are using Visual Studio, you can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to generate an object model.</span></span> <span data-ttu-id="10fc7-106">Il [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] fornisce un'interfaccia utente avanzata che consente di generare un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="10fc7-106">The [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="10fc7-107">Per ulteriori informazioni, vedere [Linq to SQL Tools in Visual Studio](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="10fc7-107">For more information see, [Linq to SQL Tools in Visual Studio](https://docs.microsoft.com/en-us/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
-   <span data-ttu-id="10fc7-108">Lo strumento della riga di comando SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="10fc7-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="10fc7-109">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="10fc7-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="10fc7-110">Se non si dispone di un database esistente e si desidera crearne uno da un modello a oggetti, è possibile creare il modello a oggetti usando l'editor di codice e <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span><span class="sxs-lookup"><span data-stu-id="10fc7-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="10fc7-111">Per ulteriori informazioni, vedere [procedura: creazione di un Database in modo dinamico](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="10fc7-111">For more information, see [How to: Dynamically Create a Database](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="10fc7-112">Documentazione per il [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] vengono forniti esempi di come generare un modello a oggetti Visual Basic o c# usando il [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="10fc7-112">Documentation for the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] provides examples of how to generate a Visual Basic or C# object model by using the [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)].</span></span> <span data-ttu-id="10fc7-113">Le informazioni seguenti forniscono esempi relativi all'uso dello strumento della riga di comando SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="10fc7-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="10fc7-114">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="10fc7-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10fc7-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="10fc7-115">Example</span></span>  
 <span data-ttu-id="10fc7-116">Riga di comando SQLMetal mostrata nell'esempio seguente produce codice Visual Basic come modello a oggetti basato su attributi di database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="10fc7-116">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="10fc7-117">Viene eseguito il rendering anche di stored procedure e funzioni.</span><span class="sxs-lookup"><span data-stu-id="10fc7-117">Stored procedures and functions are also rendered.</span></span>  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="10fc7-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="10fc7-118">Example</span></span>  
 <span data-ttu-id="10fc7-119">Usando la riga di comando SQLMetal riportata nell'esempio è possibile produrre codice C# come modello a oggetti basato su attributi del database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="10fc7-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="10fc7-120">Viene eseguito il rendering anche di stored procedure e funzioni, mentre i nomi delle tabelle vengono pluralizzati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="10fc7-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="10fc7-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10fc7-121">See Also</span></span>  
 [<span data-ttu-id="10fc7-122">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="10fc7-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 [<span data-ttu-id="10fc7-123">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="10fc7-123">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)  
 [<span data-ttu-id="10fc7-124">Apprendimento tramite procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="10fc7-124">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)  
 [<span data-ttu-id="10fc7-125">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="10fc7-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 [<span data-ttu-id="10fc7-126">Mapping basato su attributi</span><span class="sxs-lookup"><span data-stu-id="10fc7-126">Attribute-Based Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)  
 [<span data-ttu-id="10fc7-127">SqlMetal.exe (strumento per la generazione del codice)</span><span class="sxs-lookup"><span data-stu-id="10fc7-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 <span data-ttu-id="10fc7-128">[External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md) (Mapping esterno)</span><span class="sxs-lookup"><span data-stu-id="10fc7-128">[External Mapping](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)</span></span>  
 [<span data-ttu-id="10fc7-129">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="10fc7-129">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 [<span data-ttu-id="10fc7-130">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="10fc7-130">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
