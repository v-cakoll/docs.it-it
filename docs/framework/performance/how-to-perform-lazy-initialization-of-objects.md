---
title: "Procedura: eseguire l'inizializzazione lenta di oggetti"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, how to perform
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
ms.openlocfilehash: 6efc89e5c22f53d9b2c48e535c783d488df16462
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130330"
---
# <a name="how-to-perform-lazy-initialization-of-objects"></a><span data-ttu-id="03f13-102">Procedura: eseguire l'inizializzazione lenta di oggetti</span><span class="sxs-lookup"><span data-stu-id="03f13-102">How to: Perform Lazy Initialization of Objects</span></span>
<span data-ttu-id="03f13-103">La classe <xref:System.Lazy%601?displayProperty=nameWithType> semplifica le operazioni di inizializzazione differita e creazione di istanze di oggetti.</span><span class="sxs-lookup"><span data-stu-id="03f13-103">The <xref:System.Lazy%601?displayProperty=nameWithType> class simplifies the work of performing lazy initialization and instantiation of objects.</span></span> <span data-ttu-id="03f13-104">L'inizializzazione di oggetti in modalità differita consente di evitare di doverli creare se non sono mai necessari oppure di posticiparne l'inizializzazione fino al primo accesso.</span><span class="sxs-lookup"><span data-stu-id="03f13-104">By initializing objects in a lazy manner, you can avoid having to create them at all if they are never needed, or you can postpone their initialization until they are first accessed.</span></span> <span data-ttu-id="03f13-105">Per altre informazioni, vedere [Inizializzazione differita](lazy-initialization.md).</span><span class="sxs-lookup"><span data-stu-id="03f13-105">For more information, see [Lazy Initialization](lazy-initialization.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03f13-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="03f13-106">Example</span></span>  
 <span data-ttu-id="03f13-107">L'esempio seguente mostra come inizializzare un valore con <xref:System.Lazy%601>.</span><span class="sxs-lookup"><span data-stu-id="03f13-107">The following example shows how to initialize a value with <xref:System.Lazy%601>.</span></span> <span data-ttu-id="03f13-108">Partire dal presupposto che la variabile differita potrebbe non essere necessaria, a seconda che esista altro codice che imposta la variabile `someCondition` su true o false.</span><span class="sxs-lookup"><span data-stu-id="03f13-108">Assume that the lazy variable might not be needed, depending on some other code that sets the `someCondition` variable to true or false.</span></span>  
  
```vb  
Dim someCondition As Boolean = False  
  
Sub Main()  
    'Initializing a value with a big computation, computed in parallel  
    Dim _data As Lazy(Of Integer) = New Lazy(Of Integer)(Function()  
                                                             Dim result =  
                                                                 ParallelEnumerable.Range(0, 1000).  
                                                                 Aggregate(Function(x, y)  
                                                                               Return x + y  
                                                                           End Function)  
                                                             Return result  
                                                         End Function)  
  
    '  do work that may or may not set someCondition to True  
    ' ...  
    '  Initialize the data only if needed  
    If someCondition = True Then  
  
        If (_data.Value > 100) Then  
  
            Console.WriteLine("Good data")  
        End If  
    End If  
End Sub  
```  
  
```csharp  
  static bool someCondition = false;    
  //Initializing a value with a big computation, computed in parallel  
  Lazy<int> _data = new Lazy<int>(delegate  
  {  
      return ParallelEnumerable.Range(0, 1000).  
          Select(i => Compute(i)).Aggregate((x,y) => x + y);  
  }, LazyExecutionMode.EnsureSingleThreadSafeExecution);  
  
  // Do some work that may or may not set someCondition to true.  
  //  ...  
  // Initialize the data only if necessary  
  if (someCondition)  
  {  
    if (_data.Value > 100)  
      {  
          Console.WriteLine("Good data");  
      }  
  }  
```  
  
## <a name="example"></a><span data-ttu-id="03f13-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="03f13-109">Example</span></span>  
 <span data-ttu-id="03f13-110">L'esempio seguente mostra come usare la classe <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> per inizializzare un tipo visibile solo per l'istanza dell'oggetto corrente nel thread corrente.</span><span class="sxs-lookup"><span data-stu-id="03f13-110">The following example shows how to use the <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> class to initialize a type that is visible only to the current object instance on the current thread.</span></span>  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="03f13-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="03f13-111">See also</span></span>

- <xref:System.Threading.LazyInitializer?displayProperty=nameWithType>
- [<span data-ttu-id="03f13-112">Inizializzazione differita</span><span class="sxs-lookup"><span data-stu-id="03f13-112">Lazy Initialization</span></span>](lazy-initialization.md)
