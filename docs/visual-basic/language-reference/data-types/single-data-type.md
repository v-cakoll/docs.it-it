---
title: Tipo di dati Single
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
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343924"
---
# <a name="single-data-type-visual-basic"></a><span data-ttu-id="fd228-102">Tipo di dati Single (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd228-102">Single Data Type (Visual Basic)</span></span>

<span data-ttu-id="fd228-103">Include numeri a virgola mobile a precisione singola IEEE a 32 bit (4 byte) compresi tra-3.4028235 E + 38 e-401298E E-45 per i valori negativi e da 401298E E-45 a 3.4028235 E + 38 per i valori positivi.</span><span class="sxs-lookup"><span data-stu-id="fd228-103">Holds signed IEEE 32-bit (4-byte) single-precision floating-point numbers ranging in value from -3.4028235E+38 through -1.401298E-45 for negative values and from 1.401298E-45 through 3.4028235E+38 for positive values.</span></span> <span data-ttu-id="fd228-104">I numeri a precisione singola archiviano un'approssimazione di un numero reale.</span><span class="sxs-lookup"><span data-stu-id="fd228-104">Single-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd228-105">Note</span><span class="sxs-lookup"><span data-stu-id="fd228-105">Remarks</span></span>  

 <span data-ttu-id="fd228-106">Utilizzare il tipo di dati `Single` per contenere valori a virgola mobile che non richiedono la larghezza completa dei dati di `Double`.</span><span class="sxs-lookup"><span data-stu-id="fd228-106">Use the `Single` data type to contain floating-point values that do not require the full data width of `Double`.</span></span> <span data-ttu-id="fd228-107">In alcuni casi è possibile che il Common Language Runtime sia in grado di comprimere le variabili di `Single` e di risparmiare sull'utilizzo della memoria.</span><span class="sxs-lookup"><span data-stu-id="fd228-107">In some cases the common language runtime might be able to pack your `Single` variables closely together and save memory consumption.</span></span>  
  
 <span data-ttu-id="fd228-108">Il valore predefinito di `Single` è 0.</span><span class="sxs-lookup"><span data-stu-id="fd228-108">The default value of `Single` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="fd228-109">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="fd228-109">Programming Tips</span></span>  
  
- <span data-ttu-id="fd228-110">**Precisione.**</span><span class="sxs-lookup"><span data-stu-id="fd228-110">**Precision.**</span></span> <span data-ttu-id="fd228-111">Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione precisa in memoria.</span><span class="sxs-lookup"><span data-stu-id="fd228-111">When you work with floating-point numbers, keep in mind that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="fd228-112">Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l'operatore `Mod`.</span><span class="sxs-lookup"><span data-stu-id="fd228-112">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="fd228-113">Per ulteriori informazioni, vedere [risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="fd228-113">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
- <span data-ttu-id="fd228-114">**Conversioni.**</span><span class="sxs-lookup"><span data-stu-id="fd228-114">**Widening.**</span></span> <span data-ttu-id="fd228-115">Il tipo di dati `Single` viene ampliato `Double`.</span><span class="sxs-lookup"><span data-stu-id="fd228-115">The `Single` data type widens to `Double`.</span></span> <span data-ttu-id="fd228-116">Ciò significa che è possibile convertire `Single` in `Double` senza riscontrare un errore di <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd228-116">This means you can convert `Single` to `Double` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>  
  
- <span data-ttu-id="fd228-117">**Zeri finali.**</span><span class="sxs-lookup"><span data-stu-id="fd228-117">**Trailing Zeros.**</span></span> <span data-ttu-id="fd228-118">I tipi di dati a virgola mobile non hanno alcuna rappresentazione interna di caratteri finali 0.</span><span class="sxs-lookup"><span data-stu-id="fd228-118">The floating-point data types do not have any internal representation of trailing 0 characters.</span></span> <span data-ttu-id="fd228-119">Ad esempio, non si distinguono tra 4,2000 e 4,2.</span><span class="sxs-lookup"><span data-stu-id="fd228-119">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="fd228-120">Di conseguenza, i caratteri finali 0 non vengono visualizzati quando si visualizzano o stampano valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="fd228-120">Consequently, trailing 0 characters do not appear when you display or print floating-point values.</span></span>  
  
- <span data-ttu-id="fd228-121">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="fd228-121">**Type Characters.**</span></span> <span data-ttu-id="fd228-122">Aggiungendo il carattere di tipo letterale `F` a un valore letterale, se ne determina la conversione nel tipo di dati `Single`.</span><span class="sxs-lookup"><span data-stu-id="fd228-122">Appending the literal type character `F` to a literal forces it to the `Single` data type.</span></span> <span data-ttu-id="fd228-123">Aggiungendo il carattere identificatore di tipo `!` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Single`.</span><span class="sxs-lookup"><span data-stu-id="fd228-123">Appending the identifier type character `!` to any identifier forces it to `Single`.</span></span>  
  
- <span data-ttu-id="fd228-124">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="fd228-124">**Framework Type.**</span></span> <span data-ttu-id="fd228-125">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Single?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd228-125">The corresponding type in the .NET Framework is the <xref:System.Single?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd228-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd228-126">See also</span></span>

- <xref:System.Single?displayProperty=nameWithType>
- [<span data-ttu-id="fd228-127">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="fd228-127">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="fd228-128">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="fd228-128">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="fd228-129">Tipo di dati Double</span><span class="sxs-lookup"><span data-stu-id="fd228-129">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [<span data-ttu-id="fd228-130">CString</span><span class="sxs-lookup"><span data-stu-id="fd228-130">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="fd228-131">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="fd228-131">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="fd228-132">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="fd228-132">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="fd228-133">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="fd228-133">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
