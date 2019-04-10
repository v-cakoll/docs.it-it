---
title: Overflow (errore di run-time Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 63223a815e1c4ff8d4e0afbb6c732fff90aad465
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345547"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="7e4e2-102">Overflow (errore di run-time Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7e4e2-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="7e4e2-103">Un overflow quando si tenta di un'assegnazione che superano i limiti del server di destinazione dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="7e4e2-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7e4e2-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="7e4e2-104">To correct this error</span></span>  
  
1. <span data-ttu-id="7e4e2-105">Assicurarsi che i risultati di tipo di dati, calcoli e le assegnazioni di conversioni non sono troppo grandi per essere rappresentate all'interno dell'intervallo di variabili è consentita per il tipo di valore e assegnare il valore a una variabile di un tipo che possono contenere un intervallo di valori più ampio , se necessario.</span><span class="sxs-lookup"><span data-stu-id="7e4e2-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2. <span data-ttu-id="7e4e2-106">Assicurarsi che le assegnazioni a proprietà rientrino nell'intervallo della proprietà a cui sono state apportate.</span><span class="sxs-lookup"><span data-stu-id="7e4e2-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3. <span data-ttu-id="7e4e2-107">Assicurarsi che i numeri utilizzati nei calcoli che vengono assegnati forzatamente a numeri interi non sono risultati superiori ai numeri interi.</span><span class="sxs-lookup"><span data-stu-id="7e4e2-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e4e2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7e4e2-108">See also</span></span>

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [<span data-ttu-id="7e4e2-109">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="7e4e2-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="7e4e2-110">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="7e4e2-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
