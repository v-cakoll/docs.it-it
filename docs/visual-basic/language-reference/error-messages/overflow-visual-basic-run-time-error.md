---
title: Overflow (errore di run-time Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
ms.openlocfilehash: 9db79071c4895d49680352bde2d0824a3756d941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594175"
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
