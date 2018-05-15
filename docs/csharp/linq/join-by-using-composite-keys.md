---
title: Eseguire un join usando chiavi composte
description: Come creare un join usando un chiavi composte
ms.date: 12/1/2016
ms.assetid: da70b54d-3213-45eb-8437-fbe75cbcf935
ms.openlocfilehash: e40f4d147886c07913c761bb5df83ee34d23eaba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="join-by-using-composite-keys"></a><span data-ttu-id="e8cde-103">Eseguire un join usando chiavi composte</span><span class="sxs-lookup"><span data-stu-id="e8cde-103">Join by using composite keys</span></span>

<span data-ttu-id="e8cde-104">In questo esempio viene illustrato come eseguire operazioni di join in cui si vuole usare più di una chiave per definire una corrispondenza.</span><span class="sxs-lookup"><span data-stu-id="e8cde-104">This example shows how to perform join operations in which you want to use more than one key to define a match.</span></span> <span data-ttu-id="e8cde-105">Ciò è possibile usando una chiave composta,</span><span class="sxs-lookup"><span data-stu-id="e8cde-105">This is accomplished by using a composite key.</span></span> <span data-ttu-id="e8cde-106">che viene creata come tipo anonimo o tipo denominato con i valori che si vogliono confrontare.</span><span class="sxs-lookup"><span data-stu-id="e8cde-106">You create a composite key as an anonymous type or named typed with the values that you want to compare.</span></span> <span data-ttu-id="e8cde-107">Se la variabile di query viene passata attraverso i limiti del metodo, usare un tipo denominato che esegue l'override di <xref:System.Object.Equals%2A> e <xref:System.Object.GetHashCode%2A> per la chiave.</span><span class="sxs-lookup"><span data-stu-id="e8cde-107">If the query variable will be passed across method boundaries, use a named type that overrides <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> for the key.</span></span> <span data-ttu-id="e8cde-108">I nomi delle proprietà e l'ordine in cui si verificano devono essere identici in ogni chiave.</span><span class="sxs-lookup"><span data-stu-id="e8cde-108">The names of the properties, and the order in which they occur, must be identical in each key.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8cde-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e8cde-109">Example</span></span>  
 <span data-ttu-id="e8cde-110">Nell'esempio seguente viene illustrato come usare una chiave composta per eseguire un join dei dati da tre tabelle:</span><span class="sxs-lookup"><span data-stu-id="e8cde-110">The following example demonstrates how to use a composite key to join data from three tables:</span></span>  
  
```csharp  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,        d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 <span data-ttu-id="e8cde-111">L'inferenza del tipo nelle chiavi composte dipende dai nomi delle proprietà nelle chiavi e dall'ordine in cui si verificano.</span><span class="sxs-lookup"><span data-stu-id="e8cde-111">Type inference on composite keys depends on the names of the properties in the keys, and the order in which they occur.</span></span> <span data-ttu-id="e8cde-112">Se le proprietà nelle sequenze di origine non contengono gli stessi nomi, è necessario assegnare nuovi nomi nelle chiavi.</span><span class="sxs-lookup"><span data-stu-id="e8cde-112">If the properties in the source sequences do not have the same names, you must assign new names in the keys.</span></span> <span data-ttu-id="e8cde-113">Ad esempio, se nella tabella `Orders` e nella tabella `OrderDetails` vengono usati nomi diversi per le colonne, è possibile creare chiavi composte assegnando nomi identici nei tipi anonimi:</span><span class="sxs-lookup"><span data-stu-id="e8cde-113">For example, if the `Orders` table and `OrderDetails` table each used different names for their columns, you could create composite keys by assigning identical names in the anonymous types:</span></span>  
  
```csharp  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 <span data-ttu-id="e8cde-114">Le chiavi composte possono essere usate anche nella clausola `group`.</span><span class="sxs-lookup"><span data-stu-id="e8cde-114">Composite keys can be also used in a `group` clause.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e8cde-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e8cde-115">See also</span></span>  
 [<span data-ttu-id="e8cde-116">Espressioni di query LINQ</span><span class="sxs-lookup"><span data-stu-id="e8cde-116">LINQ query expressions</span></span>](index.md)  
 [<span data-ttu-id="e8cde-117">Clausola join</span><span class="sxs-lookup"><span data-stu-id="e8cde-117">join clause</span></span>](../language-reference/keywords/join-clause.md)  
 [<span data-ttu-id="e8cde-118">Clausola group</span><span class="sxs-lookup"><span data-stu-id="e8cde-118">group clause</span></span>](../language-reference/keywords/group-clause.md)
