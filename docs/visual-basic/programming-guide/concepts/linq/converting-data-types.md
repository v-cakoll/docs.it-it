---
title: La conversione dei tipi di dati (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5fb0e9dfb0f1fb882116449757ed0f0bf9029b39
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="57038-102">La conversione dei tipi di dati (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57038-102">Converting Data Types (Visual Basic)</span></span>
<span data-ttu-id="57038-103">I metodi di conversione modificano il tipo degli oggetti di input.</span><span class="sxs-lookup"><span data-stu-id="57038-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="57038-104">Le operazioni di conversione nelle query LINQ sono utili in un'ampia gamma di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="57038-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="57038-105">Ecco alcuni esempi:</span><span class="sxs-lookup"><span data-stu-id="57038-105">Following are some examples:</span></span>  
  
-   <span data-ttu-id="57038-106">Il metodo <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> può essere usato per nascondere l'implementazione personalizzata di un tipo di un operatore query standard.</span><span class="sxs-lookup"><span data-stu-id="57038-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
-   <span data-ttu-id="57038-107">Il metodo <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> può essere usato per abilitare le raccolte senza parametri per l'esecuzione di query LINQ.</span><span class="sxs-lookup"><span data-stu-id="57038-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
-   <span data-ttu-id="57038-108">I metodi <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> e <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> possono essere usati per forzare l'esecuzione di una query immediata invece che rinviarla fino a quando la query non viene enumerata.</span><span class="sxs-lookup"><span data-stu-id="57038-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57038-109">Metodi</span><span class="sxs-lookup"><span data-stu-id="57038-109">Methods</span></span>  
 <span data-ttu-id="57038-110">Nella tabella seguente sono elencati i metodi di operatore query standard che eseguono conversioni di tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="57038-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="57038-111">I metodi di conversione nella tabella i cui nomi iniziano con "As" modificano il tipo statico della raccolta di origine ma non lo enumerano.</span><span class="sxs-lookup"><span data-stu-id="57038-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="57038-112">I metodi i cui nomi iniziano con "To" enumerano la raccolta di origine e inseriscono gli elementi nel tipo di raccolta corrispondente.</span><span class="sxs-lookup"><span data-stu-id="57038-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="57038-113">Nome metodo</span><span class="sxs-lookup"><span data-stu-id="57038-113">Method Name</span></span>|<span data-ttu-id="57038-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57038-114">Description</span></span>|<span data-ttu-id="57038-115">Sintassi delle espressioni di Query Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57038-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="57038-116">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="57038-116">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="57038-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="57038-117">AsEnumerable</span></span>|<span data-ttu-id="57038-118">Restituisce l'input tipizzato come oggetto <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="57038-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="57038-119">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="57038-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57038-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="57038-120">AsQueryable</span></span>|<span data-ttu-id="57038-121">Converte un oggetto <xref:System.Collections.IEnumerable> (generico) in un oggetto <xref:System.Linq.IQueryable> (generico).</span><span class="sxs-lookup"><span data-stu-id="57038-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="57038-122">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="57038-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57038-123">Cast</span><span class="sxs-lookup"><span data-stu-id="57038-123">Cast</span></span>|<span data-ttu-id="57038-124">Esegue il cast degli elementi di una raccolta a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="57038-124">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57038-125">OfType</span><span class="sxs-lookup"><span data-stu-id="57038-125">OfType</span></span>|<span data-ttu-id="57038-126">Filtra i valori, a seconda della loro capacità di eseguire il cast a un tipo specificato.</span><span class="sxs-lookup"><span data-stu-id="57038-126">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="57038-127">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="57038-127">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57038-128">ToArray</span><span class="sxs-lookup"><span data-stu-id="57038-128">ToArray</span></span>|<span data-ttu-id="57038-129">Converte una raccolta in una matrice.</span><span class="sxs-lookup"><span data-stu-id="57038-129">Converts a collection to an array.</span></span> <span data-ttu-id="57038-130">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="57038-130">This method forces query execution.</span></span>|<span data-ttu-id="57038-131">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="57038-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57038-132">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="57038-132">ToDictionary</span></span>|<span data-ttu-id="57038-133">Inserisce gli elementi in un oggetto <xref:System.Collections.Generic.Dictionary%602> sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="57038-133">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="57038-134">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="57038-134">This method forces query execution.</span></span>|<span data-ttu-id="57038-135">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="57038-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57038-136">ToList</span><span class="sxs-lookup"><span data-stu-id="57038-136">ToList</span></span>|<span data-ttu-id="57038-137">Converte una raccolta in un oggetto <xref:System.Collections.Generic.List%601>.</span><span class="sxs-lookup"><span data-stu-id="57038-137">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="57038-138">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="57038-138">This method forces query execution.</span></span>|<span data-ttu-id="57038-139">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="57038-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="57038-140">ToLookup</span><span class="sxs-lookup"><span data-stu-id="57038-140">ToLookup</span></span>|<span data-ttu-id="57038-141">Inserisce gli elementi in un oggetto <xref:System.Linq.Lookup%602>, un dizionario uno-a-molti, sulla base di una funzione del selettore di chiavi.</span><span class="sxs-lookup"><span data-stu-id="57038-141">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="57038-142">Questo metodo forza l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="57038-142">This method forces query execution.</span></span>|<span data-ttu-id="57038-143">Non applicabile.</span><span class="sxs-lookup"><span data-stu-id="57038-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="57038-144">Esempio di sintassi delle espressioni di query</span><span class="sxs-lookup"><span data-stu-id="57038-144">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="57038-145">Nell'esempio di codice viene illustrato come utilizzare il `From As` clausola per eseguire il cast di un tipo a un sottotipo prima di accedere a un membro che è disponibile solo per il sottotipo.</span><span class="sxs-lookup"><span data-stu-id="57038-145">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="57038-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57038-146">See Also</span></span>  
 <xref:System.Linq>  
 [<span data-ttu-id="57038-147">Panoramica degli operatori query standard (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57038-147">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="57038-148">Clausola From</span><span class="sxs-lookup"><span data-stu-id="57038-148">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="57038-149">Procedura: eseguire Query di ArrayList con LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57038-149">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
