---
title: Overflow (errore di run-time Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1908ad576a499e79102aff23e3e2f11d7d99d52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="overflow-visual-basic-run-time-error"></a><span data-ttu-id="9becd-102">Overflow (errore di run-time Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9becd-102">Overflow (Visual Basic Run-Time Error)</span></span>
<span data-ttu-id="9becd-103">Quando si tenta un'assegnazione che supera i limiti della destinazione dell'assegnazione di un overflow.</span><span class="sxs-lookup"><span data-stu-id="9becd-103">An overflow results when you attempt an assignment that exceeds the limits of the assignment's target.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9becd-104">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="9becd-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="9becd-105">Assicurarsi che i risultati di tipo di dati, calcoli e le assegnazioni di conversioni non sono troppo grandi per essere rappresentate all'interno dell'intervallo di variabili consentito per il tipo di valore e assegnare il valore a una variabile di un tipo che possono contenere un intervallo più ampio di valori , se necessario.</span><span class="sxs-lookup"><span data-stu-id="9becd-105">Make sure that results of assignments, calculations, and data type conversions are not too large to be represented within the range of variables allowed for that type of value, and assign the value to a variable of a type that can hold a larger range of values, if necessary.</span></span>  
  
2.  <span data-ttu-id="9becd-106">Verificare che le assegnazioni alle proprietà corrispondono all'intervallo della proprietà a cui sono state apportate.</span><span class="sxs-lookup"><span data-stu-id="9becd-106">Make sure assignments to properties fit the range of the property to which they are made.</span></span>  
  
3.  <span data-ttu-id="9becd-107">Assicurarsi che i numeri utilizzati nei calcoli che vengono assegnati forzatamente a numeri interi non hanno risultati superiori ai valori integer.</span><span class="sxs-lookup"><span data-stu-id="9becd-107">Make sure that numbers used in calculations that are coerced into integers do not have results larger than integers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9becd-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9becd-108">See Also</span></span>  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [<span data-ttu-id="9becd-109">Tipi di dati</span><span class="sxs-lookup"><span data-stu-id="9becd-109">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="9becd-110">Tipi di errore</span><span class="sxs-lookup"><span data-stu-id="9becd-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
