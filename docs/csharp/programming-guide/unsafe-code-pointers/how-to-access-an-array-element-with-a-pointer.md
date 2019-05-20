---
title: 'Procedura: Accedere a un elemento di matrice tramite un puntatore - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: b1538068f3ba37a7637e7dc3913e9511d4380daf
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635180"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="5b294-102">Procedura: Accedere a un elemento di matrice tramite un puntatore (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="5b294-102">How to: access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="5b294-103">In un contesto non sicuro è possibile accedere a un elemento in memoria usando l'accesso all'elemento mediante puntatore, come illustrato nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="5b294-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="5b294-104">L'espressione racchiusa tra parentesi quadre deve essere convertibile in modo implicito in `int`, `uint`, `long` o `ulong`.</span><span class="sxs-lookup"><span data-stu-id="5b294-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="5b294-105">L'operazione `p[e]` è equivalente a `*(p+e)`.</span><span class="sxs-lookup"><span data-stu-id="5b294-105">The operation `p[e]` is equivalent to `*(p+e)`.</span></span> <span data-ttu-id="5b294-106">Analogamente a C e C++, l'accesso all'elemento mediante puntatore non implica la verifica di errori relativi a valori non compresi nell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="5b294-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="5b294-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="5b294-107">Example</span></span>

<span data-ttu-id="5b294-108">In questo esempio 123 posizioni di memoria vengono allocate a una matrice di caratteri, `charPointer`.</span><span class="sxs-lookup"><span data-stu-id="5b294-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="5b294-109">La matrice viene usata per visualizzare le lettere in minuscolo e maiuscolo in due cicli [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="5b294-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="5b294-110">Si noti che l'espressione `charPointer[i]` è equivalente all'espressione `*(charPointer + i)` e che è possibile ottenere lo stesso risultato usando una delle due espressioni.</span><span class="sxs-lookup"><span data-stu-id="5b294-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

 [!code-csharp[csProgGuidePointers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#11)]

 [!code-csharp[csProgGuidePointers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#12)]

<span data-ttu-id="5b294-111">**Lettere maiuscole:**</span><span class="sxs-lookup"><span data-stu-id="5b294-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="5b294-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="5b294-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="5b294-113">**Lettere minuscole:**</span><span class="sxs-lookup"><span data-stu-id="5b294-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="5b294-114">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="5b294-114">**abcdefghijklmnopqrstuvwxyz**</span></span>  

## <a name="see-also"></a><span data-ttu-id="5b294-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b294-115">See also</span></span>

- [<span data-ttu-id="5b294-116">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="5b294-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="5b294-117">Tipi</span><span class="sxs-lookup"><span data-stu-id="5b294-117">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="5b294-118">unsafe</span><span class="sxs-lookup"><span data-stu-id="5b294-118">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="5b294-119">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="5b294-119">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="5b294-120">stackalloc</span><span class="sxs-lookup"><span data-stu-id="5b294-120">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
