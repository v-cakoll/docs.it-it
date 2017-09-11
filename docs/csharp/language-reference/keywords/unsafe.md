---
title: unsafe (Riferimenti per C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
dev_langs:
- CSharp
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: 19
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
ms.openlocfilehash: ceba9e518caf6618cf2f457b930ce08f18273d8c
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="unsafe-c-reference"></a><span data-ttu-id="b42d1-102">unsafe (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="b42d1-102">unsafe (C# Reference)</span></span>
<span data-ttu-id="b42d1-103">La parola chiave `unsafe` denota un contesto unsafe, necessario per qualsiasi operazione che interessa i puntatori.</span><span class="sxs-lookup"><span data-stu-id="b42d1-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="b42d1-104">Per altre informazioni, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="b42d1-104">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="b42d1-105">È possibile usare il modificatore `unsafe` nella dichiarazione di un tipo o di un membro.</span><span class="sxs-lookup"><span data-stu-id="b42d1-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="b42d1-106">L'intera estensione testuale del tipo o membro viene pertanto considerato come contesto unsafe.</span><span class="sxs-lookup"><span data-stu-id="b42d1-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="b42d1-107">Ad esempio, il seguente è un metodo dichiarato con il modificatore `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="b42d1-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>  
  
```  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="b42d1-108">L'ambito del contesto unsafe si estende dall'elenco di parametri alla fine del metodo, in modo tale che i puntatori possano essere usati anche nell'elenco dei parametri:</span><span class="sxs-lookup"><span data-stu-id="b42d1-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>  
  
```  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 <span data-ttu-id="b42d1-109">È anche possibile usare un blocco unsafe per consentire l'uso di un codice unsafe all'interno del blocco.</span><span class="sxs-lookup"><span data-stu-id="b42d1-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="b42d1-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b42d1-110">For example:</span></span>  
  
```  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="b42d1-111">Per compilare codice unsafe, è necessario specificare l'opzione del compilatore [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b42d1-111">To compile unsafe code, you must specify the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="b42d1-112">Il codice unsafe non è verificabile da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="b42d1-112">Unsafe code is not verifiable by the common language runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b42d1-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="b42d1-113">Example</span></span>  
 <span data-ttu-id="b42d1-114">[!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b42d1-114">[!code-cs[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b42d1-115">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="b42d1-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b42d1-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b42d1-116">See Also</span></span>  
 <span data-ttu-id="b42d1-117">[Riferimenti per C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b42d1-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b42d1-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b42d1-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b42d1-119">[Parole chiave di C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="b42d1-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="b42d1-120">[Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b42d1-120">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 <span data-ttu-id="b42d1-121">[Codice di tipo unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="b42d1-121">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 [<span data-ttu-id="b42d1-122">Buffer a dimensione fissa</span><span class="sxs-lookup"><span data-stu-id="b42d1-122">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)

