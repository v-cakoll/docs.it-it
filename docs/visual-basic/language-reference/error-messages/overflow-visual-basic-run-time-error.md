---
title: Overflow (errore di run-time Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 7546676b85465577b357b7ad0757b4db8d40dbe3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934439"
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="d5194-102">Overflow (errore di run-time Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5194-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="d5194-103">Un overflow quando si tenta di un'assegnazione che superano i limiti del server di destinazione dell'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="d5194-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d5194-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="d5194-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="d5194-105">Assicurarsi che i risultati di tipo di dati, calcoli e le assegnazioni di conversioni non sono troppo grandi per essere rappresentate all'interno dell'intervallo di variabili è consentita per il tipo di valore e assegnare il valore a una variabile di un tipo che possono contenere un intervallo di valori più ampio , se necessario.</span><span class="sxs-lookup"><span data-stu-id="d5194-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2.  <span data-ttu-id="d5194-106">Assicurarsi che le assegnazioni a proprietà rientrino nell'intervallo della proprietà a cui sono state apportate.</span><span class="sxs-lookup"><span data-stu-id="d5194-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3.  <span data-ttu-id="d5194-107">Assicurarsi che i numeri utilizzati nei calcoli che vengono assegnati forzatamente a numeri interi non sono risultati superiori ai numeri interi.</span><span class="sxs-lookup"><span data-stu-id="d5194-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5194-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d5194-108">See Also</span></span>  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [<span data-ttu-id="d5194-109">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="d5194-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)  
 [<span data-ttu-id="d5194-110">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="d5194-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
