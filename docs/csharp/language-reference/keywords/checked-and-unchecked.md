---
title: Checked e Unchecked (Riferimenti per C#)
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: f8e292a67fab49b5fc3616e438d063eca2617274
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2018
ms.locfileid: "34234373"
---
# <a name="checked-and-unchecked-c-reference"></a>Checked e Unchecked (Riferimenti per C#)
È possibile eseguire istruzioni C# in contesti verificati o non verificati. In un contesto verificato l'overflow aritmetico genera un'eccezione. In un contesto non verificato, l'overflow aritmetico viene ignorato e il risultato viene troncato mediante l'eliminazione di tutti i bit più significativi che non corrispondono al tipo di destinazione.  
  
-   [checked](checked.md) Specificare il contesto verificato.  
  
-   [unchecked](unchecked.md) Specificare il contesto non verificato.  
  
 Le operazioni seguenti sono interessate dal controllo di overflow:  
  
-   Espressioni che usano gli operatori predefiniti seguenti su tipi integrali:  
  
     `++`, `--`, `-` unario, `+`, `-`, `*`, `/`  
  
-   Conversioni numeriche esplicite tra tipi integrali oppure da `float` o `double` a un tipo integrale.  
  
 Se non si specifica `checked` né `unchecked`, il contesto predefinito per le espressioni non costanti (espressioni che vengono valutate in fase di esecuzione) è definito dal valore dell'opzione del compilatore [-checked](../compiler-options/checked-compiler-option.md). Per impostazione predefinita il valore di tale opzione non è impostato e le operazioni aritmetiche vengono eseguite in un contesto non verificato.
 
 Per le espressioni costanti (espressioni che possono essere valutate per intero in fase di compilazione), il contesto predefinito viene sempre controllato. A meno che un'espressione costante non venga posizionata in modo esplicito in un contesto non verificato, gli overflow che si verificano durante la valutazione in fase di compilazione dell'espressione causano errori in fase di compilazione.
  
## <a name="see-also"></a>Vedere anche  
 [Riferimenti per C#](../index.md)  
 [Guida per programmatori C#](../../programming-guide/index.md)  
 [Parole chiave di C#](index.md)  
 [Parole chiave per le istruzioni](statement-keywords.md)
