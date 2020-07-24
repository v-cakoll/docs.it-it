---
title: Trasformazioni dati con LINQ (C#)
description: Informazioni su come usare le query LINQ in C# per trasformare i dati. È possibile modificare la sequenza ordinando e raggruppando e creando nuovi tipi utilizzando la clausola SELECT.
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
ms.openlocfilehash: 6844cf2aa589f7516a9e40bc604c5f907ec6d311
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104025"
---
# <a name="data-transformations-with-linq-c"></a><span data-ttu-id="5dd8a-104">Trasformazioni dati con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="5dd8a-104">Data Transformations with LINQ (C#)</span></span>
<span data-ttu-id="5dd8a-105">LINQ (Language-Integrated Query) non riguarda solo il recupero dei dati.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-105">Language-Integrated Query (LINQ) is not only about retrieving data.</span></span> <span data-ttu-id="5dd8a-106">È anche un potente strumento per la trasformazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-106">It is also a powerful tool for transforming data.</span></span> <span data-ttu-id="5dd8a-107">Utilizzando una query LINQ, è possibile utilizzare una sequenza di origine come input e modificarla in molti modi per creare una nuova sequenza di output.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-107">By using a LINQ query, you can use a source sequence as input and modify it in many ways to create a new output sequence.</span></span> <span data-ttu-id="5dd8a-108">È possibile modificare la sequenza senza modificare gli elementi con operazioni di ordinamento e raggruppamento.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-108">You can modify the sequence itself without modifying the elements themselves by sorting and grouping.</span></span> <span data-ttu-id="5dd8a-109">Ma probabilmente la funzionalità più potente delle query LINQ è la possibilità di creare nuovi tipi.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-109">But perhaps the most powerful feature of LINQ queries is the ability to create new types.</span></span> <span data-ttu-id="5dd8a-110">Questa operazione viene eseguita nella clausola [select](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5dd8a-110">This is accomplished in the [select](../../../language-reference/keywords/select-clause.md) clause.</span></span> <span data-ttu-id="5dd8a-111">Ad esempio, è possibile effettuare le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5dd8a-111">For example, you can perform the following tasks:</span></span>  
  
- <span data-ttu-id="5dd8a-112">Unire più sequenze di input in un'unica sequenza di output con un nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-112">Merge multiple input sequences into a single output sequence that has a new type.</span></span>  
  
- <span data-ttu-id="5dd8a-113">Creare sequenze di output i cui elementi sono costituiti da una o più proprietà di ogni elemento nella sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-113">Create output sequences whose elements consist of only one or several properties of each element in the source sequence.</span></span>  
  
- <span data-ttu-id="5dd8a-114">Creare sequenze di output i cui elementi sono costituiti dai risultati delle operazioni eseguite sui dati di origine.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-114">Create output sequences whose elements consist of the results of operations performed on the source data.</span></span>  
  
- <span data-ttu-id="5dd8a-115">Creare sequenze di output in un formato diverso.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-115">Create output sequences in a different format.</span></span> <span data-ttu-id="5dd8a-116">Ad esempio, è possibile trasformare i dati da righe SQL o file di testo in XML.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-116">For example, you can transform data from SQL rows or text files into XML.</span></span>  
  
 <span data-ttu-id="5dd8a-117">Questi sono solo alcuni esempi.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-117">These are just several examples.</span></span> <span data-ttu-id="5dd8a-118">Naturalmente, queste trasformazioni possono essere combinate in modi diversi nella stessa query.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-118">Of course, these transformations can be combined in various ways in the same query.</span></span> <span data-ttu-id="5dd8a-119">Inoltre, la sequenza di output di una query può essere usata come sequenza di input per una nuova query.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-119">Furthermore, the output sequence of one query can be used as the input sequence for a new query.</span></span>  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a><span data-ttu-id="5dd8a-120">Unione di più input in un'unica sequenza di output</span><span class="sxs-lookup"><span data-stu-id="5dd8a-120">Joining Multiple Inputs into One Output Sequence</span></span>  
 <span data-ttu-id="5dd8a-121">È possibile usare una query LINQ per creare una sequenza di output che contiene elementi da più di una sequenza di input.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-121">You can use a LINQ query to create an output sequence that contains elements from more than one input sequence.</span></span> <span data-ttu-id="5dd8a-122">Nell'esempio seguente viene illustrato come combinare due strutture di dati in memoria, ma è possibile applicare gli stessi principi per combinare dati da origini XML, SQL o DataSet.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-122">The following example shows how to combine two in-memory data structures, but the same principles can be applied to combine data from XML or SQL or DataSet sources.</span></span> <span data-ttu-id="5dd8a-123">Si supponga di avere questi tipi di classi:</span><span class="sxs-lookup"><span data-stu-id="5dd8a-123">Assume the following two class types:</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 <span data-ttu-id="5dd8a-124">Nell'esempio riportato di seguito è visualizzata la query:</span><span class="sxs-lookup"><span data-stu-id="5dd8a-124">The following example shows the query:</span></span>  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 <span data-ttu-id="5dd8a-125">Per altre informazioni, vedere [Clausola join](../../../language-reference/keywords/join-clause.md) e [Clausola select](../../../language-reference/keywords/select-clause.md).</span><span class="sxs-lookup"><span data-stu-id="5dd8a-125">For more information, see [join clause](../../../language-reference/keywords/join-clause.md) and [select clause](../../../language-reference/keywords/select-clause.md).</span></span>  
  
## <a name="selecting-a-subset-of-each-source-element"></a><span data-ttu-id="5dd8a-126">Selezione di un sottoinsieme di ogni elemento di origine</span><span class="sxs-lookup"><span data-stu-id="5dd8a-126">Selecting a Subset of each Source Element</span></span>  
 <span data-ttu-id="5dd8a-127">Esistono due modi principali per selezionare un sottoinsieme di ogni elemento nella sequenza di origine:</span><span class="sxs-lookup"><span data-stu-id="5dd8a-127">There are two primary ways to select a subset of each element in the source sequence:</span></span>  
  
1. <span data-ttu-id="5dd8a-128">Per selezionare solo un membro dell'elemento di origine, usare l'operazione con punto.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-128">To select just one member of the source element, use the dot operation.</span></span> <span data-ttu-id="5dd8a-129">Nell'esempio seguente si supponga che un oggetto `Customer` contenga diverse proprietà pubbliche tra cui una stringa denominata `City`.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-129">In the following example, assume that a `Customer` object contains several public properties including a string named `City`.</span></span> <span data-ttu-id="5dd8a-130">Quando viene eseguita, questa query produce una sequenza di output di stringhe.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-130">When executed, this query will produce an output sequence of strings.</span></span>  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. <span data-ttu-id="5dd8a-131">Per creare gli elementi che contengono più di una proprietà dall'elemento di origine, è possibile usare un inizializzatore di oggetto con un oggetto denominato o un tipo anonimo.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-131">To create elements that contain more than one property from the source element, you can use an object initializer with either a named object or an anonymous type.</span></span> <span data-ttu-id="5dd8a-132">Nell'esempio seguente viene illustrato l'uso di un tipo anonimo per incapsulare due proprietà da ogni elemento `Customer`:</span><span class="sxs-lookup"><span data-stu-id="5dd8a-132">The following example shows the use of an anonymous type to encapsulate two properties from each `Customer` element:</span></span>  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 <span data-ttu-id="5dd8a-133">Per altre informazioni, vedere [Inizializzatori di oggetto e di insieme](../../classes-and-structs/object-and-collection-initializers.md) e [Tipi anonimi](../../classes-and-structs/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="5dd8a-133">For more information, see [Object and Collection Initializers](../../classes-and-structs/object-and-collection-initializers.md) and [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>  
  
## <a name="transforming-in-memory-objects-into-xml"></a><span data-ttu-id="5dd8a-134">Trasformazione di oggetti in memoria in XML</span><span class="sxs-lookup"><span data-stu-id="5dd8a-134">Transforming in-Memory Objects into XML</span></span>  
 <span data-ttu-id="5dd8a-135">Le query LINQ semplificano la trasformazione dei dati tra le strutture di dati in memoria, i database SQL, i set di dati ADO.NET e i documenti o i flussi XML.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-135">LINQ queries make it easy to transform data between in-memory data structures, SQL databases, ADO.NET Datasets and XML streams or documents.</span></span> <span data-ttu-id="5dd8a-136">Nell'esempio seguente gli oggetti di una struttura di dati in memoria vengono trasformati in elementi XML.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-136">The following example transforms objects in an in-memory data structure into XML elements.</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 <span data-ttu-id="5dd8a-137">Il codice genera il seguente output XML:</span><span class="sxs-lookup"><span data-stu-id="5dd8a-137">The code produces the following XML output:</span></span>  
  
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
  
 <span data-ttu-id="5dd8a-138">Per altre informazioni, vedere [Creazione di alberi XML in C# (LINQ to XML)](./creating-xml-trees-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="5dd8a-138">For more information, see [Creating XML Trees in C# (LINQ to XML)](./creating-xml-trees-linq-to-xml-2.md).</span></span>  
  
## <a name="performing-operations-on-source-elements"></a><span data-ttu-id="5dd8a-139">Esecuzione di operazioni su elementi di origine</span><span class="sxs-lookup"><span data-stu-id="5dd8a-139">Performing Operations on Source Elements</span></span>  
 <span data-ttu-id="5dd8a-140">Una sequenza di output potrebbe non contenere elementi o proprietà degli elementi della sequenza di origine.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-140">An output sequence might not contain any elements or element properties from the source sequence.</span></span> <span data-ttu-id="5dd8a-141">L'output potrebbe invece essere una sequenza di valori che viene calcolata usando gli elementi di origine come argomenti di input.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-141">The output might instead be a sequence of values that is computed by using the source elements as input arguments.</span></span>

 <span data-ttu-id="5dd8a-142">Con la query seguente viene eseguita una sequenza di numeri che rappresentano raggi di cerchi, viene calcolata l'area per ogni raggio e viene restituita una sequenza di output contenente stringhe formattate con l'area calcolata.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-142">The following query will take a sequence of numbers that represent radii of circles, calculate the area for each radius, and return an output sequence containing strings formatted with the calculated area.</span></span>

 <span data-ttu-id="5dd8a-143">Ogni stringa per la sequenza di output verrà formattata utilizzando l' [interpolazione di stringhe](../../../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="5dd8a-143">Each string for the output sequence will be formatted using [string interpolation](../../../language-reference/tokens/interpolated.md).</span></span> <span data-ttu-id="5dd8a-144">Una stringa interpolata avrà un oggetto `$` davanti alle virgolette di apertura della stringa e le operazioni possono essere eseguite all'interno di parentesi graffe posizionate all'interno della stringa interpolata.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-144">An interpolated string will have a `$` in front of the string's opening quotation mark, and operations can be performed within curly braces placed inside the interpolated string.</span></span> <span data-ttu-id="5dd8a-145">Una volta eseguite queste operazioni, i risultati saranno concatenati.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-145">Once those operations are performed, the results will be concatenated.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5dd8a-146">La chiamata ai metodi nelle espressioni di query non è supportata se la query verrà traslata in un altro dominio.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-146">Calling methods in query expressions is not supported if the query will be translated into some other domain.</span></span> <span data-ttu-id="5dd8a-147">Ad esempio, non è possibile chiamare un normale metodo C# in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] perché SQL Server non offre alcun contesto.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-147">For example, you cannot call an ordinary C# method in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] because SQL Server has no context for it.</span></span> <span data-ttu-id="5dd8a-148">Tuttavia, è possibile eseguire il mapping delle stored procedure ai metodi e chiamarli.</span><span class="sxs-lookup"><span data-stu-id="5dd8a-148">However, you can map stored procedures to methods and call those.</span></span> <span data-ttu-id="5dd8a-149">Per altre informazioni, vedere [Stored procedure](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="5dd8a-149">For more information, see [Stored Procedures](../../../../framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="5dd8a-150">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5dd8a-150">See also</span></span>

- [<span data-ttu-id="5dd8a-151">LINQ (Language-Integrated Query) (C#)</span><span class="sxs-lookup"><span data-stu-id="5dd8a-151">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
- [<span data-ttu-id="5dd8a-152">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="5dd8a-152">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="5dd8a-153">LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="5dd8a-153">LINQ to DataSet</span></span>](../../../../framework/data/adonet/linq-to-dataset.md)
- [<span data-ttu-id="5dd8a-154">LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5dd8a-154">LINQ to XML (C#)</span></span>](./linq-to-xml-overview.md)
- [<span data-ttu-id="5dd8a-155">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="5dd8a-155">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="5dd8a-156">clausola SELECT</span><span class="sxs-lookup"><span data-stu-id="5dd8a-156">select clause</span></span>](../../../language-reference/keywords/select-clause.md)
