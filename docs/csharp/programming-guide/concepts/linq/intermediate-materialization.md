---
title: Materializzazione intermedia (C#)
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: af1eb7df7da02d8e72fc102cda4ee5f329dc7974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253155"
---
# <a name="intermediate-materialization-c"></a><span data-ttu-id="518da-102">Materializzazione intermedia (C#)</span><span class="sxs-lookup"><span data-stu-id="518da-102">Intermediate Materialization (C#)</span></span>
<span data-ttu-id="518da-103">Se non si presta la dovuta attenzione, in alcune situazioni è possibile modificare drasticamente il profilo di memoria e prestazioni dell'applicazione, generando la materializzazione prematura delle raccolte nelle query.</span><span class="sxs-lookup"><span data-stu-id="518da-103">If you are not careful, in some situations you can drastically alter the memory and performance profile of your application by causing premature materialization of collections in your queries.</span></span> <span data-ttu-id="518da-104">Alcuni operatori di query standard provocano la materializzazione della propria raccolta di origine prima di restituire un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="518da-104">Some standard query operators cause materialization of their source collection before yielding a single element.</span></span> <span data-ttu-id="518da-105">Ad esempio, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> scorre l'intera raccolta di origine, quindi ordina tutti gli elementi e infine restituisce il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="518da-105">For example, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> first iterates through its entire source collection, then sorts all items, and then finally yields the first item.</span></span> <span data-ttu-id="518da-106">Questo significa che ottenere il primo elemento di una raccolta ordinata è costoso, mentre ogni elemento successivo non lo è.</span><span class="sxs-lookup"><span data-stu-id="518da-106">This means that it is expensive to get the first item of an ordered collection; each item thereafter is not expensive.</span></span> <span data-ttu-id="518da-107">Questo comportamento è normale: sarebbe impossibile per questo operatore di query fare altrimenti.</span><span class="sxs-lookup"><span data-stu-id="518da-107">This makes sense: It would be impossible for that query operator to do otherwise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="518da-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="518da-108">Example</span></span>  
 <span data-ttu-id="518da-109">In questo esempio viene modificato l'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="518da-109">This example alters the previous example.</span></span> <span data-ttu-id="518da-110">Il metodo `AppendString` chiama <xref:System.Linq.Enumerable.ToList%2A> prima di scorrere l'origine.</span><span class="sxs-lookup"><span data-stu-id="518da-110">The `AppendString` method calls <xref:System.Linq.Enumerable.ToList%2A> before iterating through the source.</span></span> <span data-ttu-id="518da-111">Ciò provoca la materializzazione.</span><span class="sxs-lookup"><span data-stu-id="518da-111">This causes materialization.</span></span>  
  
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
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
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
  
 <span data-ttu-id="518da-112">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="518da-112">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="518da-113">In questo esempio è possibile osservare che tramite la chiamata a <xref:System.Linq.Enumerable.ToList%2A>, `AppendString` enumera l'origine intera prima di restituire il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="518da-113">In this example, you can see that the call to <xref:System.Linq.Enumerable.ToList%2A> causes `AppendString` to enumerate its entire source before yielding the first item.</span></span> <span data-ttu-id="518da-114">Se l'origine fosse una matrice di grandi dimensioni, il profilo di memoria dell'applicazione verrebbe modificato in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="518da-114">If the source were a large array, this would significantly alter the memory profile of the application.</span></span>  
  
 <span data-ttu-id="518da-115">Gli operatori di query standard possono anche essere concatenati.</span><span class="sxs-lookup"><span data-stu-id="518da-115">Standard query operators can also be chained together.</span></span> <span data-ttu-id="518da-116">Nell'argomento finale dell'esercitazione verrà illustrato questo aspetto.</span><span class="sxs-lookup"><span data-stu-id="518da-116">The final topic in this tutorial illustrates this.</span></span>  
  
- [<span data-ttu-id="518da-117">Concatenamento di operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="518da-117">Chaining Standard Query Operators Together (C#)</span></span>](./chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a><span data-ttu-id="518da-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="518da-118">See also</span></span>

- [<span data-ttu-id="518da-119">Esercitazione: Concatenamento di query (C#)</span><span class="sxs-lookup"><span data-stu-id="518da-119">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
