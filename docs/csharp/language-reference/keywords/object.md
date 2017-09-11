---
title: object (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- object_CSharpKeyword
- object
dev_langs:
- CSharp
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
caps.latest.revision: 16
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
ms.openlocfilehash: 744debc51f68cc52f03bce09c9f276a66ae085e1
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="object-c-reference"></a><span data-ttu-id="6b52c-102">object (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="6b52c-102">object (C# Reference)</span></span>
<span data-ttu-id="6b52c-103">Il tipo `object` è un alias di <xref:System.Object> in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6b52c-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="6b52c-104">Nel sistema di tipi unificato di C#, tutti i tipi, predefiniti e definiti dall'utente, i tipi riferimento e i tipi valore ereditano direttamente o indirettamente da <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="6b52c-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="6b52c-105">Alle variabili di tipo `object` è possibile assegnare valori di qualsiasi tipo.</span><span class="sxs-lookup"><span data-stu-id="6b52c-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="6b52c-106">Una variabile di un tipo di valore convertita in oggetto viene definita *boxed*.</span><span class="sxs-lookup"><span data-stu-id="6b52c-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="6b52c-107">Una variabile di tipo object convertita in un tipo di valore viene definita *unboxed*.</span><span class="sxs-lookup"><span data-stu-id="6b52c-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="6b52c-108">Per altre informazioni, vedere [Boxing e unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="6b52c-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b52c-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="6b52c-109">Example</span></span>  
 <span data-ttu-id="6b52c-110">L'esempio seguente descrive come le variabili di tipo `object` possono accettare valori di qualsiasi tipo di dati e come le variabili di tipo `object` possono usare i metodi in <xref:System.Object> da .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6b52c-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 <span data-ttu-id="6b52c-111">[!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6b52c-111">[!code-cs[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6b52c-112">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="6b52c-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6b52c-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6b52c-113">See Also</span></span>  
 <span data-ttu-id="6b52c-114">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6b52c-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6b52c-115">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6b52c-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6b52c-116">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="6b52c-116">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="6b52c-117">[Tipi di riferimento](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="6b52c-117">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 [<span data-ttu-id="6b52c-118">Tipi di valore</span><span class="sxs-lookup"><span data-stu-id="6b52c-118">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)

