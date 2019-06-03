---
title: sizeof - Riferimenti per C#
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: a00c4f96e62f7fd7d7c352aece097acd5b600ae2
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422402"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="77724-102">sizeof (Riferimenti per C#)</span><span class="sxs-lookup"><span data-stu-id="77724-102">sizeof (C# Reference)</span></span>

<span data-ttu-id="77724-103">Usato per ottenere la dimensione in byte per un tipo non gestito.</span><span class="sxs-lookup"><span data-stu-id="77724-103">Used to obtain the size in bytes for an unmanaged type.</span></span>

<span data-ttu-id="77724-104">I tipi non gestiti includono:</span><span class="sxs-lookup"><span data-stu-id="77724-104">Unmanaged types include:</span></span>

- <span data-ttu-id="77724-105">I tipi semplici elencati nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="77724-105">The simple types that are listed in the following table:</span></span>

   |<span data-ttu-id="77724-106">Espressione</span><span class="sxs-lookup"><span data-stu-id="77724-106">Expression</span></span>|<span data-ttu-id="77724-107">Valore costante</span><span class="sxs-lookup"><span data-stu-id="77724-107">Constant value</span></span>|
   |----------------|--------------------|
   |`sizeof(sbyte)`|<span data-ttu-id="77724-108">1</span><span class="sxs-lookup"><span data-stu-id="77724-108">1</span></span>|
   |`sizeof(byte)`|<span data-ttu-id="77724-109">1</span><span class="sxs-lookup"><span data-stu-id="77724-109">1</span></span>|
   |`sizeof(short)`|<span data-ttu-id="77724-110">2</span><span class="sxs-lookup"><span data-stu-id="77724-110">2</span></span>|
   |`sizeof(ushort)`|<span data-ttu-id="77724-111">2</span><span class="sxs-lookup"><span data-stu-id="77724-111">2</span></span>|
   |`sizeof(int)`|<span data-ttu-id="77724-112">4</span><span class="sxs-lookup"><span data-stu-id="77724-112">4</span></span>|
   |`sizeof(uint)`|<span data-ttu-id="77724-113">4</span><span class="sxs-lookup"><span data-stu-id="77724-113">4</span></span>|
   |`sizeof(long)`|<span data-ttu-id="77724-114">8</span><span class="sxs-lookup"><span data-stu-id="77724-114">8</span></span>|
   |`sizeof(ulong)`|<span data-ttu-id="77724-115">8</span><span class="sxs-lookup"><span data-stu-id="77724-115">8</span></span>|
   |`sizeof(char)`|<span data-ttu-id="77724-116">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="77724-116">2 (Unicode)</span></span>|
   |`sizeof(float)`|<span data-ttu-id="77724-117">4</span><span class="sxs-lookup"><span data-stu-id="77724-117">4</span></span>|
   |`sizeof(double)`|<span data-ttu-id="77724-118">8</span><span class="sxs-lookup"><span data-stu-id="77724-118">8</span></span>|
   |`sizeof(decimal)`|<span data-ttu-id="77724-119">16</span><span class="sxs-lookup"><span data-stu-id="77724-119">16</span></span>|
   |`sizeof(bool)`|<span data-ttu-id="77724-120">1</span><span class="sxs-lookup"><span data-stu-id="77724-120">1</span></span>|

- <span data-ttu-id="77724-121">Tipi enumerazione.</span><span class="sxs-lookup"><span data-stu-id="77724-121">Enum types.</span></span>

- <span data-ttu-id="77724-122">Tipi puntatore.</span><span class="sxs-lookup"><span data-stu-id="77724-122">Pointer types.</span></span>

- <span data-ttu-id="77724-123">Struct definiti dall'utente che non contengono campi di istanza o proprietà di istanza implementate automaticamente che sono tipi riferimento o tipi costruiti.</span><span class="sxs-lookup"><span data-stu-id="77724-123">User-defined structs that do not contain any instance fields or auto-implemented instance properties that are reference types or constructed types.</span></span>

<span data-ttu-id="77724-124">Nell'esempio seguente viene illustrato come ottenere la dimensione di un `int`:</span><span class="sxs-lookup"><span data-stu-id="77724-124">The following example shows how to retrieve the size of an `int`:</span></span>

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a><span data-ttu-id="77724-125">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="77724-125">Remarks</span></span>

<span data-ttu-id="77724-126">A partire dalla versione 2.0 di C#, l'applicazione di `sizeof` a tipi semplici o tipi enumerazione non richiede più che il codice venga compilato in un contesto [non sicuro](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="77724-126">Starting with version 2.0 of C#, applying `sizeof` to simple or enum types no longer requires that code be compiled in an [unsafe](unsafe.md) context.</span></span>

<span data-ttu-id="77724-127">Non è possibile sottoporre l'operatore `sizeof` a overload.</span><span class="sxs-lookup"><span data-stu-id="77724-127">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="77724-128">I valori restituiti dall'operatore `sizeof` sono di tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="77724-128">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="77724-129">La tabella precedente mostra i valori costanti che vengono sostituiti per le espressioni `sizeof` con determinati tipi predefiniti come operandi.</span><span class="sxs-lookup"><span data-stu-id="77724-129">The previous table shows the constant values that are substituted for `sizeof` expressions that have certain simple types as operands.</span></span>

<span data-ttu-id="77724-130">Per tutti gli altri tipi, inclusi gli struct, l'operatore `sizeof` può essere usato solo nei blocchi di codice unsafe.</span><span class="sxs-lookup"><span data-stu-id="77724-130">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="77724-131">Sebbene sia possibile usare il metodo <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>, il valore restituito da questo metodo non è sempre uguale al valore restituito da `sizeof`.</span><span class="sxs-lookup"><span data-stu-id="77724-131">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="77724-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> restituisce la dimensione dopo il marshalling del tipo, mentre `sizeof` restituisce la dimensione allocata da Common Language Runtime, che include eventuali spaziature interne.</span><span class="sxs-lookup"><span data-stu-id="77724-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>

## <a name="example"></a><span data-ttu-id="77724-133">Esempio</span><span class="sxs-lookup"><span data-stu-id="77724-133">Example</span></span>

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a><span data-ttu-id="77724-134">Specifiche del linguaggio C#</span><span class="sxs-lookup"><span data-stu-id="77724-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="77724-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77724-135">See also</span></span>

- [<span data-ttu-id="77724-136">Riferimenti per C#</span><span class="sxs-lookup"><span data-stu-id="77724-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="77724-137">Guida per programmatori C#</span><span class="sxs-lookup"><span data-stu-id="77724-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="77724-138">Parole chiave di C#</span><span class="sxs-lookup"><span data-stu-id="77724-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="77724-139">enum</span><span class="sxs-lookup"><span data-stu-id="77724-139">enum</span></span>](enum.md)
- [<span data-ttu-id="77724-140">Codice unsafe e puntatori</span><span class="sxs-lookup"><span data-stu-id="77724-140">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="77724-141">Struct</span><span class="sxs-lookup"><span data-stu-id="77724-141">Structs</span></span>](../../programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="77724-142">Costanti</span><span class="sxs-lookup"><span data-stu-id="77724-142">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)
