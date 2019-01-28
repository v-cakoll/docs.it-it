---
title: 'Procedura: Usare puntatori per copiare una matrice di byte - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: d174f51fa1709a70b98473a4dbbad89b9c62c22a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640303"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes--c-programming-guide"></a><span data-ttu-id="b2a95-102">Procedura: Usare puntatori per copiare una matrice di byte (Guida per programmatori C#)</span><span class="sxs-lookup"><span data-stu-id="b2a95-102">How to: Use Pointers to Copy an Array of Bytes  (C# Programming Guide)</span></span>

<span data-ttu-id="b2a95-103">Nell'esempio seguente vengono usati i puntatori per copiare i byte da una matrice a un'altra.</span><span class="sxs-lookup"><span data-stu-id="b2a95-103">The following example uses pointers to copy bytes from one array to another.</span></span>

<span data-ttu-id="b2a95-104">In questo esempio viene usata la parola chiave [unsafe](../../language-reference/keywords/unsafe.md), che consente l'uso di puntatori nel metodo `Copy`.</span><span class="sxs-lookup"><span data-stu-id="b2a95-104">This example uses the [unsafe](../../language-reference/keywords/unsafe.md) keyword, which enables you to use pointers in the `Copy` method.</span></span> <span data-ttu-id="b2a95-105">Per dichiarare i puntatori nelle matrici di origine e destinazione, viene usata l'istruzione [fixed](../../language-reference/keywords/fixed-statement.md),</span><span class="sxs-lookup"><span data-stu-id="b2a95-105">The [fixed](../../language-reference/keywords/fixed-statement.md) statement is used to declare pointers to the source and destination arrays.</span></span> <span data-ttu-id="b2a95-106">L'istruzione `fixed` *blocca* la posizione delle matrici di origine e destinazione nella memoria in modo che non vengano rimosse da Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b2a95-106">The `fixed` statement *pins* the location of the source and destination arrays in memory so that they will not be moved by garbage collection.</span></span> <span data-ttu-id="b2a95-107">I blocchi di memoria per le matrici vengono rimossi quando il blocco `fixed` è completato.</span><span class="sxs-lookup"><span data-stu-id="b2a95-107">The memory blocks for the arrays are unpinned when the `fixed` block is completed.</span></span> <span data-ttu-id="b2a95-108">Il metodo `Copy` in questo esempio usa la parola chiave `unsafe`. Deve pertanto essere compilato con l'opzione del compilatore [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="b2a95-108">Because the `Copy` method in this example uses the `unsafe` keyword, it must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>

<span data-ttu-id="b2a95-109">L'esempio accede agli elementi di entrambe le matrici usando gli indici invece di un secondo puntatore non gestito.</span><span class="sxs-lookup"><span data-stu-id="b2a95-109">This example accesses the elements of both arrays using indices rather than a second unmanaged pointer.</span></span> <span data-ttu-id="b2a95-110">La dichiarazione dei puntatori `pSource` e `pTarget` blocca le matrici.</span><span class="sxs-lookup"><span data-stu-id="b2a95-110">The declaration of the `pSource` and `pTarget` pointers pins the arrays.</span></span> <span data-ttu-id="b2a95-111">Questa funzionalità è disponibile a partire da C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="b2a95-111">This feature is available starting with C# 7.3.</span></span>

## <a name="example"></a><span data-ttu-id="b2a95-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b2a95-112">Example</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a><span data-ttu-id="b2a95-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b2a95-113">See also</span></span>

- [<span data-ttu-id="b2a95-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="b2a95-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b2a95-115">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="b2a95-115">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="b2a95-116">-unsafe (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="b2a95-116">-unsafe (C# Compiler Options)</span></span>](../../language-reference/compiler-options/unsafe-compiler-option.md)
- [<span data-ttu-id="b2a95-117">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="b2a95-117">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
