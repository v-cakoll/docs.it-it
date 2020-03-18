---
title: Generics e attributi - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], attributes
- attributes [C#], with generics
ms.assetid: da9fc326-4648-454a-8e13-3911a2edefd7
ms.openlocfilehash: 47bf4e8f07a8b6778db8fa675d745d362dc10d7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75703026"
---
# <a name="generics-and-attributes-c-programming-guide"></a><span data-ttu-id="1ccce-102">Generics e attributi (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="1ccce-102">Generics and Attributes (C# Programming Guide)</span></span>
<span data-ttu-id="1ccce-103">Gli attributi possono essere applicati a tipi generici allo stesso modo che ai tipi non generici.</span><span class="sxs-lookup"><span data-stu-id="1ccce-103">Attributes can be applied to generic types in the same way as non-generic types.</span></span> <span data-ttu-id="1ccce-104">Per altre informazioni sull'applicazione di attributi, vedere [Attributi](../concepts/attributes/index.md).</span><span class="sxs-lookup"><span data-stu-id="1ccce-104">For more information on applying attributes, see [Attributes](../concepts/attributes/index.md).</span></span>  
  
 <span data-ttu-id="1ccce-105">Gli attributi personalizzati sono consentiti solo per fare riferimento a tipi generici aperti, che sono tipi generici per cui non è specificato alcun argomento tipo, e tipi generici costruiti chiusi, che specificano argomenti per tutti i parametri di tipo.</span><span class="sxs-lookup"><span data-stu-id="1ccce-105">Custom attributes are only permitted to reference open generic types, which are generic types for which no type arguments are supplied, and closed constructed generic types, which supply arguments for all type parameters.</span></span>  
  
 <span data-ttu-id="1ccce-106">Gli esempi seguenti usano questo attributo personalizzato:</span><span class="sxs-lookup"><span data-stu-id="1ccce-106">The following examples use this custom attribute:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#48](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#48)]  
  
 <span data-ttu-id="1ccce-107">Un attributo può fare riferimento a un tipo generico aperto:</span><span class="sxs-lookup"><span data-stu-id="1ccce-107">An attribute can reference an open generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#49](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#49)]  
  
 <span data-ttu-id="1ccce-108">Specificare più parametri di tipo usando il numero appropriato di virgole.</span><span class="sxs-lookup"><span data-stu-id="1ccce-108">Specify multiple type parameters using the appropriate number of commas.</span></span> <span data-ttu-id="1ccce-109">In questo esempio `GenericClass2` include due parametri di tipo:</span><span class="sxs-lookup"><span data-stu-id="1ccce-109">In this example, `GenericClass2` has two type parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#50](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#50)]  
  
 <span data-ttu-id="1ccce-110">Un attributo può fare riferimento a un tipo generico costruito chiuso:</span><span class="sxs-lookup"><span data-stu-id="1ccce-110">An attribute can reference a closed constructed generic type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#51](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#51)]  
  
 <span data-ttu-id="1ccce-111">Un attributo che fa riferimento a un parametro di tipo generico provoca un errore in fase di compilazione:</span><span class="sxs-lookup"><span data-stu-id="1ccce-111">An attribute that references a generic type parameter will cause a compile-time error:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#52](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#52)]  
  
 <span data-ttu-id="1ccce-112">Un tipo generico non può ereditare da <xref:System.Attribute>:</span><span class="sxs-lookup"><span data-stu-id="1ccce-112">A generic type cannot inherit from <xref:System.Attribute>:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#53)]  
  
 <span data-ttu-id="1ccce-113">Per ottenere informazioni su un tipo generico o un parametro di tipo in fase di esecuzione, è possibile usare i metodi di <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="1ccce-113">To obtain information about a generic type or type parameter at run time, you can use the methods of <xref:System.Reflection>.</span></span> <span data-ttu-id="1ccce-114">Per altre informazioni, vedere [Generics e reflection](./generics-and-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="1ccce-114">For more information, see [Generics and Reflection](./generics-and-reflection.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ccce-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1ccce-115">See also</span></span>

- [<span data-ttu-id="1ccce-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1ccce-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1ccce-117">Generics</span><span class="sxs-lookup"><span data-stu-id="1ccce-117">Generics</span></span>](./index.md)
- [<span data-ttu-id="1ccce-118">Attributi</span><span class="sxs-lookup"><span data-stu-id="1ccce-118">Attributes</span></span>](../../../standard/attributes/index.md)
