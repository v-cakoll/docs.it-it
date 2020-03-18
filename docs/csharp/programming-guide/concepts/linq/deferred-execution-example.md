---
title: Esempio di esecuzione posticipata (C#)
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 0816594ad016f19af4c97198160b4bafb9b4b8b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "70204126"
---
# <a name="deferred-execution-example-c"></a><span data-ttu-id="d5664-102">Esempio di esecuzione posticipata (C#)</span><span class="sxs-lookup"><span data-stu-id="d5664-102">Deferred Execution Example (C#)</span></span>
<span data-ttu-id="d5664-103">In questo argomento vengono illustrati gli effetti dell'esecuzione posticipata e della valutazione lazy sulle query LINQ to XML.</span><span class="sxs-lookup"><span data-stu-id="d5664-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5664-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d5664-104">Example</span></span>  
 <span data-ttu-id="d5664-105">Nell'esempio seguente è illustrato l'ordine di esecuzione quando si usa un metodo di estensione basato su esecuzione posticipata.</span><span class="sxs-lookup"><span data-stu-id="d5664-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="d5664-106">Viene dichiarata una matrice di tre stringhe.</span><span class="sxs-lookup"><span data-stu-id="d5664-106">The example declares an array of three strings.</span></span> <span data-ttu-id="d5664-107">Viene quindi scorsa la raccolta restituita da `ConvertCollectionToUpperCase`.</span><span class="sxs-lookup"><span data-stu-id="d5664-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 <span data-ttu-id="d5664-108">Nell'esempio viene prodotto l'output seguente:</span><span class="sxs-lookup"><span data-stu-id="d5664-108">This example produces the following output:</span></span>  
  
```output  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="d5664-109">Si noti che quando si scorre la raccolta restituita da `ConvertCollectionToUpperCase`, ogni elemento viene recuperato dalla matrice di stringhe di origine e viene convertito in lettere maiuscole prima del recupero dell'elemento successivo.</span><span class="sxs-lookup"><span data-stu-id="d5664-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="d5664-110">L'intera matrice di stringhe non viene convertita in lettere maiuscole prima dell'elaborazione nel ciclo `foreach` di `Main` di ogni elemento della raccolta restituita.</span><span class="sxs-lookup"><span data-stu-id="d5664-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
 <span data-ttu-id="d5664-111">Nell'argomento successivo di questa esercitazione viene illustrato il concatenamento di query:</span><span class="sxs-lookup"><span data-stu-id="d5664-111">The next topic in this tutorial illustrates chaining queries together:</span></span>  
  
- [<span data-ttu-id="d5664-112">Esempio di concatenamento di query (C#)</span><span class="sxs-lookup"><span data-stu-id="d5664-112">Chaining Queries Example (C#)</span></span>](./chaining-queries-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="d5664-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5664-113">See also</span></span>

- [<span data-ttu-id="d5664-114">Esercitazione: Concatenamento di query (C#)</span><span class="sxs-lookup"><span data-stu-id="d5664-114">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
