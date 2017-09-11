---
title: Conversione di tipi di dati (Visual Basic) | Documenti di Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 948779e1648291b00a68bfd83d57750d48a9a6d8
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="a7399-102">La conversione dei tipi di dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7399-102">Converting Data Types (Visual Basic)</span></span>
<span data-ttu-id="a7399-103">Metodi di conversione modificano il tipo di oggetti di input.</span><span class="sxs-lookup"><span data-stu-id="a7399-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="a7399-104">Le operazioni di conversione nelle query LINQ sono utili in un'ampia gamma di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="a7399-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="a7399-105">Di seguito sono riportati alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="a7399-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="a7399-106">Il <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName>metodo può essere utilizzato per nascondere l'implementazione personalizzata di un tipo di un operatore di query standard.</xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="a7399-107">Il <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName>metodo può essere utilizzato per abilitare le raccolte senza parametri per l'esecuzione di query LINQ.</xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="a7399-108">Il <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, e <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName>possono essere utilizzati per forzare l'esecuzione immediata della query anziché rinviare, fino a che la query viene enumerata.</xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName> </xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7399-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="a7399-109">Methods</span></span>  
 <span data-ttu-id="a7399-110">Nella tabella seguente sono elencati i metodi di operatore di query standard che eseguono conversioni di tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="a7399-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="a7399-111">I metodi di conversione in questa tabella i cui nomi iniziano con "As" modificano il tipo statico dell'insieme di origine ma non lo enumerano.</span><span class="sxs-lookup"><span data-stu-id="a7399-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="a7399-112">Digitare i metodi i cui nomi iniziano con "A enumerare la raccolta di origine e inserire gli elementi nella raccolta corrispondente".</span><span class="sxs-lookup"><span data-stu-id="a7399-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="a7399-113">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="a7399-113">Method Name</span></span>|<span data-ttu-id="a7399-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a7399-114">Description</span></span>|<span data-ttu-id="a7399-115">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a7399-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="a7399-116">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="a7399-116">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="a7399-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="a7399-117">AsEnumerable</span></span>|<span data-ttu-id="a7399-118">Restituisce l'input digitato come <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="a7399-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="a7399-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="a7399-119">Not applicable.</span></span>|<span data-ttu-id="a7399-120"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-120"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="a7399-121">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="a7399-121">AsQueryable</span></span>|<span data-ttu-id="a7399-122">Converte un (generici) <xref:System.Collections.IEnumerable>in un <xref:System.Linq.IQueryable>.</xref:System.Linq.IQueryable> (generico)</xref:System.Collections.IEnumerable></span><span class="sxs-lookup"><span data-stu-id="a7399-122">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="a7399-123">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="a7399-123">Not applicable.</span></span>|<span data-ttu-id="a7399-124"><xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-124"><xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="a7399-125">Cast</span><span class="sxs-lookup"><span data-stu-id="a7399-125">Cast</span></span>|<span data-ttu-id="a7399-126">Esegue il cast di elementi di una raccolta in un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="a7399-126">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<span data-ttu-id="a7399-127"><xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-127"><xref:System.Linq.Enumerable.Cast%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="a7399-128"><xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-128"><xref:System.Linq.Queryable.Cast%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="a7399-129">OfType</span><span class="sxs-lookup"><span data-stu-id="a7399-129">OfType</span></span>|<span data-ttu-id="a7399-130">Filtra i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="a7399-130">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="a7399-131">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="a7399-131">Not applicable.</span></span>|<span data-ttu-id="a7399-132"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-132"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=fullName></span></span><br /><br /> <span data-ttu-id="a7399-133"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-133"><xref:System.Linq.Queryable.OfType%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="a7399-134">ToArray</span><span class="sxs-lookup"><span data-stu-id="a7399-134">ToArray</span></span>|<span data-ttu-id="a7399-135">Converte una raccolta in una matrice.</span><span class="sxs-lookup"><span data-stu-id="a7399-135">Converts a collection to an array.</span></span> <span data-ttu-id="a7399-136">Questo metodo impone l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="a7399-136">This method forces query execution.</span></span>|<span data-ttu-id="a7399-137">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="a7399-137">Not applicable.</span></span>|<span data-ttu-id="a7399-138"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-138"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="a7399-139">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="a7399-139">ToDictionary</span></span>|<span data-ttu-id="a7399-140">Inserisce gli elementi in un <xref:System.Collections.Generic.Dictionary%602>in base a una funzione selettore di chiave.</xref:System.Collections.Generic.Dictionary%602></span><span class="sxs-lookup"><span data-stu-id="a7399-140">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="a7399-141">Questo metodo impone l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="a7399-141">This method forces query execution.</span></span>|<span data-ttu-id="a7399-142">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="a7399-142">Not applicable.</span></span>|<span data-ttu-id="a7399-143"><xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-143"><xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="a7399-144">ToList</span><span class="sxs-lookup"><span data-stu-id="a7399-144">ToList</span></span>|<span data-ttu-id="a7399-145">Converte una raccolta a un <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601></span><span class="sxs-lookup"><span data-stu-id="a7399-145">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="a7399-146">Questo metodo impone l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="a7399-146">This method forces query execution.</span></span>|<span data-ttu-id="a7399-147">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="a7399-147">Not applicable.</span></span>|<span data-ttu-id="a7399-148"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-148"><xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span></span>|  
|<span data-ttu-id="a7399-149">ToLookup</span><span class="sxs-lookup"><span data-stu-id="a7399-149">ToLookup</span></span>|<span data-ttu-id="a7399-150">Inserisce gli elementi in un <xref:System.Linq.Lookup%602>(un dizionario uno-a-molti) in base a una funzione selettore di chiave.</xref:System.Linq.Lookup%602></span><span class="sxs-lookup"><span data-stu-id="a7399-150">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="a7399-151">Questo metodo impone l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="a7399-151">This method forces query execution.</span></span>|<span data-ttu-id="a7399-152">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="a7399-152">Not applicable.</span></span>|<span data-ttu-id="a7399-153"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="a7399-153"><xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=fullName></span></span>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="a7399-154">Esempio di sintassi di espressione di query</span><span class="sxs-lookup"><span data-stu-id="a7399-154">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="a7399-155">Nell'esempio di codice viene illustrato come utilizzare il `From As` clausola per eseguire il cast di un tipo a un sottotipo prima di accedere a un membro che è disponibile solo nel sottotipo.</span><span class="sxs-lookup"><span data-stu-id="a7399-155">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
```vb  
Class Plant  
    Public Property Name As String  
End Class  
  
Class CarnivorousPlant  
    Inherits Plant  
    Public Property TrapType As String  
End Class  
  
Sub Cast()  
  
    Dim plants() As Plant = {   
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},   
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},   
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},   
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}  
  
    Dim query = From plant As CarnivorousPlant In plants   
                Where plant.TrapType = "Snap Trap"   
                Select plant  
  
    Dim sb As New System.Text.StringBuilder()  
    For Each plant In query  
        sb.AppendLine(plant.Name)  
    Next  
  
    ' Display the results.  
    MsgBox(sb.ToString())  
  
    ' This code produces the following output:  
  
    ' Venus Fly Trap  
    ' Waterwheel Plant  
  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7399-156">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a7399-156">See Also</span></span>  
 <span data-ttu-id="a7399-157"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="a7399-157"><xref:System.Linq></span></span>   
<span data-ttu-id="a7399-158"> [Cenni preliminari sugli operatori di Query standard (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span><span class="sxs-lookup"><span data-stu-id="a7399-158"> [Standard Query Operators Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md) </span></span>  
<span data-ttu-id="a7399-159"> [Clausola FROM](../../../../visual-basic/language-reference/queries/from-clause.md) </span><span class="sxs-lookup"><span data-stu-id="a7399-159"> [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md) </span></span>  
<span data-ttu-id="a7399-160"> [Procedura: eseguire Query su un ArrayList con LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)</span><span class="sxs-lookup"><span data-stu-id="a7399-160"> [How to: Query an ArrayList with LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)</span></span>
