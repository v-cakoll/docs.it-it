---
title: Concatenamento di operatori di query standard (C#)
ms.date: 07/20/2015
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
ms.openlocfilehash: 37df654b2bfdcc135460e5ded2ceec1eca33b35a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204213"
---
# <a name="chaining-standard-query-operators-together-c"></a><span data-ttu-id="75b0a-102">Concatenamento di operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="75b0a-102">Chaining Standard Query Operators Together (C#)</span></span>
<span data-ttu-id="75b0a-103">Questo è l'argomento finale dell'[Esercitazione: concatenamento di query (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="75b0a-103">This is the final topic in the [Tutorial: Chaining Queries Together (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) tutorial.</span></span>  
  
 <span data-ttu-id="75b0a-104">È anche possibile concatenare gli operatori di query standard.</span><span class="sxs-lookup"><span data-stu-id="75b0a-104">The standard query operators can also be chained together.</span></span> <span data-ttu-id="75b0a-105">Ad esempio, è possibile inserire l'operatore <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> che opera anch'esso in modo lazy.</span><span class="sxs-lookup"><span data-stu-id="75b0a-105">For example, you can interject the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator, and it also operates in a lazy fashion.</span></span> <span data-ttu-id="75b0a-106">Questo operatore non materializza nessun risultato intermedio.</span><span class="sxs-lookup"><span data-stu-id="75b0a-106">No intermediate results are materialized by it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75b0a-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="75b0a-107">Example</span></span>  
 <span data-ttu-id="75b0a-108">In questo esempio viene chiamato il metodo <xref:System.Linq.Enumerable.Where%2A> prima della chiamata a `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="75b0a-108">In this example, the <xref:System.Linq.Enumerable.Where%2A> method is called before calling `ConvertCollectionToUpperCase`.</span></span> <span data-ttu-id="75b0a-109">Il metodo <xref:System.Linq.Enumerable.Where%2A> opera quasi esattamente allo stesso modo dei metodi lazy usati negli esempi precedenti di questa esercitazione, ovvero `ConvertCollectionToUpperCase` e `AppendString`.</span><span class="sxs-lookup"><span data-stu-id="75b0a-109">The <xref:System.Linq.Enumerable.Where%2A> method operates in almost exactly the same way as the lazy methods used in previous examples in this tutorial, `ConvertCollectionToUpperCase` and `AppendString`.</span></span>  
  
 <span data-ttu-id="75b0a-110">La differenza è che in questo caso il metodo <xref:System.Linq.Enumerable.Where%2A> scorre la raccolta di origine, determina che il primo elemento non passa il predicato, quindi ottiene l'elemento successivo, che invece passa.</span><span class="sxs-lookup"><span data-stu-id="75b0a-110">One difference is that in this case, the <xref:System.Linq.Enumerable.Where%2A> method iterates through its source collection, determines that the first item does not pass the predicate, and then gets the next item, which does pass.</span></span> <span data-ttu-id="75b0a-111">Infine restituisce il secondo elemento.</span><span class="sxs-lookup"><span data-stu-id="75b0a-111">It then yields the second item.</span></span>  
  
 <span data-ttu-id="75b0a-112">Tuttavia, l'idea di base è la stessa: le raccolte intermedie vengono materializzate solo se è necessario.</span><span class="sxs-lookup"><span data-stu-id="75b0a-112">However, the basic idea is the same: Intermediate collections are not materialized unless they have to be.</span></span>  
  
 <span data-ttu-id="75b0a-113">Quando si usano le espressioni di query, vengono convertite in chiamate agli operatori di query standard e si applicano gli stessi principi.</span><span class="sxs-lookup"><span data-stu-id="75b0a-113">When query expressions are used, they are converted to calls to the standard query operators, and the same principles apply.</span></span>  
  
 <span data-ttu-id="75b0a-114">Tutti gli esempi di questa sezione in cui vengono eseguite query su documenti Office Open XML si basano sullo stesso principio.</span><span class="sxs-lookup"><span data-stu-id="75b0a-114">All of the examples in this section that are querying Office Open XML documents use the same principle.</span></span> <span data-ttu-id="75b0a-115">Le idee di esecuzione posticipata e valutazione lazy sono alcuni dei concetti fondamentali che è necessario comprendere per usare LINQ e LINQ to XML in modo efficace.</span><span class="sxs-lookup"><span data-stu-id="75b0a-115">Deferred execution and lazy evaluation are some of the fundamental concepts that you must understand  to use LINQ (and LINQ to XML) effectively.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            where s.CompareTo("D") >= 0  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="75b0a-116">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="75b0a-116">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
