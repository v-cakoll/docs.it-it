---
title: Tipo di dati Single (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Single
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
ms.openlocfilehash: 98433c0f1d1008664bb994f3b43fe48a753a432c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43803727"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="95673-102">Tipo di dati Single (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95673-102">Single Data Type (Visual Basic)</span></span>
<span data-ttu-id="95673-103">Contiene con segno a 32 bit IEEE (4 byte) e con precisione singola numeri a virgola mobile con valore compreso tra - 3,4028235E + 38 e - 1,401298E-45 per valori negativi e tra 1,401298E-45 e 3,4028235E + 38 per i valori positivi.</span><span class="sxs-lookup"><span data-stu-id="95673-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="95673-104">Numeri a precisione singola contengono un'approssimazione di un numero reale.</span><span class="sxs-lookup"><span data-stu-id="95673-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95673-105">Note</span><span class="sxs-lookup"><span data-stu-id="95673-105">Remarks</span></span>  
 <span data-ttu-id="95673-106">Usare la `Single` tipo di dati contengono valori a virgola mobile che non richiedono l'intera ampiezza dei dati `Double`.</span><span class="sxs-lookup"><span data-stu-id="95673-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="95673-107">In alcuni casi, common language runtime potrebbe essere possibile riunire i `Single` variabili e ridurre il consumo di memoria.</span><span class="sxs-lookup"><span data-stu-id="95673-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="95673-108">Il valore predefinito di `Single` è 0.</span><span class="sxs-lookup"><span data-stu-id="95673-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="95673-109">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="95673-109">Programming Tips</span></span>  
  
-   <span data-ttu-id="95673-110">**Precisione.**</span><span class="sxs-lookup"><span data-stu-id="95673-110">**Precision.**</span></span> <span data-ttu-id="95673-111">Quando si lavora con numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione esatta in memoria.</span><span class="sxs-lookup"><span data-stu-id="95673-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="95673-112">Ciò potrebbe provocare risultati imprevisti da determinate operazioni, ad esempio il confronto dei valori e `Mod` operatore.</span><span class="sxs-lookup"><span data-stu-id="95673-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="95673-113">Per altre informazioni, vedere [tipi di dati di risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="95673-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="95673-114">**Ampliamento.**</span><span class="sxs-lookup"><span data-stu-id="95673-114">**Widening.**</span></span> <span data-ttu-id="95673-115">Il `Single` può ampliarsi nel tipo di dati `Double`.</span><span class="sxs-lookup"><span data-stu-id="95673-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="95673-116">Ciò significa che è possibile convertire `Single` al `Double` senza che si verifichi un <xref:System.OverflowException?displayProperty=nameWithType> errore.</span><span class="sxs-lookup"><span data-stu-id="95673-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
-   <span data-ttu-id="95673-117">**Zeri finali.**</span><span class="sxs-lookup"><span data-stu-id="95673-117">**Trailing Zeros.**</span></span> <span data-ttu-id="95673-118">I tipi di dati a virgola mobile non è qualsiasi rappresentazione interna di 0 caratteri finali.</span><span class="sxs-lookup"><span data-stu-id="95673-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="95673-119">Ad esempio, essi non viene fatta distinzione tra 4,2000 e 4.2.</span><span class="sxs-lookup"><span data-stu-id="95673-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="95673-120">Di conseguenza, i caratteri 0 finali non vengono visualizzati quando si visualizzano o stampare valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="95673-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="95673-121">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="95673-121">**Type Characters.**</span></span> <span data-ttu-id="95673-122">Aggiungendo il carattere di tipo letterale `F` a un valore letterale, se ne determina la conversione nel tipo di dati `Single`.</span><span class="sxs-lookup"><span data-stu-id="95673-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="95673-123">Aggiungendo il carattere identificatore di tipo `!` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Single`.</span><span class="sxs-lookup"><span data-stu-id="95673-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
-   <span data-ttu-id="95673-124">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="95673-124">**Framework Type.**</span></span> <span data-ttu-id="95673-125">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Single?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="95673-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95673-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="95673-126">See Also</span></span>  
 <xref:System.Single?displayProperty=nameWithType>  
 [<span data-ttu-id="95673-127">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="95673-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="95673-128">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="95673-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [<span data-ttu-id="95673-129">Tipo di dati Double</span><span class="sxs-lookup"><span data-stu-id="95673-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [<span data-ttu-id="95673-130">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="95673-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="95673-131">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="95673-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="95673-132">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="95673-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="95673-133">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="95673-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
