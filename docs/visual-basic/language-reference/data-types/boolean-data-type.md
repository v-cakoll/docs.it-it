---
title: Tipo di dati Boolean
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
ms.openlocfilehash: 851c524a83c5f24b77a151634a96798249c5905e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84374421"
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="ee4a1-102">Tipo di dati Boolean (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee4a1-102">Boolean Data Type (Visual Basic)</span></span>

<span data-ttu-id="ee4a1-103">Include valori che possono essere solo `True` o `False` .</span><span class="sxs-lookup"><span data-stu-id="ee4a1-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="ee4a1-104">Le parole chiave `True` e `False` corrispondono ai due stati di `Boolean` variabili.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee4a1-105">Commenti</span><span class="sxs-lookup"><span data-stu-id="ee4a1-105">Remarks</span></span>  

 <span data-ttu-id="ee4a1-106">Usare il [tipo di dati booleano (Visual Basic)](boolean-data-type.md) per contenere valori a due Stati, ad esempio true/false, Yes/No o on/off.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-106">Use the [Boolean Data Type (Visual Basic)](boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="ee4a1-107">Il valore predefinito di `Boolean` è `False`.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="ee4a1-108">`Boolean`i valori non vengono archiviati come numeri e i valori archiviati non sono destinati a essere equivalenti ai numeri.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="ee4a1-109">Non scrivere mai codice che si basa su valori numerici equivalenti per `True` e `False` .</span><span class="sxs-lookup"><span data-stu-id="ee4a1-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="ee4a1-110">Laddove possibile, è consigliabile limitare l'utilizzo delle `Boolean` variabili ai valori logici per i quali sono stati progettati.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="ee4a1-111">Conversione di tipi</span><span class="sxs-lookup"><span data-stu-id="ee4a1-111">Type Conversions</span></span>  

 <span data-ttu-id="ee4a1-112">Quando Visual Basic converte i valori del tipo di dati numerico in `Boolean` , 0 diventa `False` e tutti gli altri valori diventano `True` .</span><span class="sxs-lookup"><span data-stu-id="ee4a1-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="ee4a1-113">Quando Visual Basic converte `Boolean` i valori in tipi numerici, `False` diventa 0 e `True` diventa-1.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="ee4a1-114">Quando si esegue la conversione tra `Boolean` valori e tipi di dati numerici, tenere presente che i metodi di conversione .NET Framework non producono sempre gli stessi risultati delle parole chiave di conversione di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="ee4a1-115">Ciò è dovuto al fatto che la conversione Visual Basic mantiene il comportamento compatibile con le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="ee4a1-116">Per ulteriori informazioni, vedere "il tipo booleano non viene convertito in un tipo numerico con precisione" nella [risoluzione dei problemi](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)relativi ai tipi di dati.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="ee4a1-117">Suggerimenti per la programmazione</span><span class="sxs-lookup"><span data-stu-id="ee4a1-117">Programming Tips</span></span>  
  
- <span data-ttu-id="ee4a1-118">**Numeri negativi.**</span><span class="sxs-lookup"><span data-stu-id="ee4a1-118">**Negative Numbers.**</span></span> <span data-ttu-id="ee4a1-119">`Boolean`non è un tipo numerico e non può rappresentare un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="ee4a1-120">In ogni caso, è consigliabile non usare `Boolean` per mantenere i valori numerici.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
- <span data-ttu-id="ee4a1-121">**Digitare i caratteri.**</span><span class="sxs-lookup"><span data-stu-id="ee4a1-121">**Type Characters.**</span></span> <span data-ttu-id="ee4a1-122">`Boolean`non ha un carattere di tipo letterale o un carattere di tipo identificatore.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
- <span data-ttu-id="ee4a1-123">**Tipo di framework.**</span><span class="sxs-lookup"><span data-stu-id="ee4a1-123">**Framework Type.**</span></span> <span data-ttu-id="ee4a1-124">Il tipo corrispondente in .NET Framework è la struttura <xref:System.Boolean?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee4a1-125">Esempio</span><span class="sxs-lookup"><span data-stu-id="ee4a1-125">Example</span></span>  

 <span data-ttu-id="ee4a1-126">Nell'esempio seguente `runningVB` è una `Boolean` variabile che archivia una semplice impostazione Yes/No.</span><span class="sxs-lookup"><span data-stu-id="ee4a1-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```vb  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="ee4a1-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ee4a1-127">See also</span></span>

- <xref:System.Boolean?displayProperty=nameWithType>
- [<span data-ttu-id="ee4a1-128">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="ee4a1-128">Data Types</span></span>](index.md)
- [<span data-ttu-id="ee4a1-129">CString</span><span class="sxs-lookup"><span data-stu-id="ee4a1-129">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="ee4a1-130">Riepilogo della conversione</span><span class="sxs-lookup"><span data-stu-id="ee4a1-130">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="ee4a1-131">Uso efficiente dei tipi di dati</span><span class="sxs-lookup"><span data-stu-id="ee4a1-131">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="ee4a1-132">Risoluzione dei problemi relativi ai tipi di dati</span><span class="sxs-lookup"><span data-stu-id="ee4a1-132">Troubleshooting Data Types</span></span>](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="ee4a1-133">CType Function</span><span class="sxs-lookup"><span data-stu-id="ee4a1-133">CType Function</span></span>](../functions/ctype-function.md)
