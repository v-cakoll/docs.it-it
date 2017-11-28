---
title: '&lt;&lt;Operatore (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56cfb227f7e5c68de802c1f2cfb842a770f65ae0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-visual-basic"></a>&lt;&lt;Operatore (Visual Basic)
Esegue uno spostamento a sinistra aritmetico in uno schema di bit.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Valore numerico integrale. Il risultato di spostamento dello schema di bit. Il tipo di dati è uguale a quello di `pattern`.  
  
 `pattern`  
 Obbligatorio. Espressione numerica integrale. Lo schema di bit da spostare. Il tipo di dati deve essere un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obbligatorio. Espressione numerica. Il numero di bit da spostare lo schema di bit. Il tipo di dati deve essere `Integer` o ampliarsi `Integer`.  
  
## <a name="remarks"></a>Note  
 Aritmetici non sono circolare, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità. In uno spostamento a sinistra aritmetico, vengono eliminati i bit spostati oltre l'intervallo del tipo di dati di risultati, e le posizioni dei bit liberate a destra vengono impostate su zero.  
  
 Per evitare lo spostamento di un bit più che il risultato può contenere, Visual Basic nasconde il valore di `amount` con una maschera di dimensioni che corrisponde al tipo di dati di `pattern`. L'operazione di AND binaria di questi valori viene utilizzato per l'entità dello spostamento. Di seguito sono riportate le maschere di dimensioni:  
  
|Tipo di dati`pattern`|Maschera di dimensioni (decimale)|Maschera di dimensioni (esadecimale)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Se `amount` è zero, il valore di `result` è identico al valore di `pattern`. Se `amount` è negativo, verrà considerato come un valore senza segno e nascosto con la maschera di dimensioni appropriate.  
  
 Aritmetici non generano mai eccezioni di overflow.  
  
> [!NOTE]
>  Il `<<` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice utilizza l'operatore su una classe o una struttura, assicurarsi di aver compreso il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `<<` operatore per eseguire operazioni aritmetiche sinistra su valori integrali. Il risultato dispone sempre gli stessi dati di tipo dell'espressione viene spostato.  
  
 [!code-vb[VbVbalrOperators#12](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/left-shift-operator_1.vb)]  
  
 I risultati dell'esempio precedente sono come segue:  
  
-   `result1`è 192 (0000 0000 1100 0000).  
  
-   `result2`è 3072 (0000 1100 0000 0000).  
  
-   `result3`è compreso tra -32768 (1000 0000 0000 0000).  
  
-   `result4`è 384 (0000 0001 1000 0000).  
  
-   `result5`è 0 (spostato 15 posizioni a sinistra).  
  
 L'entità dello spostamento per `result4` viene calcolata come 17 e 15, pari a 1.  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori di spostamento bit](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operatore <<=](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
