---
title: Trasformazioni dati con LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: 41542b663930ba92d47e62151e913429b690054d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879127"
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="5e46b-102">Trasformazioni dati con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="5e46b-102">Data Transformations with LINQ (C#)</span></span>
[!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] <span data-ttu-id="5e46b-103">non riguarda solo il recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="5e46b-103">is not only about retrieving data.</span></span> <span data-ttu-id="5e46b-104">È anche un potente strumento per la trasformazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="5e46b-104">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="5e46b-105">Con una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] è possibile usare una sequenza di origine come input e modificarla in molti modi per creare una nuova sequenza di output.</span><span class="sxs-lookup"><span data-stu-id="5e46b-105">By using a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="5e46b-106">È possibile modificare la sequenza senza modificare gli elementi con operazioni di ordinamento e raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="5e46b-106">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="5e46b-107">Ma probabilmente la funzionalità più potente delle query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] è la possibilità di creare nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="5e46b-107">But perhaps the most powerful feature of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries is the ability to create new types.</span></span> <span data-ttu-id="5e46b-108">Questa operazione viene eseguita nella clausola [select](../../../../csharp/language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5e46b-108">This is accomplished in the [select](../../../../csharp/language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="5e46b-109">Ad esempio, è possibile effettuare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e46b-109">For example, you can perform the following tasks:</span></span>  
  
- <span data-ttu-id="5e46b-110">Unire più sequenze di input in un'unica sequenza di output con un nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="5e46b-110">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
- <span data-ttu-id="5e46b-111">Creare sequenze di output i cui elementi sono costituiti da una o più proprietà di ogni elemento nella sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="5e46b-111">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
- <span data-ttu-id="5e46b-112">Creare sequenze di output i cui elementi sono costituiti dai risultati delle operazioni eseguite sui dati di origine.</span><span class="sxs-lookup"><span data-stu-id="5e46b-112">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
- <span data-ttu-id="5e46b-113">Creare sequenze di output in un formato diverso.</span><span class="sxs-lookup"><span data-stu-id="5e46b-113">Create output sequences in a different format.</span></span> <span data-ttu-id="5e46b-114">Ad esempio, è possibile trasformare i dati da righe SQL o file di testo in XML.</span><span class="sxs-lookup"><span data-stu-id="5e46b-114">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="5e46b-115">Questi sono solo alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="5e46b-115">These are just several examples.</span></span> <span data-ttu-id="5e46b-116">Naturalmente, queste trasformazioni possono essere combinate in modi diversi nella stessa query.</span><span class="sxs-lookup"><span data-stu-id="5e46b-116">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="5e46b-117">Inoltre, la sequenza di output di una query può essere usata come sequenza di input per una nuova query.</span><span class="sxs-lookup"><span data-stu-id="5e46b-117">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="5e46b-118">Unione di più input in un'unica sequenza di output</span><span class="sxs-lookup"><span data-stu-id="5e46b-118">Joining Multiple Inputs into One Output Sequence</span></span>  
 <span data-ttu-id="5e46b-119">È possibile usare una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] per creare una sequenza di output che contiene gli elementi di più di una sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="5e46b-119">You can use a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="5e46b-120">Nell'esempio seguente viene illustrato come combinare due strutture di dati in memoria, ma è possibile applicare gli stessi principi per combinare dati da origini XML, SQL o DataSet.</span><span class="sxs-lookup"><span data-stu-id="5e46b-120">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="5e46b-121">Si supponga di avere questi tipi di classi:</span><span class="sxs-lookup"><span data-stu-id="5e46b-121">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 <span data-ttu-id="5e46b-122">Nell'esempio riportato di seguito è visualizzata la query:</span><span class="sxs-lookup"><span data-stu-id="5e46b-122">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 <span data-ttu-id="5e46b-123">Per altre informazioni, vedere [Clausola join](../../../../csharp/language-reference/keywords/join-clause.md) e [Clausola select](../../../../csharp/language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5e46b-123">For more information, see [join clause](../../../../csharp/language-reference/keywords/join-clause.md) and [select clause](../../../../csharp/language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="5e46b-124">Selezione di un sottoinsieme di ogni elemento di origine</span><span class="sxs-lookup"><span data-stu-id="5e46b-124">Selecting a Subset of each Source Element</span></span>  
 <span data-ttu-id="5e46b-125">Esistono due modi principali per selezionare un sottoinsieme di ogni elemento nella sequenza di origine:</span><span class="sxs-lookup"><span data-stu-id="5e46b-125">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1. <span data-ttu-id="5e46b-126">Per selezionare solo un membro dell'elemento di origine, usare l'operazione con punto.</span><span class="sxs-lookup"><span data-stu-id="5e46b-126">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="5e46b-127">Nell'esempio seguente si supponga che un oggetto `Customer` contenga diverse proprietà pubbliche tra cui una stringa denominata `City`.</span><span class="sxs-lookup"><span data-stu-id="5e46b-127">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="5e46b-128">Quando viene eseguita, questa query produce una sequenza di output di stringhe.</span><span class="sxs-lookup"><span data-stu-id="5e46b-128">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. <span data-ttu-id="5e46b-129">Per creare gli elementi che contengono più di una proprietà dall'elemento di origine, è possibile usare un inizializzatore di oggetto con un oggetto denominato o un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="5e46b-129">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="5e46b-130">Nell'esempio seguente viene illustrato l'uso di un tipo anonimo per incapsulare due proprietà da ogni elemento `Customer`:</span><span class="sxs-lookup"><span data-stu-id="5e46b-130">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="5e46b-131">Per altre informazioni, vedere [Inizializzatori di oggetto e di insieme](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) e [Tipi anonimi](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="5e46b-131">For more information, see [Object and Collection Initializers](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="5e46b-132">Trasformazione di oggetti in memoria in XML</span><span class="sxs-lookup"><span data-stu-id="5e46b-132">Transforming in-Memory Objects into XML</span></span>  
 <span data-ttu-id="5e46b-133">Le query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] semplificano la trasformazione dei dati tra strutture di dati in memoria, database SQL, set di dati ADO.NET e flussi o documenti XML.</span><span class="sxs-lookup"><span data-stu-id="5e46b-133">[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] queries make it easy to transform data between in-memory data structures, SQL databases, ADO.NET Datasets and XML streams or documents.</span></span> <span data-ttu-id="5e46b-134">Nell'esempio seguente gli oggetti di una struttura di dati in memoria vengono trasformati in elementi XML.</span><span class="sxs-lookup"><span data-stu-id="5e46b-134">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 <span data-ttu-id="5e46b-135">Il codice genera il seguente output XML:</span><span class="sxs-lookup"><span data-stu-id="5e46b-135">The code produces the following XML output:</span></span>  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 <span data-ttu-id="5e46b-136">Per altre informazioni, vedere [Creazione di alberi XML in C# (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="5e46b-136">For more information, see [Creating XML Trees in C# (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="5e46b-137">Esecuzione di operazioni su elementi di origine</span><span class="sxs-lookup"><span data-stu-id="5e46b-137">Performing Operations on Source Elements</span></span>  
 <span data-ttu-id="5e46b-138">Una sequenza di output potrebbe non contenere elementi o proprietà degli elementi della sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="5e46b-138">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="5e46b-139">L'output potrebbe invece essere una sequenza di valori che viene calcolata usando gli elementi di origine come argomenti di input.</span><span class="sxs-lookup"><span data-stu-id="5e46b-139">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span> <span data-ttu-id="5e46b-140">La seguente query semplice, quando viene eseguita, restituisce una sequenza di stringhe i cui valori rappresentano un calcolo basato sulla sequenza di origine di elementi di tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="5e46b-140">The following simple query, when it is executed, outputs a sequence of strings whose values represent a calculation based on the source sequence of elements of type `double`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e46b-141">La chiamata ai metodi nelle espressioni di query non è supportata se la query verrà traslata in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="5e46b-141">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="5e46b-142">Ad esempio, non è possibile chiamare un normale metodo C# in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] perché SQL Server non offre alcun contesto.</span><span class="sxs-lookup"><span data-stu-id="5e46b-142">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="5e46b-143">Tuttavia, è possibile eseguire il mapping delle stored procedure ai metodi e chiamarli.</span><span class="sxs-lookup"><span data-stu-id="5e46b-143">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="5e46b-144">Per altre informazioni, vedere [Stored procedure](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5e46b-144">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="5e46b-145">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e46b-145">See also</span></span>

- [<span data-ttu-id="5e46b-146">Language-Integrated Query (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="5e46b-146">Language-Integrated Query (LINQ) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/index.md)
- [<span data-ttu-id="5e46b-147">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5e46b-147">LINQ to SQL</span></span>](../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="5e46b-148">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="5e46b-148">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)
- [<span data-ttu-id="5e46b-149">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5e46b-149">LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)
- [<span data-ttu-id="5e46b-150">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="5e46b-150">LINQ Query Expressions</span></span>](../../../../csharp/programming-guide/linq-query-expressions/index.md)
- [<span data-ttu-id="5e46b-151">Clausola select</span><span class="sxs-lookup"><span data-stu-id="5e46b-151">select clause</span></span>](../../../../csharp/language-reference/keywords/select-clause.md)
