---
title: 'Procedura: Generare codice personalizzato modificando un file DBML'
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: 6619f4b8c0a47b36a0b84fa21bab4109d26ef895
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002948"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="1d5cb-102">Procedura: Generare codice personalizzato modificando un file DBML</span><span class="sxs-lookup"><span data-stu-id="1d5cb-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="1d5cb-103">È possibile generare Visual Basic o C# codice sorgente da un file di metadati con estensione dbml (database Markup Language).</span><span class="sxs-lookup"><span data-stu-id="1d5cb-103">You can generate Visual Basic or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="1d5cb-104">Questo approccio consente di personalizzare il file DBML predefinito prima di generare il codice di mapping dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="1d5cb-105">Si tratta di una funzionalità avanzata.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="1d5cb-106">Di seguito sono elencati i passaggi di questo processo.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-106">The steps in this process are as follows:</span></span>  
  
1. <span data-ttu-id="1d5cb-107">Generare un file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-107">Generate a .dbml file.</span></span>  
  
2. <span data-ttu-id="1d5cb-108">Usare un editor per modificare il file con estensione dbml,</span><span class="sxs-lookup"><span data-stu-id="1d5cb-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="1d5cb-109">Si noti che il file. dbml deve essere convalidato in base al file di definizione dello schema (con estensione XSD) per i file [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. dbml.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="1d5cb-110">Per altre informazioni, vedere [generazione di codice in LINQ to SQL](code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="1d5cb-110">For more information, see [Code Generation in LINQ to SQL](code-generation-in-linq-to-sql.md).</span></span>  
  
3. <span data-ttu-id="1d5cb-111">Generare il Visual Basic o C# il codice sorgente.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-111">Generate the Visual Basic or C# source code.</span></span>  
  
 <span data-ttu-id="1d5cb-112">Negli esempi seguenti viene usato lo strumento della riga di comando SQLMetal.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="1d5cb-113">Per altre informazioni, vedere [SqlMetal.exe (strumento per la generazione del codice)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="1d5cb-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d5cb-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d5cb-114">Example</span></span>  
 <span data-ttu-id="1d5cb-115">Nel codice seguente viene generato un file con estensione dbml dal database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="1d5cb-116">Come origine per i metadati del database è possibile usare il nome del database o il nome del file con estensione mdf.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```console  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="1d5cb-117">Esempio</span><span class="sxs-lookup"><span data-stu-id="1d5cb-117">Example</span></span>  
 <span data-ttu-id="1d5cb-118">Il codice seguente genera Visual Basic o C# un file di codice sorgente da un file con estensione dbml.</span><span class="sxs-lookup"><span data-stu-id="1d5cb-118">The following code generates Visual Basic or C# source code file from a .dbml file.</span></span>  
  
```console
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="1d5cb-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d5cb-119">See also</span></span>

- [<span data-ttu-id="1d5cb-120">Generazione di codice in LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1d5cb-120">Code Generation in LINQ to SQL</span></span>](code-generation-in-linq-to-sql.md)
- [<span data-ttu-id="1d5cb-121">SqlMetal.exe (strumento per la generazione del codice)</span><span class="sxs-lookup"><span data-stu-id="1d5cb-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [<span data-ttu-id="1d5cb-122">Creazione del modello a oggetti</span><span class="sxs-lookup"><span data-stu-id="1d5cb-122">Creating the Object Model</span></span>](creating-the-object-model.md)
