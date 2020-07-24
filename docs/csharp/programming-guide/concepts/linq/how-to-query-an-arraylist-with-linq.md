---
title: Come eseguire una query su un ArrayList con LINQ (C#)
description: Questo esempio USA LINQ per eseguire query su un ArrayList in C#. È necessario dichiarare il tipo della variabile di intervallo in modo che corrisponda al tipo degli oggetti nella raccolta.
ms.date: 07/20/2015
ms.assetid: 2bfb471c-6e9a-4e60-bd83-4a1778abde11
ms.openlocfilehash: 5c251e17de062a4578f06fc1a40ea3ede9f3ab67
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104598"
---
# <a name="how-to-query-an-arraylist-with-linq-c"></a><span data-ttu-id="c773c-104">Come eseguire una query su un ArrayList con LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="c773c-104">How to query an ArrayList with LINQ (C#)</span></span>
<span data-ttu-id="c773c-105">Quando si usa LINQ per eseguire una query su raccolte <xref:System.Collections.IEnumerable> non generiche, ad esempio <xref:System.Collections.ArrayList>, è necessario dichiarare in modo esplicito il tipo della variabile di intervallo in base al tipo specifico di oggetti nella raccolta.</span><span class="sxs-lookup"><span data-stu-id="c773c-105">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="c773c-106">Ad esempio, con un <xref:System.Collections.ArrayList> di oggetti `Student`, la [clausola from](../../../language-reference/keywords/from-clause.md) sarà simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="c773c-106">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [from clause](../../../language-reference/keywords/from-clause.md) should look like this:</span></span>  
  
```csharp
var query = from Student s in arrList  
//...
```  
  
 <span data-ttu-id="c773c-107">Specificando il tipo della variabile di intervallo, si esegue il cast di ogni elemento di <xref:System.Collections.ArrayList> in `Student`.</span><span class="sxs-lookup"><span data-stu-id="c773c-107">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>  
  
 <span data-ttu-id="c773c-108">L'uso di una variabile di intervallo tipizzata in modo esplicito in un'espressione di query è equivalente alla chiamata del metodo <xref:System.Linq.Enumerable.Cast%2A>.</span><span class="sxs-lookup"><span data-stu-id="c773c-108">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="c773c-109"><xref:System.Linq.Enumerable.Cast%2A> genera un'eccezione se non è possibile eseguire il cast specificato.</span><span class="sxs-lookup"><span data-stu-id="c773c-109"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="c773c-110"><xref:System.Linq.Enumerable.Cast%2A> e <xref:System.Linq.Enumerable.OfType%2A> sono i due metodi dell'operatore query standard che operano sui tipi <xref:System.Collections.IEnumerable> non generici.</span><span class="sxs-lookup"><span data-stu-id="c773c-110"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="c773c-111">Per altre informazioni, vedere [relazioni tra i tipi nelle operazioni di query LINQ](./type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="c773c-111">For more information, see [Type Relationships in LINQ Query Operations](./type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c773c-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="c773c-112">Example</span></span>  
 <span data-ttu-id="c773c-113">L'esempio seguente mostra una query semplice su un oggetto <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="c773c-113">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="c773c-114">Si noti che questo esempio usa gli inizializzatori di oggetto quando il codice chiama il metodo <xref:System.Collections.ArrayList.Add%2A>, anche se non si tratta di un requisito.</span><span class="sxs-lookup"><span data-stu-id="c773c-114">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Linq;  
  
namespace NonGenericLINQ  
{  
    public class Student  
    {  
        public string FirstName { get; set; }  
        public string LastName { get; set; }  
        public int[] Scores { get; set; }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ArrayList arrList = new ArrayList();  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Svetlana", LastName = "Omelchenko", Scores = new int[] { 98, 92, 81, 60 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Claire", LastName = "O’Donnell", Scores = new int[] { 75, 84, 91, 39 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Sven", LastName = "Mortensen", Scores = new int[] { 88, 94, 65, 91 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Cesar", LastName = "Garcia", Scores = new int[] { 97, 89, 85, 82 }  
                    });  
  
            var query = from Student student in arrList  
                        where student.Scores[0] > 95  
                        select student;  
  
            foreach (Student s in query)  
                Console.WriteLine(s.LastName + ": " + s.Scores[0]);  
  
            // Keep the console window open in debug mode.  
            Console.WriteLine("Press any key to exit.");  
            Console.ReadKey();  
        }  
    }  
}  
/* Output:
    Omelchenko: 98  
    Garcia: 97  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="c773c-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c773c-115">See also</span></span>

- [<span data-ttu-id="c773c-116">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="c773c-116">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
