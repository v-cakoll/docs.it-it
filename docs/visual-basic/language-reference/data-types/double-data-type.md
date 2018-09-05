---
title: Tipo di dati Double (Visual Basic)
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
ms.openlocfilehash: 5d2d84f298b9cf6138e84ef287f6ea9212da2960
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734812"
---
# <a name="double-data-type-visual-basic"></a><span data-ttu-id="9a67a-102">Tipo di dati Double (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9a67a-102">Double Data Type (Visual Basic)</span></span>
<span data-ttu-id="9a67a-103">Contiene segno IEEE a 64 bit (8 byte) e con precisione doppia numeri a virgola mobile che intervallo compreso tra - 1, 79769313486231570E + 308 a - fino a 4.94065645841246544-324 per i valori negativi e tra fino a 4.94065645841246544-324 e 1.79769313486231570 e + 308 per valori positivi.</span><span class="sxs-lookup"><span data-stu-id="9a67a-103">Holds signed IEEE 64-bit (8-byte) double-precision floating-point numbers that range in value from -1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values and from 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span> <span data-ttu-id="9a67a-104">Numeri a precisione doppia contengono un'approssimazione di un numero reale.</span><span class="sxs-lookup"><span data-stu-id="9a67a-104">Double-precision numbers store an approximation of a real number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a67a-105">Note</span><span class="sxs-lookup"><span data-stu-id="9a67a-105">Remarks</span></span>  
 <span data-ttu-id="9a67a-106">Il `Double` tipo di dati fornisce la grandezza più grande e più piccolo possibile per un numero.</span><span class="sxs-lookup"><span data-stu-id="9a67a-106">The `Double` data type provides the largest and smallest possible magnitudes for a number.</span></span>  
  
 <span data-ttu-id="9a67a-107">Il valore predefinito di `Double` è 0.</span><span class="sxs-lookup"><span data-stu-id="9a67a-107">The default value of `Double` is 0.</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="9a67a-108">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="9a67a-108">Programming Tips</span></span>  
  
-   <span data-ttu-id="9a67a-109">**Precisione.**</span><span class="sxs-lookup"><span data-stu-id="9a67a-109">**Precision.**</span></span> <span data-ttu-id="9a67a-110">Quando si lavora con numeri a virgola mobile, tenere presente che non sempre hanno una rappresentazione esatta in memoria.</span><span class="sxs-lookup"><span data-stu-id="9a67a-110">When you work with floating-point numbers, remember that they do not always have a precise representation in memory.</span></span> <span data-ttu-id="9a67a-111">Ciò potrebbe provocare risultati imprevisti da determinate operazioni, ad esempio il confronto dei valori e `Mod` operatore.</span><span class="sxs-lookup"><span data-stu-id="9a67a-111">This could lead to unexpected results from certain operations, such as value comparison and the `Mod` operator.</span></span> <span data-ttu-id="9a67a-112">Per altre informazioni, vedere [tipi di dati di risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="9a67a-112">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
-   <span data-ttu-id="9a67a-113">**Zeri finali.**</span><span class="sxs-lookup"><span data-stu-id="9a67a-113">**Trailing Zeros.**</span></span> <span data-ttu-id="9a67a-114">I tipi di dati a virgola mobile non è qualsiasi rappresentazione interna di zeri finali.</span><span class="sxs-lookup"><span data-stu-id="9a67a-114">The floating-point data types do not have any internal representation of trailing zero characters.</span></span> <span data-ttu-id="9a67a-115">Ad esempio, essi non viene fatta distinzione tra 4,2000 e 4.2.</span><span class="sxs-lookup"><span data-stu-id="9a67a-115">For example, they do not distinguish between 4.2000 and 4.2.</span></span> <span data-ttu-id="9a67a-116">Di conseguenza, gli zeri finali non vengono visualizzati quando si visualizza o stampa valori a virgola mobile.</span><span class="sxs-lookup"><span data-stu-id="9a67a-116">Consequently, trailing zero characters do not appear when you display or print floating-point values.</span></span>  
  
-   <span data-ttu-id="9a67a-117">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="9a67a-117">**Type Characters.**</span></span> <span data-ttu-id="9a67a-118">Aggiungendo il carattere di tipo letterale `R` a un valore letterale, se ne determina la conversione nel tipo di dati `Double`.</span><span class="sxs-lookup"><span data-stu-id="9a67a-118">Appending the literal type character `R` to a literal forces it to the `Double` data type.</span></span> <span data-ttu-id="9a67a-119">Ad esempio, se un valore intero è seguito da `R`, il valore viene modificato in un `Double`.</span><span class="sxs-lookup"><span data-stu-id="9a67a-119">For example, if an integer value is followed by `R`, the value is changed to a `Double`.</span></span>  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     <span data-ttu-id="9a67a-120">Aggiungendo il carattere identificatore di tipo `#` a qualsiasi identificatore, se ne determina la conversione al tipo di dati `Double`.</span><span class="sxs-lookup"><span data-stu-id="9a67a-120">Appending the identifier type character `#` to any identifier forces it to `Double`.</span></span> <span data-ttu-id="9a67a-121">Nell'esempio seguente, la variabile `num` tipizzata come una `Double`:</span><span class="sxs-lookup"><span data-stu-id="9a67a-121">In the following example, the variable `num` is typed as a `Double`:</span></span>  
  
    ```  
    Dim num# = 3  
    ```  
  
-   <span data-ttu-id="9a67a-122">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="9a67a-122">**Framework Type.**</span></span> <span data-ttu-id="9a67a-123">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Double?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9a67a-123">The corresponding type in the .NET Framework is the <xref:System.Double?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a67a-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9a67a-124">See Also</span></span>  
 <xref:System.Double?displayProperty=nameWithType>  
 [<span data-ttu-id="9a67a-125">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9a67a-125">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="9a67a-126">Tipo di dati Decimal</span><span class="sxs-lookup"><span data-stu-id="9a67a-126">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [<span data-ttu-id="9a67a-127">Tipo di dati Single</span><span class="sxs-lookup"><span data-stu-id="9a67a-127">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [<span data-ttu-id="9a67a-128">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="9a67a-128">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="9a67a-129">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="9a67a-129">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="9a67a-130">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9a67a-130">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="9a67a-131">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9a67a-131">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [<span data-ttu-id="9a67a-132">Caratteri tipo</span><span class="sxs-lookup"><span data-stu-id="9a67a-132">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
