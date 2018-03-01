---
title: 'Procedura: accedere a un elemento di matrice mediante un puntatore (Guida per programmatori C#)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 737c1d7fc0bc0a739de5c0a6cbc5dc09f813133e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="e6f92-102">Procedura: accedere a un elemento di matrice mediante un puntatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="e6f92-102">How to: Access an Array Element with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="e6f92-103">In un contesto non sicuro è possibile accedere a un elemento in memoria usando l'accesso all'elemento mediante puntatore, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="e6f92-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>  
  
```  
 char* charPointer = stackalloc char[123];  
for (int i = 65; i < 123; i++)  
{  
    charPointer[i] = (char)i; //access array elements  
}  
```  
  
 <span data-ttu-id="e6f92-104">L'espressione racchiusa tra parentesi quadre deve essere convertibile in modo implicito in `int`, `uint`, `long` o `ulong`.</span><span class="sxs-lookup"><span data-stu-id="e6f92-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="e6f92-105">L'operazione p[e] è equivalente a \*(p+e).</span><span class="sxs-lookup"><span data-stu-id="e6f92-105">The operation p[e] is equivalent to \*(p+e).</span></span> <span data-ttu-id="e6f92-106">Analogamente a C e C++, l'accesso all'elemento mediante puntatore non implica la verifica di errori relativi a valori non compresi nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="e6f92-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6f92-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="e6f92-107">Example</span></span>  
 <span data-ttu-id="e6f92-108">In questo esempio 123 posizioni di memoria vengono allocate a una matrice di caratteri, `charPointer`.</span><span class="sxs-lookup"><span data-stu-id="e6f92-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="e6f92-109">La matrice viene usata per visualizzare le lettere in minuscolo e maiuscolo in due cicli [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="e6f92-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>  
  
 <span data-ttu-id="e6f92-110">Si noti che l'espressione `charPointer[i]` è equivalente all'espressione `*(charPointer + i)` e che è possibile ottenere lo stesso risultato usando una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="e6f92-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]  
  
 <span data-ttu-id="e6f92-111">**Lettere maiuscole:**</span><span class="sxs-lookup"><span data-stu-id="e6f92-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="e6f92-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="e6f92-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="e6f92-113">**Lettere minuscole:**</span><span class="sxs-lookup"><span data-stu-id="e6f92-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="e6f92-114">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="e6f92-114">**abcdefghijklmnopqrstuvwxyz**</span></span>   
## <a name="see-also"></a><span data-ttu-id="e6f92-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e6f92-115">See Also</span></span>  
 [<span data-ttu-id="e6f92-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="e6f92-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e6f92-117">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="e6f92-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="e6f92-118">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="e6f92-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="e6f92-119">Tipi</span><span class="sxs-lookup"><span data-stu-id="e6f92-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="e6f92-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="e6f92-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="e6f92-121">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="e6f92-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="e6f92-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="e6f92-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
