---
title: Come eseguire una query sui metadati di un assembly tramite reflection (LINQ) (C#)
description: Informazioni su come usare LINQ con le API di Reflection .NET in C# per recuperare metadati specifici sui metodi che corrispondono a un criterio di ricerca.
ms.date: 07/20/2015
ms.assetid: c4cdce49-b1c8-4420-b12a-9ff7e6671368
ms.openlocfilehash: dc5352e9cb90e9ad2808fb027823174d07d69da6
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104595"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-c"></a><span data-ttu-id="1a414-103">Come eseguire una query sui metadati di un assembly tramite reflection (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="1a414-103">How to query an assembly's metadata with Reflection (LINQ) (C#)</span></span>

<span data-ttu-id="1a414-104">È possibile utilizzare le API di Reflection .NET per esaminare i metadati in un assembly .NET e creare raccolte di tipi, membri dei tipi, parametri e così via che si trovano in tale assembly.</span><span class="sxs-lookup"><span data-stu-id="1a414-104">The .NET reflection APIs can be used to examine the metadata in a .NET assembly and create collections of types, type members, parameters, and so on that are in that assembly.</span></span> <span data-ttu-id="1a414-105">Poiché queste raccolte supportano l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>, è possibile eseguire query su tali raccolte tramite LINQ.</span><span class="sxs-lookup"><span data-stu-id="1a414-105">Because these collections support the generic <xref:System.Collections.Generic.IEnumerable%601> interface, they can be queried by using LINQ.</span></span>  
  
<span data-ttu-id="1a414-106">Nell'esempio seguente viene illustrato come LINQ può essere usato con il processo di reflection per recuperare metadati specifici sui metodi che corrispondono a un criterio di ricerca specificato.</span><span class="sxs-lookup"><span data-stu-id="1a414-106">The following example shows how LINQ can be used with reflection to retrieve specific metadata about methods that match a specified search criterion.</span></span> <span data-ttu-id="1a414-107">In questo caso la query individuerà i nomi di tutti i metodi dell'assembly che restituiscono tipi enumerabili, ad esempio matrici.</span><span class="sxs-lookup"><span data-stu-id="1a414-107">In this case, the query will find the names of all the methods in the assembly that return enumerable types such as arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a414-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="1a414-108">Example</span></span>  
  
```csharp  
using System;
using System.Linq;
using System.Reflection;  

class ReflectionHowTO  
{  
    static void Main()  
    {  
        Assembly assembly = Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089");  
        var pubTypesQuery = from type in assembly.GetTypes()  
                    where type.IsPublic  
                        from method in type.GetMethods()  
                        where method.ReturnType.IsArray == true
                            || ( method.ReturnType.GetInterface(  
                                typeof(System.Collections.Generic.IEnumerable<>).FullName ) != null  
                            && method.ReturnType.FullName != "System.String" )  
                        group method.ToString() by type.ToString();  

        foreach (var groupOfMethods in pubTypesQuery)  
        {  
            Console.WriteLine("Type: {0}", groupOfMethods.Key);  
            foreach (var method in groupOfMethods)  
            {  
                Console.WriteLine("  {0}", method);  
            }  
        }  

        Console.WriteLine("Press any key to exit... ");  
        Console.ReadKey();  
    }  
}
```  

<span data-ttu-id="1a414-109">L'esempio usa il metodo <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> per restituire una matrice di tipi nell'assembly specificato.</span><span class="sxs-lookup"><span data-stu-id="1a414-109">The example uses the <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> method to return an array of types in the specified assembly.</span></span> <span data-ttu-id="1a414-110">Il filtro [where](../../../language-reference/keywords/where-clause.md) viene applicato in modo che vengano restituiti solo i tipi pubblici.</span><span class="sxs-lookup"><span data-stu-id="1a414-110">The [where](../../../language-reference/keywords/where-clause.md) filter is applied so that only public types are returned.</span></span> <span data-ttu-id="1a414-111">Per ogni tipo pubblico, viene generata una sottoquery usando la matrice <xref:System.Reflection.MethodInfo> restituita dalla chiamata a <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1a414-111">For each public type, a subquery is generated by using the <xref:System.Reflection.MethodInfo> array that is returned from the <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> call.</span></span> <span data-ttu-id="1a414-112">Questi risultati vengono filtrati per restituire solo i metodi il cui tipo restituito è una matrice oppure un tipo che implementa <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="1a414-112">These results are filtered to return only those methods whose return type is an array or else a type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="1a414-113">Infine, questi risultati vengono raggruppati usando il nome del tipo come chiave.</span><span class="sxs-lookup"><span data-stu-id="1a414-113">Finally, these results are grouped by using the type name as a key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a414-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a414-114">See also</span></span>

- [<span data-ttu-id="1a414-115">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="1a414-115">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
