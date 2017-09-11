---
title: 'Procedura: accedere a un elemento di matrice mediante un puntatore (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
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
ms.openlocfilehash: 73f14aba63b7f7677a889f18cc1b410e3ecf1438
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="727d4-102">Procedura: accedere a un elemento di matrice mediante un puntatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="727d4-102">How to: Access an Array Element with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="727d4-103">In un contesto non sicuro è possibile accedere a un elemento in memoria usando l'accesso all'elemento mediante puntatore, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="727d4-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 <span data-ttu-id="727d4-104">L'espressione racchiusa tra parentesi quadre deve essere convertibile in modo implicito in `int`, `uint`, `long` o `ulong`.</span><span class="sxs-lookup"><span data-stu-id="727d4-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="727d4-105">L'operazione p[e] è equivalente a *(p+e).</span><span class="sxs-lookup"><span data-stu-id="727d4-105">The operation p[e] is equivalent to *(p+e).</span></span> <span data-ttu-id="727d4-106">Analogamente a C e C++, l'accesso all'elemento mediante puntatore non implica la verifica di errori relativi a valori non compresi nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="727d4-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="727d4-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="727d4-107">Example</span></span>  
 <span data-ttu-id="727d4-108">In questo esempio 123 posizioni di memoria vengono allocate a una matrice di caratteri, `charPointer`.</span><span class="sxs-lookup"><span data-stu-id="727d4-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="727d4-109">La matrice viene usata per visualizzare le lettere in minuscolo e maiuscolo in due cicli [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="727d4-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>  
  
 <span data-ttu-id="727d4-110">Si noti che l'espressione `charPointer[i]` è equivalente all'espressione `*(charPointer + i)` e che è possibile ottenere lo stesso risultato usando una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="727d4-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 <span data-ttu-id="727d4-111">[!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="727d4-111">[!code-cs[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]</span></span>  
  
 <span data-ttu-id="727d4-112">[!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="727d4-112">[!code-cs[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]</span></span>  
  
 <span data-ttu-id="727d4-113">**Lettere maiuscole:**</span><span class="sxs-lookup"><span data-stu-id="727d4-113">**Uppercase letters:**</span></span>  
<span data-ttu-id="727d4-114">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="727d4-114">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="727d4-115">**Lettere minuscole:**</span><span class="sxs-lookup"><span data-stu-id="727d4-115">**Lowercase letters:**</span></span>  
<span data-ttu-id="727d4-116">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="727d4-116">**abcdefghijklmnopqrstuvwxyz**</span></span>   
## <a name="see-also"></a><span data-ttu-id="727d4-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="727d4-117">See Also</span></span>  
 <span data-ttu-id="727d4-118">[Guida per programmatori C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="727d4-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="727d4-119">[Espressioni puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="727d4-119">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="727d4-120">[Tipi di puntatore](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="727d4-120">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="727d4-121">[Tipi](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="727d4-121">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="727d4-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="727d4-122">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="727d4-123">[Istruzione fixed](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="727d4-123">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="727d4-124">stackalloc</span><span class="sxs-lookup"><span data-stu-id="727d4-124">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

