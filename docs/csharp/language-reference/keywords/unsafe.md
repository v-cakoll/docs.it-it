---
title: unsafe (Riferimenti per C#)
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: c476bdcea4993b27c0e8f8148a985f18a43ba09b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171954"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="ff185-102">unsafe (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="ff185-102">unsafe (C# Reference)</span></span>
<span data-ttu-id="ff185-103">La parola chiave `unsafe` denota un contesto unsafe, necessario per qualsiasi operazione che interessa i puntatori.</span><span class="sxs-lookup"><span data-stu-id="ff185-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="ff185-104">Per altre informazioni, vedere [Codice unsafe e puntatori](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff185-104">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="ff185-105">È possibile usare il modificatore `unsafe` nella dichiarazione di un tipo o di un membro.</span><span class="sxs-lookup"><span data-stu-id="ff185-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="ff185-106">L'intera estensione testuale del tipo o membro viene pertanto considerato come contesto unsafe.</span><span class="sxs-lookup"><span data-stu-id="ff185-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="ff185-107">Ad esempio, il seguente è un metodo dichiarato con il modificatore `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="ff185-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>  
  
```csharp  
      unsafe static void FastCopy(byte[] src, byte[] dst, int count)  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="ff185-108">L'ambito del contesto unsafe si estende dall'elenco di parametri alla fine del metodo, in modo tale che i puntatori possano essere usati anche nell'elenco dei parametri:</span><span class="sxs-lookup"><span data-stu-id="ff185-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>  
  
```csharp  
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}  
```  
  
 <span data-ttu-id="ff185-109">È anche possibile usare un blocco unsafe per consentire l'uso di un codice unsafe all'interno del blocco.</span><span class="sxs-lookup"><span data-stu-id="ff185-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="ff185-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ff185-110">For example:</span></span>  
  
```csharp  
      unsafe  
{  
    // Unsafe context: can use pointers here.  
}  
```  
  
 <span data-ttu-id="ff185-111">Per compilare codice unsafe, è necessario specificare l'opzione del compilatore [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ff185-111">To compile unsafe code, you must specify the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="ff185-112">Il codice unsafe non è verificabile da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="ff185-112">Unsafe code is not verifiable by the common language runtime.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff185-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="ff185-113">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#22](../../../csharp/language-reference/keywords/codesnippet/CSharp/unsafe_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="ff185-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="ff185-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ff185-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff185-115">See Also</span></span>  
 [<span data-ttu-id="ff185-116">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="ff185-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ff185-117">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="ff185-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ff185-118">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="ff185-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ff185-119">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="ff185-119">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="ff185-120">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="ff185-120">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="ff185-121">Buffer a dimensione fissa</span><span class="sxs-lookup"><span data-stu-id="ff185-121">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
