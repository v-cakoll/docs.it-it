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
ms.openlocfilehash: 899554f427ac77ead465752c35e51ca88d045763
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415634"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="0b671-102">Tipo di dati Double (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b671-102">Double Data Type (Visual Basic)</span></span>

<span data-ttu-id="0b671-103">Include numeri a virgola mobile a precisione doppia IEEE a 64 bit (8 byte) che variano in base al valore da-1.79769313486231570 E + 308 a-4.94065645841246544 E-324 per i valori negativi e da 4.94065645841246544 E-324 a 1.79769313486231570 E + 308 per i valori positivi.</span><span class="sxs-lookup"><span data-stu-id="0b671-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="0b671-104">I numeri a precisione doppia archiviano un'approssimazione di un numero reale.</span><span class="sxs-lookup"><span data-stu-id="0b671-104">Double-precision numbers store an approximation of a real number.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b671-105">Commenti</span><span class="sxs-lookup"><span data-stu-id="0b671-105">Remarks</span></span>

<span data-ttu-id="0b671-106">Il `Double` tipo di dati fornisce le Magnitude più grandi e minime possibili per un numero.</span><span class="sxs-lookup"><span data-stu-id="0b671-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>

<span data-ttu-id="0b671-107">Il valore predefinito di `Double` è 0.</span><span class="sxs-lookup"><span data-stu-id="0b671-107">The default value of `Double` is 0.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="0b671-108">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="0b671-108">Programming Tips</span></span>

- <span data-ttu-id="0b671-109">**Precisione.**</span><span class="sxs-lookup"><span data-stu-id="0b671-109">**Precision.**</span></span> <span data-ttu-id="0b671-110">Quando si utilizzano numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione precisa in memoria.</span><span class="sxs-lookup"><span data-stu-id="0b671-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="0b671-111">Questo può causare risultati imprevisti di determinate operazioni, ad esempio il confronto dei valori e l' `Mod` operatore.</span><span class="sxs-lookup"><span data-stu-id="0b671-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="0b671-112">Per ulteriori informazioni, vedere [risoluzione dei problemi](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="0b671-112">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

- <span data-ttu-id="0b671-113">**Zeri finali.**</span><span class="sxs-lookup"><span data-stu-id="0b671-113">**Trailing Zeros.**</span></span> <span data-ttu-id="0b671-114">I tipi di dati a virgola mobile non hanno alcuna rappresentazione interna di caratteri zero finali.</span><span class="sxs-lookup"><span data-stu-id="0b671-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="0b671-115">Ad esempio, non si distinguono tra 4,2000 e 4,2.</span><span class="sxs-lookup"><span data-stu-id="0b671-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="0b671-116">Di conseguenza, i caratteri zero finali non vengono visualizzati quando si visualizzano o stampano valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="0b671-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>

- <span data-ttu-id="0b671-117">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="0b671-117">**Type Characters.**</span></span> <span data-ttu-id="0b671-118">Aggiungendo il carattere di tipo letterale `R` a un valore letterale, se ne determina la conversione nel tipo di dati `Double`.</span><span class="sxs-lookup"><span data-stu-id="0b671-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="0b671-119">Se, ad esempio, un valore integer è seguito da `R` , il valore viene modificato in un oggetto `Double` .</span><span class="sxs-lookup"><span data-stu-id="0b671-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  <span data-ttu-id="0b671-120">Aggiungendo il carattere identificatore di tipo `#` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Double`.</span><span class="sxs-lookup"><span data-stu-id="0b671-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="0b671-121">Nell'esempio seguente la variabile `num` è tipizzata come `Double` :</span><span class="sxs-lookup"><span data-stu-id="0b671-121">In the following example, the variable `num` is typed as a `Double`:</span></span>

  ```vb
  Dim num# = 3
  ```

- <span data-ttu-id="0b671-122">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="0b671-122">**Framework Type.**</span></span> <span data-ttu-id="0b671-123">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0b671-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b671-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b671-124">See also</span></span>

- <xref:System.Double?displayProperty=nameWithType>
- [<span data-ttu-id="0b671-125">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0b671-125">Data Types</span></span>](index.md)
- [<span data-ttu-id="0b671-126">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="0b671-126">Decimal Data Type</span></span>](decimal-data-type.md)
- [<span data-ttu-id="0b671-127">Tipo di dati Single</span><span class="sxs-lookup"><span data-stu-id="0b671-127">Single Data Type</span></span>](single-data-type.md)
- [<span data-ttu-id="0b671-128">CString</span><span class="sxs-lookup"><span data-stu-id="0b671-128">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="0b671-129">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="0b671-129">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="0b671-130">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0b671-130">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="0b671-131">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0b671-131">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="0b671-132">Caratteri tipo</span><span class="sxs-lookup"><span data-stu-id="0b671-132">Type Characters</span></span>](../../programming-guide/language-features/data-types/type-characters.md)
