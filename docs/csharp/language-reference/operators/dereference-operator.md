---
title: Operatore -&gt; - Riferimenti per C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: bb1ccd026f403e68565c5c7681943d8017578d01
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53234890"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="3b2ec-102">-&gt; Operatore (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="3b2ec-102">-&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="3b2ec-103">L'operatore di accesso ai membri del puntatore `->` combina il riferimento indiretto al puntatore con l'accesso ai membri.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-103">The pointer member access operator `->` combines pointer indirection and member access.</span></span>

<span data-ttu-id="3b2ec-104">Se `x` è un puntatore del tipo `T*` e `y` è un membro accessibile di `T`, un'espressione nella forma</span><span class="sxs-lookup"><span data-stu-id="3b2ec-104">If `x` is a pointer of the type `T*` and `y` is an accessible member of `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="3b2ec-105">equivale a</span><span class="sxs-lookup"><span data-stu-id="3b2ec-105">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="3b2ec-106">L'operatore `->` richiede un contesto [unsafe](../keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ec-106">The `->` operator requires [unsafe](../keywords/unsafe.md) context.</span></span>

<span data-ttu-id="3b2ec-107">Per altre informazioni, vedere [Procedura: Accedere a un membro con un puntatore](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ec-107">For more information, see [How to: access a member with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="3b2ec-108">Overload degli operatori</span><span class="sxs-lookup"><span data-stu-id="3b2ec-108">Operator overloadability</span></span>

<span data-ttu-id="3b2ec-109">Non è possibile sottoporre l'operatore `->` a overload.</span><span class="sxs-lookup"><span data-stu-id="3b2ec-109">The `->` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="3b2ec-110">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="3b2ec-110">C# language specification</span></span>

<span data-ttu-id="3b2ec-111">Per altre informazioni, vedere la sezione [Accesso ai membri del puntatore](~/_csharplang/spec/unsafe-code.md#pointer-member-access) della [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="3b2ec-111">For more information, see the [Pointer member access](~/_csharplang/spec/unsafe-code.md#pointer-member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3b2ec-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3b2ec-112">See also</span></span>

- [<span data-ttu-id="3b2ec-113">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="3b2ec-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3b2ec-114">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="3b2ec-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3b2ec-115">Operatori C#</span><span class="sxs-lookup"><span data-stu-id="3b2ec-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="3b2ec-116">Tipi di puntatori</span><span class="sxs-lookup"><span data-stu-id="3b2ec-116">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
