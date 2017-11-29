---
title: Operatori bit per bit (F#)
description: 'Informazioni sugli operatori bit per bit disponibili in F # linguaggio di programmazione.'
keywords: visual f#, f#, programmazione funzionale
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8a2c87f5-b4c7-47fe-8580-82c956f605e5
ms.openlocfilehash: 61a8e6bafe97a229480c967a4afb5d2a256474c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="bitwise-operators"></a><span data-ttu-id="0107d-104">Operatori bit per bit</span><span class="sxs-lookup"><span data-stu-id="0107d-104">Bitwise Operators</span></span>

<span data-ttu-id="0107d-105">Questo argomento descrive gli operatori bit per bit sono disponibili nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="0107d-105">This topic describes bitwise operators that are available in the F# language.</span></span>

## <a name="summary-of-bitwise-operators"></a><span data-ttu-id="0107d-106">Riepilogo degli operatori bit per bit</span><span class="sxs-lookup"><span data-stu-id="0107d-106">Summary of Bitwise Operators</span></span>
<span data-ttu-id="0107d-107">Nella tabella seguente descrive gli operatori bit per bit supportati per i tipi integrali unboxed nel linguaggio F #.</span><span class="sxs-lookup"><span data-stu-id="0107d-107">The following table describes the bitwise operators that are supported for unboxed integral types in the F# language.</span></span>

|<span data-ttu-id="0107d-108">Operatore</span><span class="sxs-lookup"><span data-stu-id="0107d-108">Operator</span></span>|<span data-ttu-id="0107d-109">Note</span><span class="sxs-lookup"><span data-stu-id="0107d-109">Notes</span></span>|
|--------|-----|
|`&&&`|<span data-ttu-id="0107d-110">Operatore AND bit per bit.</span><span class="sxs-lookup"><span data-stu-id="0107d-110">Bitwise AND operator.</span></span> <span data-ttu-id="0107d-111">I bit nel risultato hanno il valore 1 solo se i bit corrispondenti in entrambi gli operandi di origine sono 1.</span><span class="sxs-lookup"><span data-stu-id="0107d-111">Bits in the result have the value 1 if and only if the corresponding bits in both source operands are 1.</span></span>|
|<code>&#124;&#124;&#124;</code>|<span data-ttu-id="0107d-112">Operatore OR bit per bit.</span><span class="sxs-lookup"><span data-stu-id="0107d-112">Bitwise OR operator.</span></span> <span data-ttu-id="0107d-113">I bit nel risultato hanno il valore 1 se entrambi i bit corrispondenti nell'origine gli operandi sono di 1.</span><span class="sxs-lookup"><span data-stu-id="0107d-113">Bits in the result have the value 1 if either of the corresponding bits in the source operands are 1.</span></span>|
|`^^^`|<span data-ttu-id="0107d-114">Bit per bit esclusivo operatore OR.</span><span class="sxs-lookup"><span data-stu-id="0107d-114">Bitwise exclusive OR operator.</span></span> <span data-ttu-id="0107d-115">I bit nel risultato hanno il valore 1 se e solo se i bit negli operandi di origine hanno valori uguali.</span><span class="sxs-lookup"><span data-stu-id="0107d-115">Bits in the result have the value 1 if and only if bits in the source operands have unequal values.</span></span>|
|`~~~`|<span data-ttu-id="0107d-116">Operatore di negazione bit per bit.</span><span class="sxs-lookup"><span data-stu-id="0107d-116">Bitwise negation operator.</span></span> <span data-ttu-id="0107d-117">Questo è un operatore unario e produce un risultato in cui tutti i bit 0 nell'operando di origine vengono convertiti in bit 1 e tutti i componenti di 1 vengono convertiti in bit 0.</span><span class="sxs-lookup"><span data-stu-id="0107d-117">This is a unary operator and produces a result in which all 0 bits in the source operand are converted to 1 bits and all 1 bits are converted to 0 bits.</span></span>|
|`<<<`|<span data-ttu-id="0107d-118">Bit per bit (operatore di spostamento a sinistra).</span><span class="sxs-lookup"><span data-stu-id="0107d-118">Bitwise left-shift operator.</span></span> <span data-ttu-id="0107d-119">Il risultato è che il primo operando con i bit spostati a sinistra del numero di bit nel secondo operando.</span><span class="sxs-lookup"><span data-stu-id="0107d-119">The result is the first operand with bits shifted left by the number of bits in the second operand.</span></span> <span data-ttu-id="0107d-120">I bit spostati dalla posizione più significativa non vengono ruotati nella posizione meno significativa.</span><span class="sxs-lookup"><span data-stu-id="0107d-120">Bits shifted off the most significant position are not rotated into the least significant position.</span></span> <span data-ttu-id="0107d-121">Il bit meno significativi vengono riempite con zeri.</span><span class="sxs-lookup"><span data-stu-id="0107d-121">The least significant bits are padded with zeros.</span></span> <span data-ttu-id="0107d-122">Il tipo del secondo argomento è `int32`.</span><span class="sxs-lookup"><span data-stu-id="0107d-122">The type of the second argument is `int32`.</span></span>|
|`>>>`|<span data-ttu-id="0107d-123">Bit per bit (operatore di spostamento a destra).</span><span class="sxs-lookup"><span data-stu-id="0107d-123">Bitwise right-shift operator.</span></span> <span data-ttu-id="0107d-124">Il risultato è il primo operando con i bit spostati a destra del numero di bit nel secondo operando.</span><span class="sxs-lookup"><span data-stu-id="0107d-124">The result is the first operand with bits shifted right by the number of bits in the second operand.</span></span> <span data-ttu-id="0107d-125">I bit spostati dalla posizione meno significativa non vengono ruotati nella posizione più significativa.</span><span class="sxs-lookup"><span data-stu-id="0107d-125">Bits shifted off the least significant position are not rotated into the most significant position.</span></span> <span data-ttu-id="0107d-126">Per i tipi senza segno, il bit più significativi vengono riempite con zeri.</span><span class="sxs-lookup"><span data-stu-id="0107d-126">For unsigned types, the most significant bits are padded with zeros.</span></span> <span data-ttu-id="0107d-127">Per i tipi con segno, il bit più significativi vengono riempiti con quelle.</span><span class="sxs-lookup"><span data-stu-id="0107d-127">For signed types, the most significant bits are padded with ones.</span></span> <span data-ttu-id="0107d-128">Il tipo del secondo argomento è `int32`.</span><span class="sxs-lookup"><span data-stu-id="0107d-128">The type of the second argument is `int32`.</span></span>|

<span data-ttu-id="0107d-129">I tipi seguenti sono utilizzabili con operatori bit per bit: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, e `unativeint`.</span><span class="sxs-lookup"><span data-stu-id="0107d-129">The following types can be used with bitwise operators: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, and `unativeint`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0107d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0107d-130">See Also</span></span>
[<span data-ttu-id="0107d-131">Riferimenti per simboli e operatori</span><span class="sxs-lookup"><span data-stu-id="0107d-131">Symbol and Operator Reference</span></span>](index.md)

[<span data-ttu-id="0107d-132">Operatori aritmetici</span><span class="sxs-lookup"><span data-stu-id="0107d-132">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="0107d-133">Operatori booleani</span><span class="sxs-lookup"><span data-stu-id="0107d-133">Boolean Operators</span></span>](boolean-operators.md)

