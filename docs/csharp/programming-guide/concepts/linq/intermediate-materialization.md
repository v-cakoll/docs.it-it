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
# <a name="intermediate-materialization-c"></a>Materializzazione intermedia (C#)
Se non si presta la dovuta attenzione, in alcune situazioni è possibile modificare drasticamente il profilo di memoria e prestazioni dell'applicazione, generando la materializzazione prematura delle raccolte nelle query. Alcuni operatori di query standard provocano la materializzazione della propria raccolta di origine prima di restituire un solo elemento. Ad esempio, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> scorre l'intera raccolta di origine, quindi ordina tutti gli elementi e infine restituisce il primo elemento. Questo significa che ottenere il primo elemento di una raccolta ordinata è costoso, mentre ogni elemento successivo non lo è. Questo comportamento è normale: sarebbe impossibile per questo operatore di query fare altrimenti.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene modificato l'esempio precedente. Il metodo `AppendString` chiama <xref:System.Linq.Enumerable.ToList%2A> prima di scorrere l'origine. Ciò provoca la materializzazione.  
  
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
  
 Nell'esempio viene prodotto l'output seguente:  
  
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
  
 In questo esempio è possibile osservare che tramite la chiamata a <xref:System.Linq.Enumerable.ToList%2A>, `AppendString` enumera l'origine intera prima di restituire il primo elemento. Se l'origine fosse una matrice di grandi dimensioni, il profilo di memoria dell'applicazione verrebbe modificato in modo significativo.  
  
 Gli operatori di query standard possono anche essere concatenati. Nell'argomento finale dell'esercitazione verrà illustrato questo aspetto.  
  
- [Concatenamento di operatori di query standard (C#)](./chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a>Vedere anche

- [Esercitazione: Concatenamento di query (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
