---
title: Tipo di dati Boolean (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 5e90d1dc5eb0beb3afd8fc69da32f89943e94c48
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54741912"
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="0ad76-102">Tipo di dati Boolean (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ad76-102">Boolean Data Type (Visual Basic)</span></span>
<span data-ttu-id="0ad76-103">Contiene i valori che possono essere solo `True` o `False`.</span><span class="sxs-lookup"><span data-stu-id="0ad76-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="0ad76-104">Le parole chiave `True` e `False` corrispondono a due stati di `Boolean` variabili.</span><span class="sxs-lookup"><span data-stu-id="0ad76-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ad76-105">Note</span><span class="sxs-lookup"><span data-stu-id="0ad76-105">Remarks</span></span>  
 <span data-ttu-id="0ad76-106">Usare la [tipo di dati Boolean (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) per contenere i valori di due stati, ad esempio true/false, sì/no o on/off.</span><span class="sxs-lookup"><span data-stu-id="0ad76-106">Use the [Boolean Data Type (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="0ad76-107">Il valore predefinito di `Boolean` è `False`.</span><span class="sxs-lookup"><span data-stu-id="0ad76-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="0ad76-108">`Boolean` i valori non vengono archiviati come numeri e i valori archiviati non sono considerati equivalenti ai numeri.</span><span class="sxs-lookup"><span data-stu-id="0ad76-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="0ad76-109">Non scrivere mai codice che si basa su valori numerici equivalenti per `True` e `False`.</span><span class="sxs-lookup"><span data-stu-id="0ad76-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="0ad76-110">Quando possibile, è consigliabile limitare l'utilizzo di `Boolean` variabili per i valori logici per il quale sono progettate.</span><span class="sxs-lookup"><span data-stu-id="0ad76-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="0ad76-111">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="0ad76-111">Type Conversions</span></span>  
 <span data-ttu-id="0ad76-112">Quando Visual Basic converte i valori di tipo di dati numerici in `Boolean`, diventa 0 `False` e tutti gli altri valori diventano `True`.</span><span class="sxs-lookup"><span data-stu-id="0ad76-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="0ad76-113">Quando Visual Basic consente di convertire `Boolean` i valori per i tipi numerici `False` diventa 0 e `True` diventano -1.</span><span class="sxs-lookup"><span data-stu-id="0ad76-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="0ad76-114">Quando eseguire la conversione tra `Boolean` valori e tipi di dati numerici, tenere presente che i metodi di conversione di .NET Framework non producono sempre gli stessi risultati di parole chiave di conversione di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0ad76-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="0ad76-115">Questo avviene perché la conversione di Visual Basic mantiene un comportamento compatibile con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="0ad76-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="0ad76-116">Per altre informazioni, vedere "Booleano tipo non di numerico tipo accuratezza durante la conversione" nella [tipi di dati di risoluzione dei problemi](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0ad76-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="0ad76-117">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="0ad76-117">Programming Tips</span></span>  
  
-   <span data-ttu-id="0ad76-118">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="0ad76-118">**Negative Numbers.**</span></span> <span data-ttu-id="0ad76-119">`Boolean` non è un tipo numerico e non può rappresentare un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="0ad76-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="0ad76-120">In ogni caso, è consigliabile non usare `Boolean` per contenere valori numerici.</span><span class="sxs-lookup"><span data-stu-id="0ad76-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="0ad76-121">**Caratteri tipo.**</span><span class="sxs-lookup"><span data-stu-id="0ad76-121">**Type Characters.**</span></span> <span data-ttu-id="0ad76-122">`Boolean` non dispone di alcun carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="0ad76-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="0ad76-123">**Tipo di Framework.**</span><span class="sxs-lookup"><span data-stu-id="0ad76-123">**Framework Type.**</span></span> <span data-ttu-id="0ad76-124">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0ad76-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ad76-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ad76-125">Example</span></span>  
 <span data-ttu-id="0ad76-126">Nell'esempio riportato di seguito `runningVB` è un `Boolean` variabile che archivia una semplice impostazione sì/no.</span><span class="sxs-lookup"><span data-stu-id="0ad76-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ad76-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0ad76-127">See also</span></span>
- <xref:System.Boolean?displayProperty=nameWithType>
- [<span data-ttu-id="0ad76-128">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0ad76-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0ad76-129">Funzioni di conversione del tipo</span><span class="sxs-lookup"><span data-stu-id="0ad76-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0ad76-130">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="0ad76-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="0ad76-131">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0ad76-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="0ad76-132">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="0ad76-132">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="0ad76-133">Funzione CType</span><span class="sxs-lookup"><span data-stu-id="0ad76-133">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
