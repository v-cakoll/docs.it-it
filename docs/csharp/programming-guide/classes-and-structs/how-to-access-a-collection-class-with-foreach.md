---
title: 'Procedura: accedere a una classe Collection con foreach (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection classes [C#], foreach statement
ms.assetid: a6b9cf5c-6c8d-4223-b12c-288949434493
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2ad81ab699b079f4aabb04a886211e94a937335d
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-a-collection-class-with-foreach-c-programming-guide"></a><span data-ttu-id="cf6e0-102">Procedura: accedere a una classe Collection con foreach (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="cf6e0-102">How to: Access a Collection Class with foreach (C# Programming Guide)</span></span>
<span data-ttu-id="cf6e0-103">Nell'esempio di codice seguente viene illustrato come scrivere una classe Collection non generica che può essere usata con [foreach](../../../csharp/language-reference/keywords/foreach-in.md) e</span><span class="sxs-lookup"><span data-stu-id="cf6e0-103">The following code example illustrates how to write a non-generic collection class that can be used with [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span></span> <span data-ttu-id="cf6e0-104">viene definita una classe tokenizer di stringa.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-104">The example defines a string tokenizer class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf6e0-105">La procedura riportata in questo esempio è consigliata solo quando non è possibile usare una classe Collection generica.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-105">This example represents recommended practice only when you cannot use a generic collection class.</span></span> <span data-ttu-id="cf6e0-106">Per un esempio di come implementare una classe Collection generica indipendente dai tipi che supporta <xref:System.Collections.Generic.IEnumerable%601>, vedere [Iteratori](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span><span class="sxs-lookup"><span data-stu-id="cf6e0-106">For an example of how to implement a type-safe generic collection class that supports <xref:System.Collections.Generic.IEnumerable%601>, see [Iterators](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).</span></span>  
  
 <span data-ttu-id="cf6e0-107">Nell'esempio il segmento di codice seguente usa la classe `Tokens` per suddividere la frase "This is a sample sentence"</span><span class="sxs-lookup"><span data-stu-id="cf6e0-107">In the example, the following code segment uses the `Tokens` class to break the sentence "This is a sample sentence."</span></span> <span data-ttu-id="cf6e0-108">in token usando ' ' e '-' come separatori.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-108">into tokens by using ' ' and '-' as separators.</span></span> <span data-ttu-id="cf6e0-109">Il codice consente di visualizzare tali token tramite un'istruzione `foreach`.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-109">The code then displays those tokens by using a `foreach` statement.</span></span>  
  
 <span data-ttu-id="cf6e0-110">[!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf6e0-110">[!code-cs[csProgGuideCollections#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf6e0-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="cf6e0-111">Example</span></span>  
 <span data-ttu-id="cf6e0-112">Internamente la classe `Tokens` usa una matrice per archiviare i token.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-112">Internally, the `Tokens` class uses an array to store the tokens.</span></span> <span data-ttu-id="cf6e0-113">Poiché le matrici implementano <xref:System.Collections.IEnumerator> e <xref:System.Collections.IEnumerable>, l'esempio di codice avrebbe potuto usare i metodi di enumerazione della matrice (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> e <xref:System.Collections.IEnumerator.Current%2A>) invece di definirli nella classe `Tokens`.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-113">Because arrays implement <xref:System.Collections.IEnumerator> and <xref:System.Collections.IEnumerable>, the code example could have used the array's enumeration methods (<xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A>) instead of defining them in the `Tokens` class.</span></span> <span data-ttu-id="cf6e0-114">Le definizioni dei metodi sono incluse nell'esempio per chiarire come vengono definiti i metodi e lo scopo di ognuno di essi.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-114">The method definitions are included in the example to clarify how they are defined and what each does.</span></span>  
  
 <span data-ttu-id="cf6e0-115">[!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="cf6e0-115">[!code-cs[csProgGuideCollections#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-access-a-collection-class-with-foreach_2.cs)]</span></span>  
  
 <span data-ttu-id="cf6e0-116">In C# non è necessario che una classe Collection implementi <xref:System.Collections.IEnumerable> e <xref:System.Collections.IEnumerator> per essere compatibile con `foreach`.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-116">In C#, it is not necessary for a collection class to implement <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> to be compatible with `foreach`.</span></span> <span data-ttu-id="cf6e0-117">Se la classe ha i membri <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A> e <xref:System.Collections.IEnumerator.Current%2A> necessari, funzionerà con `foreach`.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-117">If the class has the required <xref:System.Collections.IEnumerable.GetEnumerator%2A>, <xref:System.Collections.IEnumerator.MoveNext%2A>, <xref:System.Collections.IEnumerator.Reset%2A>, and <xref:System.Collections.IEnumerator.Current%2A> members, it will work with `foreach`.</span></span> <span data-ttu-id="cf6e0-118">L'omissione delle interfacce offre il vantaggio di poter definire un tipo restituito per `Current` più specifico di <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-118">Omitting the interfaces has the advantage of enabling you to define a return type for `Current` that is more specific than <xref:System.Object>.</span></span> <span data-ttu-id="cf6e0-119">In questo modo viene garantita l'indipendenza dai tipi.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-119">This provides type safety.</span></span>  
  
 <span data-ttu-id="cf6e0-120">Modificare ad esempio le righe seguenti dell'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-120">For example, change the following lines in the previous example.</span></span>  
  
```csharp  
// Change the Tokens class so that it no longer implements IEnumerable.  
public class Tokens  
{  
    // . . .  
  
    // Change the return type for the GetEnumerator method.  
    public TokenEnumerator GetEnumerator()  
    {   }  
  
    // Change TokenEnumerator so that it no longer implements IEnumerator.  
    public class TokenEnumerator  
    {  
        // . . .  
  
        // Change the return type of method Current to string.  
        public string Current  
        {   }  
    }  
 }  
```  
  
 <span data-ttu-id="cf6e0-121">Poiché `Current` restituisce una stringa, il compilatore può rilevare l'eventuale uso di un tipo non compatibile in un'istruzione `foreach`, come illustrato nel codice seguente.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-121">Because `Current` returns a string, the compiler can detect when an incompatible type is used in a `foreach` statement, as shown in the following code.</span></span>  
  
```csharp  
// Error: Cannot convert type string to int.  
foreach (int item in f)    
```  
  
 <span data-ttu-id="cf6e0-122">L'omissione di <xref:System.Collections.IEnumerable> e <xref:System.Collections.IEnumerator> impedisce però l'interoperabilità della classe Collection con le istruzioni `foreach` o con istruzioni equivalenti, di altri linguaggi compatibili con Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cf6e0-122">The disadvantage of omitting <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> is that the collection class is no longer interoperable with the `foreach` statements, or equivalent statements, of other common language runtime languages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf6e0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf6e0-123">See Also</span></span>  
 <span data-ttu-id="cf6e0-124"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="cf6e0-124"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="cf6e0-125">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf6e0-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="cf6e0-126">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf6e0-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="cf6e0-127">[Matrici](../../../csharp/programming-guide/arrays/index.md) </span><span class="sxs-lookup"><span data-stu-id="cf6e0-127">[Arrays](../../../csharp/programming-guide/arrays/index.md) </span></span>  
 [<span data-ttu-id="cf6e0-128">Raccolte</span><span class="sxs-lookup"><span data-stu-id="cf6e0-128">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)

