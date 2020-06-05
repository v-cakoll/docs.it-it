---
title: Overflow (errore di run-time Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 5606ae8188c12142800adef46819791b732ff73c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387270"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="2dc2d-102">Overflow (errore di run-time Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2dc2d-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="2dc2d-103">Un overflow viene restituito quando si tenta un'assegnazione che supera i limiti della destinazione dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="2dc2d-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2dc2d-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="2dc2d-104">To correct this error</span></span>  
  
1. <span data-ttu-id="2dc2d-105">Verificare che i risultati di assegnazioni, calcoli e conversioni di tipi di dati non siano troppo grandi per essere rappresentati nell'intervallo di variabili consentito per quel tipo di valore, quindi assegnare il valore a una variabile di un tipo che può contenere un intervallo di valori più grande, se necessario.</span><span class="sxs-lookup"><span data-stu-id="2dc2d-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2. <span data-ttu-id="2dc2d-106">Assicurarsi che le assegnazioni alle proprietà corrispondano all'intervallo della proprietà in cui vengono eseguite.</span><span class="sxs-lookup"><span data-stu-id="2dc2d-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3. <span data-ttu-id="2dc2d-107">Verificare che i numeri utilizzati nei calcoli assegnati a valori integer non contengano risultati maggiori di quelli di tipo Integer.</span><span class="sxs-lookup"><span data-stu-id="2dc2d-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dc2d-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2dc2d-108">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="2dc2d-109">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="2dc2d-109">Data Types</span></span>](../data-types/index.md)
- [<span data-ttu-id="2dc2d-110">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="2dc2d-110">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
