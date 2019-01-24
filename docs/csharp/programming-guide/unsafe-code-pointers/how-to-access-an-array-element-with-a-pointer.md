---
title: 'Procedura: Accedere a un elemento di matrice tramite un puntatore - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: 59765dbcad6c28cf2ad9f3df2052df19cafd08f1
ms.sourcegitcommit: 75567a3cb437009db55949c6092f4e77ed1a9da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2019
ms.locfileid: "54307279"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="5a5de-102">Procedura: Accedere a un elemento di matrice tramite un puntatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5a5de-102">How to: access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="5a5de-103">In un contesto non sicuro è possibile accedere a un elemento in memoria usando l'accesso all'elemento mediante puntatore, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5a5de-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="5a5de-104">L'espressione racchiusa tra parentesi quadre deve essere convertibile in modo implicito in `int`, `uint`, `long` o `ulong`.</span><span class="sxs-lookup"><span data-stu-id="5a5de-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="5a5de-105">L'operazione `p[e]` è equivalente a `*(p+e)`.</span><span class="sxs-lookup"><span data-stu-id="5a5de-105">The operation `p[e]` is equivalent to `*(p+e)`.</span></span> <span data-ttu-id="5a5de-106">Analogamente a C e C++, l'accesso all'elemento mediante puntatore non implica la verifica di errori relativi a valori non compresi nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="5a5de-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="5a5de-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="5a5de-107">Example</span></span>

<span data-ttu-id="5a5de-108">In questo esempio 123 posizioni di memoria vengono allocate a una matrice di caratteri, `charPointer`.</span><span class="sxs-lookup"><span data-stu-id="5a5de-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="5a5de-109">La matrice viene usata per visualizzare le lettere in minuscolo e maiuscolo in due cicli [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="5a5de-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="5a5de-110">Si noti che l'espressione `charPointer[i]` è equivalente all'espressione `*(charPointer + i)` e che è possibile ottenere lo stesso risultato usando una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="5a5de-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

[!code-csharp[csProgGuidePointers#11](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_1.cs)]

[!code-csharp[csProgGuidePointers#12](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-an-array-element-with-a-pointer_2.cs)]

<span data-ttu-id="5a5de-111">**Lettere maiuscole:**</span><span class="sxs-lookup"><span data-stu-id="5a5de-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="5a5de-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="5a5de-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="5a5de-113">**Lettere minuscole:**</span><span class="sxs-lookup"><span data-stu-id="5a5de-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="5a5de-114">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="5a5de-114">**abcdefghijklmnopqrstuvwxyz**</span></span>  

## <a name="see-also"></a><span data-ttu-id="5a5de-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a5de-115">See also</span></span>

- [<span data-ttu-id="5a5de-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5a5de-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5a5de-117">Espressioni puntatore</span><span class="sxs-lookup"><span data-stu-id="5a5de-117">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="5a5de-118">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="5a5de-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="5a5de-119">Tipi</span><span class="sxs-lookup"><span data-stu-id="5a5de-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="5a5de-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="5a5de-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="5a5de-121">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="5a5de-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="5a5de-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="5a5de-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
