---
title: parziale (Tipo) (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- partialtype
- partialtype_CSharpKeyword
helpviewer_keywords:
- partial types [C#]
ms.assetid: 27320743-a22e-4c7b-b0b3-53afe3607334
ms.openlocfilehash: 362a02815cb249d57c0bd19706714df1d71644f4
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42929663"
---
# <a name="partial-type-c-reference"></a><span data-ttu-id="e968a-102">parziale (Tipo) (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="e968a-102">partial (Type) (C# Reference)</span></span>
<span data-ttu-id="e968a-103">Le definizioni di tipi parziali consentono la suddivisione in più file della definizione di una classe, una struttura o un'interfaccia.</span><span class="sxs-lookup"><span data-stu-id="e968a-103">Partial type definitions allow for the definition of a class, struct, or interface to be split into multiple files.</span></span>  
  
 <span data-ttu-id="e968a-104">In File1.cs:</span><span class="sxs-lookup"><span data-stu-id="e968a-104">In File1.cs:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_1.cs)]  
  
 <span data-ttu-id="e968a-105">In File2.cs la dichiarazione:</span><span class="sxs-lookup"><span data-stu-id="e968a-105">In File2.cs the declaration:</span></span>  
  
 [!code-csharp[csrefKeywordsContextual#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/partial-type_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="e968a-106">Note</span><span class="sxs-lookup"><span data-stu-id="e968a-106">Remarks</span></span>  
 <span data-ttu-id="e968a-107">La suddivisione di un tipo di classe, struttura o interfaccia in più file può essere utile per progetti di grandi dimensioni o quando si usa codice generato automaticamente come quello fornito da [Progettazione Windows Form](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="e968a-107">Splitting a class, struct or interface type over several files can be useful when you are working with large projects, or with automatically generated code such as that provided by the [Windows Forms Designer](../../../framework/winforms/controls/developing-windows-forms-controls-at-design-time.md).</span></span> <span data-ttu-id="e968a-108">Un tipo parziale può contenere un [metodo parziale](../../../csharp/language-reference/keywords/partial-method.md).</span><span class="sxs-lookup"><span data-stu-id="e968a-108">A partial type may contain a [partial method](../../../csharp/language-reference/keywords/partial-method.md).</span></span> <span data-ttu-id="e968a-109">Per altre informazioni, vedere [Classi e metodi parziali](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span><span class="sxs-lookup"><span data-stu-id="e968a-109">For more information, see [Partial Classes and Methods](../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="e968a-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="e968a-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e968a-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e968a-111">See Also</span></span>

- [<span data-ttu-id="e968a-112">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="e968a-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e968a-113">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e968a-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e968a-114">Modificatori</span><span class="sxs-lookup"><span data-stu-id="e968a-114">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
- [<span data-ttu-id="e968a-115">Introduzione ai generics</span><span class="sxs-lookup"><span data-stu-id="e968a-115">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)
