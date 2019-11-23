---
title: 'Procedura: generare il modello a oggetti in Visual Basic o C#'
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 7d2c0600534c93f5884eec48a4bdaa3ce99945e9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002811"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a><span data-ttu-id="970df-102">Procedura: generare il modello a oggetti in Visual Basic o C\#</span><span class="sxs-lookup"><span data-stu-id="970df-102">How to: Generate the Object Model in Visual Basic or C\#</span></span>
<span data-ttu-id="970df-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene eseguito il mapping di un modello a oggetti nel linguaggio di programmazione in uso a un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="970df-103">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], an object model in your own programming language is mapped to a relational database.</span></span> <span data-ttu-id="970df-104">Sono disponibili due strumenti per la generazione automatica di un C# Visual Basic o di un modello dai metadati di un database esistente.</span><span class="sxs-lookup"><span data-stu-id="970df-104">Two tools are available for automatically generating a Visual Basic or C# model from the metadata of an existing database.</span></span>  
  
- <span data-ttu-id="970df-105">Se si utilizza Visual Studio, è possibile utilizzare il Object Relational Designer per generare un modello a oggetti.</span><span class="sxs-lookup"><span data-stu-id="970df-105">If you are using Visual Studio, you can use the Object Relational Designer to generate an object model.</span></span> <span data-ttu-id="970df-106">In O/R Designer è disponibile un'interfaccia utente avanzata che consente di generare un modello a oggetti [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="970df-106">The O/R Designer provides a rich user interface to help you generate a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span> <span data-ttu-id="970df-107">Per altre informazioni, vedere [strumenti LINQ to SQL in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span><span class="sxs-lookup"><span data-stu-id="970df-107">For more information see, [Linq to SQL Tools in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).</span></span>
  
- <span data-ttu-id="970df-108">Lo strumento della riga di comando SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="970df-108">The SQLMetal command-line tool.</span></span> <span data-ttu-id="970df-109">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="970df-109">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="970df-110">Se non si dispone di un database esistente e si desidera crearne uno da un modello a oggetti, è possibile creare il modello a oggetti usando l'editor di codice e <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span><span class="sxs-lookup"><span data-stu-id="970df-110">If you do not have an existing database and want to create one from an object model, you can create your object model by using your code editor and <xref:System.Data.Linq.DataContext.CreateDatabase%2A>.</span></span> <span data-ttu-id="970df-111">Per altre informazioni, vedere [procedura: creare un database in modo dinamico](how-to-dynamically-create-a-database.md).</span><span class="sxs-lookup"><span data-stu-id="970df-111">For more information, see [How to: Dynamically Create a Database](how-to-dynamically-create-a-database.md).</span></span>  
  
 <span data-ttu-id="970df-112">La documentazione relativa a Progettazione relazionale oggetti fornisce esempi su come generare un modello a C# oggetti o Visual Basic usando la finestra di progettazione di o/r.</span><span class="sxs-lookup"><span data-stu-id="970df-112">Documentation for the O/R Designer provides examples of how to generate a Visual Basic or C# object model by using the O/R Designer.</span></span> <span data-ttu-id="970df-113">Le informazioni seguenti forniscono esempi relativi all'uso dello strumento della riga di comando SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="970df-113">The following information provide examples of how to use the SQLMetal command-line tool.</span></span> <span data-ttu-id="970df-114">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="970df-114">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="970df-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="970df-115">Example</span></span>  
 <span data-ttu-id="970df-116">La riga di comando SQLMetal illustrata nell'esempio seguente produce Visual Basic codice come modello a oggetti basato su attributi del database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="970df-116">The SQLMetal command line shown in the following example produces Visual Basic code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="970df-117">Viene eseguito il rendering anche di stored procedure e funzioni.</span><span class="sxs-lookup"><span data-stu-id="970df-117">Stored procedures and functions are also rendered.</span></span>  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a><span data-ttu-id="970df-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="970df-118">Example</span></span>  
 <span data-ttu-id="970df-119">Usando la riga di comando SQLMetal riportata nell'esempio è possibile produrre codice C# come modello a oggetti basato su attributi del database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="970df-119">The SQLMetal command line shown in the following example produces C# code as the attribute-based object model of the Northwind sample database.</span></span> <span data-ttu-id="970df-120">Viene eseguito il rendering anche di stored procedure e funzioni, mentre i nomi delle tabelle vengono pluralizzati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="970df-120">Stored procedures and functions are also rendered, and table names are automatically pluralized.</span></span>  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a><span data-ttu-id="970df-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="970df-121">See also</span></span>

- [<span data-ttu-id="970df-122">Guida per programmatori</span><span class="sxs-lookup"><span data-stu-id="970df-122">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="970df-123">Modello a oggetti LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="970df-123">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="970df-124">Apprendimento tramite procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="970df-124">Learning by Walkthroughs</span></span>](learning-by-walkthroughs.md)
- [<span data-ttu-id="970df-125">Procedura: personalizzare classi di entità mediante l'Editor del codice</span><span class="sxs-lookup"><span data-stu-id="970df-125">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [<span data-ttu-id="970df-126">Mapping basato su attributi</span><span class="sxs-lookup"><span data-stu-id="970df-126">Attribute-Based Mapping</span></span>](attribute-based-mapping.md)
- [<span data-ttu-id="970df-127">SqlMetal.exe (strumento per la generazione del codice)</span><span class="sxs-lookup"><span data-stu-id="970df-127">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- <span data-ttu-id="970df-128">[External Mapping](external-mapping.md) (Mapping esterno)</span><span class="sxs-lookup"><span data-stu-id="970df-128">[External Mapping](external-mapping.md)</span></span>
- [<span data-ttu-id="970df-129">Download di database di esempio</span><span class="sxs-lookup"><span data-stu-id="970df-129">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="970df-130">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="970df-130">Creating the Object Model</span></span>](creating-the-object-model.md)
