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
# <a name="overflow-visual-basic-run-time-error"></a>Overflow (errore di run-time Visual Basic)
Un overflow quando si tenta di un'assegnazione che superano i limiti del server di destinazione dell'assegnazione.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Assicurarsi che i risultati di tipo di dati, calcoli e le assegnazioni di conversioni non sono troppo grandi per essere rappresentate all'interno dell'intervallo di variabili è consentita per il tipo di valore e assegnare il valore a una variabile di un tipo che possono contenere un intervallo di valori più ampio , se necessario.  
  
2. Assicurarsi che le assegnazioni a proprietà rientrino nell'intervallo della proprietà a cui sono state apportate.  
  
3. Assicurarsi che i numeri utilizzati nei calcoli che vengono assegnati forzatamente a numeri interi non sono risultati superiori ai numeri interi.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Tipi di dati](../../../visual-basic/language-reference/data-types/index.md)
- [Tipi di errore](../../../visual-basic/programming-guide/language-features/error-types.md)
