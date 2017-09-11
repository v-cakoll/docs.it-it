---
title: Generics e attributi (Guida per programmatori C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
caps.latest.revision: 13
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
ms.openlocfilehash: 5136ae928a3a4b6f8ec4d86100d695f958d55858
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="efd9c-102">Generics e attributi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="efd9c-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="efd9c-103">Gli attributi possono essere applicati a tipi generici allo stesso modo che ai tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="efd9c-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="efd9c-104">Per altre informazioni sull'applicazione di attributi, vedere [Attributi](../../../csharp/programming-guide/concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="efd9c-104">For more information on applying attributes, see [Attributes](../../../csharp/programming-guide/concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="efd9c-105">Gli attributi personalizzati sono consentiti solo per fare riferimento a tipi generici aperti, che sono tipi generici per cui non è specificato alcun argomento tipo, e tipi generici costruiti chiusi, che specificano argomenti per tutti i parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="efd9c-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="efd9c-106">Gli esempi seguenti usano questo attributo personalizzato:</span><span class="sxs-lookup"><span data-stu-id="efd9c-106">The following examples use this custom attribute:</span></span>  
  
 <span data-ttu-id="efd9c-107">[!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="efd9c-107">[!code-cs[csProgGuideGenerics#48](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_1.cs)]</span></span>  
  
 <span data-ttu-id="efd9c-108">Un attributo può fare riferimento a un tipo generico aperto:</span><span class="sxs-lookup"><span data-stu-id="efd9c-108">An attribute can reference an open generic type:</span></span>  
  
 <span data-ttu-id="efd9c-109">[!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="efd9c-109">[!code-cs[csProgGuideGenerics#49](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_2.cs)]</span></span>  
  
 <span data-ttu-id="efd9c-110">Specificare più parametri di tipo usando il numero appropriato di virgole.</span><span class="sxs-lookup"><span data-stu-id="efd9c-110">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="efd9c-111">In questo esempio `GenericClass2` include due parametri di tipo:</span><span class="sxs-lookup"><span data-stu-id="efd9c-111">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 <span data-ttu-id="efd9c-112">[!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="efd9c-112">[!code-cs[csProgGuideGenerics#50](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_3.cs)]</span></span>  
  
 <span data-ttu-id="efd9c-113">Un attributo può fare riferimento a un tipo generico costruito chiuso:</span><span class="sxs-lookup"><span data-stu-id="efd9c-113">An attribute can reference a closed constructed generic type:</span></span>  
  
 <span data-ttu-id="efd9c-114">[!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="efd9c-114">[!code-cs[csProgGuideGenerics#51](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_4.cs)]</span></span>  
  
 <span data-ttu-id="efd9c-115">Un attributo che fa riferimento a un parametro di tipo generico provoca un errore in fase di compilazione:</span><span class="sxs-lookup"><span data-stu-id="efd9c-115">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 <span data-ttu-id="efd9c-116">[!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="efd9c-116">[!code-cs[csProgGuideGenerics#52](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_5.cs)]</span></span>  
  
 <span data-ttu-id="efd9c-117">Un tipo generico non può ereditare da <xref:System.Attribute>:</span><span class="sxs-lookup"><span data-stu-id="efd9c-117">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 <span data-ttu-id="efd9c-118">[!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="efd9c-118">[!code-cs[csProgGuideGenerics#53](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-and-attributes_6.cs)]</span></span>  
  
 <span data-ttu-id="efd9c-119">Per ottenere informazioni su un tipo generico o un parametro di tipo in fase di esecuzione, è possibile usare i metodi di <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="efd9c-119">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="efd9c-120">Per altre informazioni, vedere [Generics e reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="efd9c-120">For more information, see [Generics and Reflection](../../../csharp/programming-guide/generics/generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efd9c-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="efd9c-121">See Also</span></span>  
 <span data-ttu-id="efd9c-122">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="efd9c-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="efd9c-123">[Generics](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="efd9c-123">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 [<span data-ttu-id="efd9c-124">Attributi</span><span class="sxs-lookup"><span data-stu-id="efd9c-124">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)

