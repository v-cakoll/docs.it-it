---
title: Operatori bit per bit (F#)
description: 'Informazioni sugli operatori bit per bit disponibili in F # linguaggio di programmazione.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 4d5abff564a5d1dcbe52b99edf431ca10e442061
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2018
---
# <a name="bitwise-operators"></a><span data-ttu-id="74d4d-103">Operatori bit per bit</span><span class="sxs-lookup"><span data-stu-id="74d4d-103">Bitwise Operators</span></span>

<span data-ttu-id="74d4d-104">Questo argomento descrive gli operatori bit per bit sono disponibili nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="74d4d-104">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="74d4d-105">Riepilogo degli operatori bit per bit</span><span class="sxs-lookup"><span data-stu-id="74d4d-105">Summary of Bitwise Operators</span></span>
<span data-ttu-id="74d4d-106">Nella tabella seguente descrive gli operatori bit per bit supportati per i tipi integrali unboxed nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="74d4d-106">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="74d4d-107">Operatore</span><span class="sxs-lookup"><span data-stu-id="74d4d-107">Operator</span></span>|<span data-ttu-id="74d4d-108">Note</span><span class="sxs-lookup"><span data-stu-id="74d4d-108">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="74d4d-109">Operatore AND bit per bit.</span><span class="sxs-lookup"><span data-stu-id="74d4d-109">Bitwise AND operator.</span></span> <span data-ttu-id="74d4d-110">I bit nel risultato hanno il valore 1 solo se i bit corrispondenti in entrambi gli operandi di origine sono 1.</span><span class="sxs-lookup"><span data-stu-id="74d4d-110">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="74d4d-111">Operatore OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="74d4d-111">Bitwise OR operator.</span></span> <span data-ttu-id="74d4d-112">I bit nel risultato hanno il valore 1 se entrambi i bit corrispondenti nell'origine gli operandi sono di 1.</span><span class="sxs-lookup"><span data-stu-id="74d4d-112">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="74d4d-113">Bit per bit esclusivo operatore OR.</span><span class="sxs-lookup"><span data-stu-id="74d4d-113">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="74d4d-114">I bit nel risultato hanno il valore 1 se e solo se i bit negli operandi di origine hanno valori uguali.</span><span class="sxs-lookup"><span data-stu-id="74d4d-114">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="74d4d-115">Operatore di negazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="74d4d-115">Bitwise negation operator.</span></span> <span data-ttu-id="74d4d-116">Questo è un operatore unario e produce un risultato in cui tutti i bit 0 nell'operando di origine vengono convertiti in bit 1 e tutti i componenti di 1 vengono convertiti in bit 0.</span><span class="sxs-lookup"><span data-stu-id="74d4d-116">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="74d4d-117">Bit per bit (operatore di spostamento a sinistra).</span><span class="sxs-lookup"><span data-stu-id="74d4d-117">Bitwise left-shift operator.</span></span> <span data-ttu-id="74d4d-118">Il risultato è che il primo operando con i bit spostati a sinistra del numero di bit nel secondo operando.</span><span class="sxs-lookup"><span data-stu-id="74d4d-118">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="74d4d-119">I bit spostati dalla posizione più significativa non vengono ruotati nella posizione meno significativa.</span><span class="sxs-lookup"><span data-stu-id="74d4d-119">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="74d4d-120">Il bit meno significativi vengono riempite con zeri.</span><span class="sxs-lookup"><span data-stu-id="74d4d-120">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="74d4d-121">Il tipo del secondo argomento è `int32`.</span><span class="sxs-lookup"><span data-stu-id="74d4d-121">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="74d4d-122">Bit per bit (operatore di spostamento a destra).</span><span class="sxs-lookup"><span data-stu-id="74d4d-122">Bitwise right-shift operator.</span></span> <span data-ttu-id="74d4d-123">Il risultato è il primo operando con i bit spostati a destra del numero di bit nel secondo operando.</span><span class="sxs-lookup"><span data-stu-id="74d4d-123">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="74d4d-124">I bit spostati dalla posizione meno significativa non vengono ruotati nella posizione più significativa.</span><span class="sxs-lookup"><span data-stu-id="74d4d-124">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="74d4d-125">Per i tipi senza segno, il bit più significativi vengono riempite con zeri.</span><span class="sxs-lookup"><span data-stu-id="74d4d-125">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="74d4d-126">Per i tipi con segno, il bit più significativi vengono riempiti con quelle.</span><span class="sxs-lookup"><span data-stu-id="74d4d-126">For signed types, the most significant bits are padded with ones.</span></span> <span data-ttu-id="74d4d-127">Il tipo del secondo argomento è `int32`.</span><span class="sxs-lookup"><span data-stu-id="74d4d-127">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="74d4d-128">I tipi seguenti sono utilizzabili con operatori bit per bit: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, e `unativeint`.</span><span class="sxs-lookup"><span data-stu-id="74d4d-128">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="74d4d-129">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="74d4d-129">See Also</span></span>
[<span data-ttu-id="74d4d-130">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="74d4d-130">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="74d4d-131">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="74d4d-131">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="74d4d-132">Operatori booleani</span><span class="sxs-lookup"><span data-stu-id="74d4d-132">Boolean Operators</span></span>](boolean-operators.md)

