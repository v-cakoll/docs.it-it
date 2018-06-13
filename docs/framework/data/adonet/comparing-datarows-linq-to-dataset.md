---
title: Confronto di DataRows (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
ms.openlocfilehash: 79fc91092badfd871a1409e2ee602272f3eae100
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756280"
---
# <a name="comparing-datarows-linq-to-dataset"></a><span data-ttu-id="3df01-102">Confronto di DataRows (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="3df01-102">Comparing DataRows (LINQ to DataSet)</span></span>
<span data-ttu-id="3df01-103">In [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] sono definiti diversi operatori sui set per confrontare gli elementi di origine e verificarne l'uguaglianza.</span><span class="sxs-lookup"><span data-stu-id="3df01-103">[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] defines various set operators to compare source elements to see if they are equal.</span></span> <span data-ttu-id="3df01-104">Gli operatori sui set disponibili in [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="3df01-104">[!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] provides the following set operators:</span></span>  
  
-   <xref:System.Linq.Enumerable.Distinct%2A>  
  
-   <xref:System.Linq.Enumerable.Union%2A>  
  
-   <xref:System.Linq.Enumerable.Intersect%2A>  
  
-   <xref:System.Linq.Enumerable.Except%2A>  
  
 <span data-ttu-id="3df01-105">Questi operatori confrontano gli elementi di origine chiamando i metodi <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> e <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> su ogni raccolta di elementi.</span><span class="sxs-lookup"><span data-stu-id="3df01-105">These operators compare source elements by calling the <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> and <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> methods on each collection of elements.</span></span> <span data-ttu-id="3df01-106">Nel caso di un oggetto <xref:System.Data.DataRow>, questi operatori eseguono un confronto di riferimento, che tuttavia non corrisponde in genere al comportamento ideale per le operazioni sui set eseguite su dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="3df01-106">In the case of a <xref:System.Data.DataRow>, these operators perform a reference comparison, which is generally not the ideal behavior for set operations over tabular data.</span></span> <span data-ttu-id="3df01-107">Per le operazioni sui set si desidera in genere stabilire se i valori degli elementi, e non i riferimenti agli elementi, sono uguali.</span><span class="sxs-lookup"><span data-stu-id="3df01-107">For set operations, you usually want to determine whether the element values are equal and not the element references.</span></span> <span data-ttu-id="3df01-108">Per questo motivo a <xref:System.Data.DataRowComparer> è stata aggiunta la classe [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3df01-108">Therefore, the <xref:System.Data.DataRowComparer> class has been added to [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="3df01-109">Questa classe può essere utilizzata per confrontare i valori di riga.</span><span class="sxs-lookup"><span data-stu-id="3df01-109">This class can be used to compare row values.</span></span>  
  
 <span data-ttu-id="3df01-110">La classe <xref:System.Data.DataRowComparer> contiene un'implementazione del confronto di valori per <xref:System.Data.DataRow>, pertanto può essere usata per operazioni sui set, ad esempio <xref:System.Linq.Enumerable.Distinct%2A>.</span><span class="sxs-lookup"><span data-stu-id="3df01-110">The <xref:System.Data.DataRowComparer> class contains a value comparison implementation for <xref:System.Data.DataRow>, so this class can be used for set operations such as <xref:System.Linq.Enumerable.Distinct%2A>.</span></span> <span data-ttu-id="3df01-111">Non è possibile creare direttamente un'istanza di questa classe ed è invece necessario usare la proprietà <xref:System.Data.DataRowComparer.Default%2A> per restituire un'istanza di <xref:System.Data.DataRowComparer%601>.</span><span class="sxs-lookup"><span data-stu-id="3df01-111">This class cannot be directly instantiated; instead, the <xref:System.Data.DataRowComparer.Default%2A> property must be used to return an instance of the <xref:System.Data.DataRowComparer%601>.</span></span> <span data-ttu-id="3df01-112">Viene quindi chiamato il metodo <xref:System.Data.DataRowComparer%601.Equals%2A> e i due oggetti <xref:System.Data.DataRow> da confrontare vengono passati come parametri di input.</span><span class="sxs-lookup"><span data-stu-id="3df01-112">The <xref:System.Data.DataRowComparer%601.Equals%2A> method is then called and the two <xref:System.Data.DataRow> objects to be compared are passed in as input parameters.</span></span> <span data-ttu-id="3df01-113">Il metodo <xref:System.Data.DataRowComparer%601.Equals%2A> restituisce `true` se il set ordinato di valori di colonna è uguale in entrambi gli oggetti <xref:System.Data.DataRow>; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3df01-113">The <xref:System.Data.DataRowComparer%601.Equals%2A> method returns `true` if the ordered set of column values in both <xref:System.Data.DataRow> objects are equal; otherwise, `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3df01-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="3df01-114">Example</span></span>  
 <span data-ttu-id="3df01-115">In questo esempio viene usato `Intersect` per restituire i contatti presenti in entrambe le tabelle.</span><span class="sxs-lookup"><span data-stu-id="3df01-115">This example uses `Intersect` to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### <a name="example"></a><span data-ttu-id="3df01-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="3df01-116">Example</span></span>  
 <span data-ttu-id="3df01-117">Nell'esempio seguente vengono confrontate due righe e ne vengono ottenuti i codici hash.</span><span class="sxs-lookup"><span data-stu-id="3df01-117">The following example compares two rows and gets their hash codes.</span></span>  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## <a name="see-also"></a><span data-ttu-id="3df01-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3df01-118">See Also</span></span>  
 <xref:System.Data.DataRowComparer>  
 [<span data-ttu-id="3df01-119">Caricamento di dati in un oggetto DataSet</span><span class="sxs-lookup"><span data-stu-id="3df01-119">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)  
 [<span data-ttu-id="3df01-120">Esempi di LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="3df01-120">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
