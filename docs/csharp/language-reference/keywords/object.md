---
title: object (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: 67eaf7f1fd2f01e433395ed21701c3b7fad7c7b4
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2018
ms.locfileid: "39199251"
---
# <a name="object-c-reference"></a><span data-ttu-id="19fc8-102">object (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="19fc8-102">object (C# Reference)</span></span>
<span data-ttu-id="19fc8-103">Il tipo `object` è un alias di <xref:System.Object> in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19fc8-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="19fc8-104">Nel sistema di tipi unificato di C#, tutti i tipi, predefiniti e definiti dall'utente, i tipi riferimento e i tipi valore ereditano direttamente o indirettamente da <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="19fc8-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="19fc8-105">Alle variabili di tipo `object` è possibile assegnare valori di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="19fc8-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="19fc8-106">Una variabile di un tipo di valore convertita in oggetto viene definita *boxed*.</span><span class="sxs-lookup"><span data-stu-id="19fc8-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="19fc8-107">Una variabile di tipo object convertita in un tipo di valore viene definita *unboxed*.</span><span class="sxs-lookup"><span data-stu-id="19fc8-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="19fc8-108">Per altre informazioni, vedere [Boxing e unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="19fc8-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19fc8-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="19fc8-109">Example</span></span>  
 <span data-ttu-id="19fc8-110">L'esempio seguente descrive come le variabili di tipo `object` possono accettare valori di qualsiasi tipo di dati e come le variabili di tipo `object` possono usare i metodi in <xref:System.Object> da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="19fc8-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="19fc8-111">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="19fc8-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="19fc8-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="19fc8-112">See Also</span></span>  
 [<span data-ttu-id="19fc8-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="19fc8-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="19fc8-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="19fc8-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="19fc8-115">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="19fc8-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="19fc8-116">Tipi riferimento</span><span class="sxs-lookup"><span data-stu-id="19fc8-116">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="19fc8-117">Tipi valore</span><span class="sxs-lookup"><span data-stu-id="19fc8-117">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
