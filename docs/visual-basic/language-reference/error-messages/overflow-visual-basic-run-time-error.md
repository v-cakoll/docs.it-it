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
# <a name="overflow-visual-basic-run-time-error"></a>Overflow (errore di run-time Visual Basic)
Un overflow viene restituito quando si tenta un'assegnazione che supera i limiti della destinazione dell'assegnazione.  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
1. Verificare che i risultati di assegnazioni, calcoli e conversioni di tipi di dati non siano troppo grandi per essere rappresentati nell'intervallo di variabili consentito per quel tipo di valore, quindi assegnare il valore a una variabile di un tipo che può contenere un intervallo di valori più grande, se necessario.  
  
2. Assicurarsi che le assegnazioni alle proprietà corrispondano all'intervallo della proprietà in cui vengono eseguite.  
  
3. Verificare che i numeri utilizzati nei calcoli assegnati a valori integer non contengano risultati maggiori di quelli di tipo Integer.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Int32.MaxValue?displayProperty=nameWithType>
- <xref:System.Double.MaxValue?displayProperty=nameWithType>
- [Tipi di dati](../data-types/index.md)
- [Tipi di errore](../../programming-guide/language-features/error-types.md)
