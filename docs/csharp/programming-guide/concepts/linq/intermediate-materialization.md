---
title: Materializzazione intermedia (C#)
description: Questo esempio C# Mostra la materializzazione intermedia, in cui una query fa in modo che AppendString enumera l'intera origine prima di restituire il primo elemento.
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: 30951aaeea261efbd414205bcc54b63106324344
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165722"
---
# <a name="intermediate-materialization-c"></a><span data-ttu-id="6e4b8-103">Materializzazione intermedia (C#)</span><span class="sxs-lookup"><span data-stu-id="6e4b8-103">Intermediate Materialization (C#)</span></span>
<span data-ttu-id="6e4b8-104">Se non si presta la dovuta attenzione, in alcune situazioni è possibile modificare drasticamente il profilo di memoria e prestazioni dell'applicazione, generando la materializzazione prematura delle raccolte nelle query.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-104">If you are not careful, in some situations you can drastically alter the memory and performance profile of your application by causing premature materialization of collections in your queries.</span></span> <span data-ttu-id="6e4b8-105">Alcuni operatori di query standard provocano la materializzazione della propria raccolta di origine prima di restituire un solo elemento.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-105">Some standard query operators cause materialization of their source collection before yielding a single element.</span></span> <span data-ttu-id="6e4b8-106">Ad esempio, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> scorre l'intera raccolta di origine, quindi ordina tutti gli elementi e infine restituisce il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-106">For example, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> first iterates through its entire source collection, then sorts all items, and then finally yields the first item.</span></span> <span data-ttu-id="6e4b8-107">Questo significa che ottenere il primo elemento di una raccolta ordinata è costoso, mentre ogni elemento successivo non lo è.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-107">This means that it is expensive to get the first item of an ordered collection; each item thereafter is not expensive.</span></span> <span data-ttu-id="6e4b8-108">Questo comportamento è normale: sarebbe impossibile per questo operatore di query fare altrimenti.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-108">This makes sense: It would be impossible for that query operator to do otherwise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e4b8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e4b8-109">Example</span></span>  
 <span data-ttu-id="6e4b8-110">In questo esempio viene modificato l'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-110">This example alters the previous example.</span></span> <span data-ttu-id="6e4b8-111">Il metodo `AppendString` chiama <xref:System.Linq.Enumerable.ToList%2A> prima di scorrere l'origine.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-111">The `AppendString` method calls <xref:System.Linq.Enumerable.ToList%2A> before iterating through the source.</span></span> <span data-ttu-id="6e4b8-112">Ciò provoca la materializzazione.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-112">This causes materialization.</span></span>  
  
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
  
 <span data-ttu-id="6e4b8-113">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="6e4b8-113">This example produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="6e4b8-114">In questo esempio è possibile osservare che tramite la chiamata a <xref:System.Linq.Enumerable.ToList%2A>, `AppendString` enumera l'origine intera prima di restituire il primo elemento.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-114">In this example, you can see that the call to <xref:System.Linq.Enumerable.ToList%2A> causes `AppendString` to enumerate its entire source before yielding the first item.</span></span> <span data-ttu-id="6e4b8-115">Se l'origine fosse una matrice di grandi dimensioni, il profilo di memoria dell'applicazione verrebbe modificato in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-115">If the source were a large array, this would significantly alter the memory profile of the application.</span></span>  
  
 <span data-ttu-id="6e4b8-116">Gli operatori di query standard possono anche essere concatenati.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-116">Standard query operators can also be chained together.</span></span> <span data-ttu-id="6e4b8-117">Nell'argomento finale dell'esercitazione verrà illustrato questo aspetto.</span><span class="sxs-lookup"><span data-stu-id="6e4b8-117">The final topic in this tutorial illustrates this.</span></span>  
  
- [<span data-ttu-id="6e4b8-118">Concatenamento di operatori di query standard (C#)</span><span class="sxs-lookup"><span data-stu-id="6e4b8-118">Chaining Standard Query Operators Together (C#)</span></span>](./chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a><span data-ttu-id="6e4b8-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e4b8-119">See also</span></span>

- [<span data-ttu-id="6e4b8-120">Esercitazione: Concatenamento di query (C#)</span><span class="sxs-lookup"><span data-stu-id="6e4b8-120">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
