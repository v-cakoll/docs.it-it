---
title: Parola chiave unsafe - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 81a293a6922a71f7428167c50aed064d7387a099
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236622"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="0e654-102">unsafe (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="0e654-102">unsafe (C# Reference)</span></span>

<span data-ttu-id="0e654-103">La parola chiave `unsafe` denota un contesto unsafe, necessario per qualsiasi operazione che interessa i puntatori.</span><span class="sxs-lookup"><span data-stu-id="0e654-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="0e654-104">Per altre informazioni, vedere [Codice unsafe e puntatori](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="0e654-104">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="0e654-105">È possibile usare il modificatore `unsafe` nella dichiarazione di un tipo o di un membro.</span><span class="sxs-lookup"><span data-stu-id="0e654-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="0e654-106">L'intera estensione testuale del tipo o membro viene pertanto considerato come contesto unsafe.</span><span class="sxs-lookup"><span data-stu-id="0e654-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="0e654-107">Ad esempio, il seguente è un metodo dichiarato con il modificatore `unsafe`:</span><span class="sxs-lookup"><span data-stu-id="0e654-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="0e654-108">L'ambito del contesto unsafe si estende dall'elenco di parametri alla fine del metodo, in modo tale che i puntatori possano essere usati anche nell'elenco dei parametri:</span><span class="sxs-lookup"><span data-stu-id="0e654-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="0e654-109">È anche possibile usare un blocco unsafe per consentire l'uso di un codice unsafe all'interno del blocco.</span><span class="sxs-lookup"><span data-stu-id="0e654-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="0e654-110">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0e654-110">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="0e654-111">Per compilare codice unsafe, è necessario specificare l'opzione del compilatore [/unsafe](../compiler-options/unsafe-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0e654-111">To compile unsafe code, you must specify the [/unsafe](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="0e654-112">Il codice unsafe non è verificabile da Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="0e654-112">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="0e654-113">Esempio</span><span class="sxs-lookup"><span data-stu-id="0e654-113">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="0e654-114">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="0e654-114">C# language specification</span></span>

<span data-ttu-id="0e654-115">Per altre informazioni, vedere [Codice di tipo unsafe](~/_csharplang/spec/unsafe-code.md) nella [specifica del linguaggio C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="0e654-115">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="0e654-116">La specifica del linguaggio costituisce il riferimento ufficiale principale per la sintassi e l'uso di C#.</span><span class="sxs-lookup"><span data-stu-id="0e654-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e654-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0e654-117">See also</span></span>

- [<span data-ttu-id="0e654-118">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="0e654-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0e654-119">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="0e654-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0e654-120">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="0e654-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="0e654-121">Istruzione fixed</span><span class="sxs-lookup"><span data-stu-id="0e654-121">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="0e654-122">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="0e654-122">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="0e654-123">Buffer a dimensione fissa</span><span class="sxs-lookup"><span data-stu-id="0e654-123">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)