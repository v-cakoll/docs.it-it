---
title: Operatore -> - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: be74f02a85aa05cdab32768ed38222fc4d9289b1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255367"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="76533-102">Operatore -> (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="76533-102">-> Operator (C# Reference)</span></span>

<span data-ttu-id="76533-103">L'operatore di accesso ai membri del puntatore `->` combina il riferimento indiretto al puntatore con l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="76533-103">The pointer member access operator `->` combines pointer indirection and member access.</span></span>

<span data-ttu-id="76533-104">Se `x` è un puntatore del tipo `T*` e `y` è un membro accessibile di `T`, un'espressione nella forma</span><span class="sxs-lookup"><span data-stu-id="76533-104">If `x` is a pointer of the type `T*` and `y` is an accessible member of `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="76533-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="76533-105">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="76533-106">L'operatore `->` richiede un contesto [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="76533-106">The `->` operator requires [unsafe](../keywords/unsafe.md) context.</span></span>

<span data-ttu-id="76533-107">Per altre informazioni, vedere [Procedura: Accedere a un membro con un puntatore](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="76533-107">For more information, see [How to: access a member with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="76533-108">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="76533-108">Operator overloadability</span></span>

<span data-ttu-id="76533-109">Non è possibile sottoporre l'operatore `->` a overload.</span><span class="sxs-lookup"><span data-stu-id="76533-109">The `->` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="76533-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="76533-110">C# language specification</span></span>

<span data-ttu-id="76533-111">Per altre informazioni, vedere la sezione [Accesso ai membri del puntatore](~/_csharplang/spec/unsafe-code.md#pointer-member-access) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="76533-111">For more information, see the [Pointer member access](~/_csharplang/spec/unsafe-code.md#pointer-member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="76533-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76533-112">See also</span></span>

- [<span data-ttu-id="76533-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="76533-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="76533-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="76533-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="76533-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="76533-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="76533-116">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="76533-116">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
