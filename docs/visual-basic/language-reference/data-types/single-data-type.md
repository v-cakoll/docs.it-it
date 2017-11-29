---
title: Tipo di dati Single (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c91dbdf73ed1e26393518001ec8651557e5b780f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="21b90-102">Tipo di dati Single (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21b90-102">Single Data Type (Visual Basic)</span></span>
<span data-ttu-id="21b90-103">Contiene con segno a 32 bit IEEE (4 byte) e con precisione singola numeri a virgola mobile compresi nell'intervallo da - 3, 4028235E + 38 e-1, 401298E-45 per i valori negativi e tra 1, 401298E-45 a 3, 4028235E + 38 per i valori positivi.</span><span class="sxs-lookup"><span data-stu-id="21b90-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="21b90-104">Numeri a precisione singola archiviano un'approssimazione di un numero reale.</span><span class="sxs-lookup"><span data-stu-id="21b90-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21b90-105">Note</span><span class="sxs-lookup"><span data-stu-id="21b90-105">Remarks</span></span>  
 <span data-ttu-id="21b90-106">Utilizzare il `Single` il tipo di dati per contenere i valori a virgola mobile che non richiedono l'ampiezza dei dati completo `Double`.</span><span class="sxs-lookup"><span data-stu-id="21b90-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="21b90-107">In alcuni casi potrebbe essere in grado di pack common language runtime il `Single` variabili e ridurre il consumo di memoria.</span><span class="sxs-lookup"><span data-stu-id="21b90-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="21b90-108">Il valore predefinito di `Single` è 0.</span><span class="sxs-lookup"><span data-stu-id="21b90-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="21b90-109">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="21b90-109">Programming Tips</span></span>  
  
-   <span data-ttu-id="21b90-110">**Precisione.**</span><span class="sxs-lookup"><span data-stu-id="21b90-110">**Precision.**</span></span> <span data-ttu-id="21b90-111">Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre contengono una precisa rappresentazione in memoria.</span><span class="sxs-lookup"><span data-stu-id="21b90-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="21b90-112">Ciò potrebbe provocare risultati imprevisti da alcune operazioni, ad esempio il confronto di valori e `Mod` operatore.</span><span class="sxs-lookup"><span data-stu-id="21b90-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="21b90-113">Per ulteriori informazioni, vedere [risoluzione dei problemi dei tipi di dati](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="21b90-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="21b90-114">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="21b90-114">**Widening.**</span></span> <span data-ttu-id="21b90-115">Il `Single` può ampliarsi nel tipo di dati `Double`.</span><span class="sxs-lookup"><span data-stu-id="21b90-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="21b90-116">È pertanto possibile convertire `Single` a `Double` senza che si verifichi un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="21b90-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="21b90-117">**Zeri finali.**</span><span class="sxs-lookup"><span data-stu-id="21b90-117">**Trailing Zeros.**</span></span> <span data-ttu-id="21b90-118">I tipi di dati a virgola mobile non dispone di alcuna rappresentazione interna di caratteri 0 finali.</span><span class="sxs-lookup"><span data-stu-id="21b90-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="21b90-119">Ad esempio, non distingue tra 4,2000 e 4.2.</span><span class="sxs-lookup"><span data-stu-id="21b90-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="21b90-120">Di conseguenza, i caratteri 0 finali non vengono visualizzati quando si visualizzano o stampare i valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="21b90-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="21b90-121">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="21b90-121">**Type Characters.**</span></span> <span data-ttu-id="21b90-122">Aggiungendo il carattere di tipo letterale `F` a un valore letterale, se ne determina la conversione nel tipo di dati `Single`.</span><span class="sxs-lookup"><span data-stu-id="21b90-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="21b90-123">Aggiungendo il carattere identificatore di tipo `!` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Single`.</span><span class="sxs-lookup"><span data-stu-id="21b90-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
-   <span data-ttu-id="21b90-124">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="21b90-124">**Framework Type.**</span></span> <span data-ttu-id="21b90-125">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Single?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="21b90-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b90-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="21b90-126">See Also</span></span>  
 <xref:System.Single?displayProperty=nameWithType>  
 [<span data-ttu-id="21b90-127">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="21b90-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="21b90-128">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="21b90-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [<span data-ttu-id="21b90-129">Tipo di dati Double</span><span class="sxs-lookup"><span data-stu-id="21b90-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [<span data-ttu-id="21b90-130">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="21b90-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="21b90-131">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="21b90-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="21b90-132">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="21b90-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="21b90-133">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="21b90-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
