---
title: unsafe (Riferimenti per C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords: unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1fffbe36e39d279b2364b178188381a403c8ff86
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="1696b-102">unsafe (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="1696b-102">unsafe (C# Reference)</span></span>
<span data-ttu-id="1696b-103">La parola chiave `unsafe` denota un contesto unsafe, necessario per qualsiasi operazione che interessa i puntatori.</span><span class="sxs-lookup"><span data-stu-id="1696b-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="1696b-104">Per altre informazioni, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="1696b-104">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="1696b-105">È possibile usare il modificatore `unsafe` nella dichiarazione di un tipo o di un membro.</span><span class="sxs-lookup"><span data-stu-id="1696b-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="1696b-106">L'intera estensione testuale del tipo o membro viene pertanto considerato come contesto unsafe.</span><span class="sxs-lookup"><span data-stu-id="1696b-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="1696b-107">Ad esempio, il seguente è un metodo dichiarato con il modificatore `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="1696b-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>  
  
```  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="1696b-108">L'ambito del contesto unsafe si estende dall'elenco di parametri alla fine del metodo, in modo tale che i puntatori possano essere usati anche nell'elenco dei parametri:</span><span class="sxs-lookup"><span data-stu-id="1696b-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>  
  
```  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 <span data-ttu-id="1696b-109">È anche possibile usare un blocco unsafe per consentire l'uso di un codice unsafe all'interno del blocco.</span><span class="sxs-lookup"><span data-stu-id="1696b-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="1696b-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1696b-110">For example:</span></span>  
  
```  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="1696b-111">Per compilare codice unsafe, è necessario specificare l'opzione del compilatore [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1696b-111">To compile unsafe code, you must specify the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="1696b-112">Il codice unsafe non è verificabile da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="1696b-112">Unsafe code is not verifiable by the common language runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1696b-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="1696b-113">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="1696b-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="1696b-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1696b-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1696b-115">See Also</span></span>  
 [<span data-ttu-id="1696b-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="1696b-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="1696b-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="1696b-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="1696b-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="1696b-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="1696b-119">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="1696b-119">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="1696b-120">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="1696b-120">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="1696b-121">Buffer a dimensione fissa</span><span class="sxs-lookup"><span data-stu-id="1696b-121">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
