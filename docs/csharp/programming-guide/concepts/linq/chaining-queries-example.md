---
title: Esempio di concatenamento di query (C#)
description: Questo esempio mostra cosa accade quando si concatenano due query che usano l'esecuzione posticipata e la valutazione lazy in C#.
ms.date: 07/20/2015
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
ms.openlocfilehash: 0cfcfe1c8f537778fd1ef909277d95d83991af51
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105539"
---
# <a name="chaining-queries-example-c"></a><span data-ttu-id="e7076-103">Esempio di concatenamento di query (C#)</span><span class="sxs-lookup"><span data-stu-id="e7076-103">Chaining Queries Example (C#)</span></span>
<span data-ttu-id="e7076-104">In questo esempio, basato sull'esempio precedente, vengono illustrati gli effetti del concatenamento di due query che usano l'esecuzione posticipata e la valutazione lazy.</span><span class="sxs-lookup"><span data-stu-id="e7076-104">This example builds on the previous example and shows what happens when you chain together two queries that both use deferred execution and lazy evaluation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7076-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="e7076-105">Example</span></span>  
 <span data-ttu-id="e7076-106">In questo esempio viene introdotto un altro metodo di estensione, `AppendString`, che aggiunge una stringa specificata a ogni stringa della raccolta di origine e quindi restituisce le nuove stringhe.</span><span class="sxs-lookup"><span data-stu-id="e7076-106">In this example, another extension method is introduced, `AppendString`, which appends a specified string onto every string in the source collection, and then yields the new strings.</span></span>  
  
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
  
 <span data-ttu-id="e7076-107">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="e7076-107">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="e7076-108">In questo esempio è possibile osservare che i metodi di estensione operano uno alla volta per ogni elemento della raccolta di origine.</span><span class="sxs-lookup"><span data-stu-id="e7076-108">In this example, you can see that each extension method operates one at a time for each item in the source collection.</span></span>  
  
 <span data-ttu-id="e7076-109">Scopo di questo esempio è dimostrare che, anche se le query che restituiscono le raccolte sono state concatenate, non vengono materializzate raccolte intermedie.</span><span class="sxs-lookup"><span data-stu-id="e7076-109">What should be clear from this example is that even though we have chained together queries that yield collections, no intermediate collections are materialized.</span></span> <span data-ttu-id="e7076-110">Al contrario, ogni elemento viene passato da un metodo lazy al successivo.</span><span class="sxs-lookup"><span data-stu-id="e7076-110">Instead, each item is passed from one lazy method to the next.</span></span> <span data-ttu-id="e7076-111">Il risultato è un footprint di memoria molto più piccolo rispetto a quello di un approccio che prevede di prendere una matrice di stringhe, quindi creare una seconda matrice di stringhe che sono state convertite in maiuscolo e infine creare una terza matrice di stringhe in cui alla fine di ogni stringa è stato aggiunto un punto esclamativo.</span><span class="sxs-lookup"><span data-stu-id="e7076-111">This results in a much smaller memory footprint than an approach that would first take one array of strings, then create a second array of strings that have been converted to uppercase, and finally create a third array of strings where each string has the exclamation points appended to it.</span></span>  
  
 <span data-ttu-id="e7076-112">Nell'argomento successivo di questa esercitazione viene illustrata la materializzazione intermedia:</span><span class="sxs-lookup"><span data-stu-id="e7076-112">The next topic in this tutorial illustrates intermediate materialization:</span></span>  
  
- [<span data-ttu-id="e7076-113">Materializzazione intermedia (C#)</span><span class="sxs-lookup"><span data-stu-id="e7076-113">Intermediate Materialization (C#)</span></span>](./intermediate-materialization.md)  
  
## <a name="see-also"></a><span data-ttu-id="e7076-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e7076-114">See also</span></span>

- [<span data-ttu-id="e7076-115">Esercitazione: Concatenamento di query (C#)</span><span class="sxs-lookup"><span data-stu-id="e7076-115">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
