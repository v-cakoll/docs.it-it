---
title: Overflow (errore di run-time Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1908ad576a499e79102aff23e3e2f11d7d99d52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="overflow-visual-basic-run-time-error"></a>Overflow (errore di run-time Visual Basic)
Quando si tenta un'assegnazione che supera i limiti della destinazione dell'assegnazione di un overflow.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1.  Assicurarsi che i risultati di tipo di dati, calcoli e le assegnazioni di conversioni non sono troppo grandi per essere rappresentate all'interno dell'intervallo di variabili consentito per il tipo di valore e assegnare il valore a una variabile di un tipo che possono contenere un intervallo più ampio di valori , se necessario.  
  
2.  Verificare che le assegnazioni alle proprietà corrispondono all'intervallo della proprietà a cui sono state apportate.  
  
3.  Assicurarsi che i numeri utilizzati nei calcoli che vengono assegnati forzatamente a numeri interi non hanno risultati superiori ai valori integer.  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [Tipi di dati](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)
