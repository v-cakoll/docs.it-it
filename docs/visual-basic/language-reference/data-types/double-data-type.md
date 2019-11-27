---
title: Tipo di dati Double
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 347b5c7b7af4c4aafec0f91aca46a8cf640236b9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344006"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="662dd-102">Tipo di dati Double (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="662dd-102">Double Data Type (Visual Basic)</span></span>

<span data-ttu-id="662dd-103">Include numeri a virgola mobile a precisione doppia a IEEE 64 bit (8 byte) che variano in base al valore da-1.79769313486231570 E + 308 a-4.94065645841246544 E-324 per i valori negativi e da 4.94065645841246544 E-324 a 1.79769313486231570 E + 308 per valori positivi.</span><span class="sxs-lookup"><span data-stu-id="662dd-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="662dd-104">I numeri a precisione doppia archiviano un'approssimazione di un numero reale.</span><span class="sxs-lookup"><span data-stu-id="662dd-104">Double-precision numbers store an approximation of a real number.</span></span>

## <a name="remarks"></a><span data-ttu-id="662dd-105">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="662dd-105">Remarks</span></span>

<span data-ttu-id="662dd-106">Il tipo di dati `Double` fornisce le Magnitude più grandi e minime possibili per un numero.</span><span class="sxs-lookup"><span data-stu-id="662dd-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>

<span data-ttu-id="662dd-107">Il valore predefinito di `Double` è 0.</span><span class="sxs-lookup"><span data-stu-id="662dd-107">The default value of `Double` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="662dd-108">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="662dd-108">Programming Tips</span></span>

- <span data-ttu-id="662dd-109">**Precisione.**</span><span class="sxs-lookup"><span data-stu-id="662dd-109">**Precision.**</span></span> <span data-ttu-id="662dd-110">Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione precisa in memoria.</span><span class="sxs-lookup"><span data-stu-id="662dd-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="662dd-111">Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l'operatore `Mod`.</span><span class="sxs-lookup"><span data-stu-id="662dd-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="662dd-112">Per ulteriori informazioni, vedere [risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="662dd-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

- <span data-ttu-id="662dd-113">**Zeri finali.**</span><span class="sxs-lookup"><span data-stu-id="662dd-113">**Trailing Zeros.**</span></span> <span data-ttu-id="662dd-114">I tipi di dati a virgola mobile non hanno alcuna rappresentazione interna di caratteri zero finali.</span><span class="sxs-lookup"><span data-stu-id="662dd-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="662dd-115">Ad esempio, non si distinguono tra 4,2000 e 4,2.</span><span class="sxs-lookup"><span data-stu-id="662dd-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="662dd-116">Di conseguenza, i caratteri zero finali non vengono visualizzati quando si visualizzano o stampano valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="662dd-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>

- <span data-ttu-id="662dd-117">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="662dd-117">**Type Characters.**</span></span> <span data-ttu-id="662dd-118">Aggiungendo il carattere di tipo letterale `R` a un valore letterale, se ne determina la conversione nel tipo di dati `Double`.</span><span class="sxs-lookup"><span data-stu-id="662dd-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="662dd-119">Se, ad esempio, un valore integer è seguito da `R`, il valore viene modificato in una `Double`.</span><span class="sxs-lookup"><span data-stu-id="662dd-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  <span data-ttu-id="662dd-120">Aggiungendo il carattere identificatore di tipo `#` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Double`.</span><span class="sxs-lookup"><span data-stu-id="662dd-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="662dd-121">Nell'esempio seguente, la variabile `num` viene digitata come `Double`:</span><span class="sxs-lookup"><span data-stu-id="662dd-121">In the following example, the variable `num` is typed as a `Double`:</span></span>

  ```vb
  Dim num# = 3
  ```

- <span data-ttu-id="662dd-122">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="662dd-122">**Framework Type.**</span></span> <span data-ttu-id="662dd-123">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="662dd-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="662dd-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="662dd-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="662dd-125">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="662dd-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="662dd-126">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="662dd-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [<span data-ttu-id="662dd-127">Tipo di dati Single</span><span class="sxs-lookup"><span data-stu-id="662dd-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [<span data-ttu-id="662dd-128">CString</span><span class="sxs-lookup"><span data-stu-id="662dd-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="662dd-129">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="662dd-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="662dd-130">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="662dd-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="662dd-131">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="662dd-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="662dd-132">Caratteri tipo</span><span class="sxs-lookup"><span data-stu-id="662dd-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
