---
title: '&gt;&gt;Operatore (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4eb0ed817c95905a679de5026bf6494eb72df078
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt;Operatore (Visual Basic)
Esegue uno spostamento verso destra aritmetico in uno schema di bit.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Valore numerico integrale. Il risultato di spostamento dello schema di bit. Il tipo di dati è uguale a quello di `pattern`.  
  
 `pattern`  
 Obbligatorio. Espressione numerica integrale. Lo schema di bit da spostare. Il tipo di dati deve essere un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obbligatorio. Espressione numerica. Il numero di bit da spostare lo schema di bit. Il tipo di dati deve essere `Integer` o ampliarsi `Integer`.  
  
## <a name="remarks"></a>Note  
 Aritmetici non sono circolare, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità. In un aritmetico a destra, i bit spostati oltre la posizione del primo bit a destra vengono ignorati e il bit più a sinistra (accesso) verrà distribuito alle posizioni dei bit liberate a sinistra. Questo significa che se `pattern` ha un valore negativo, le posizioni liberate vengono impostate su uno; in caso contrario vengono impostate su zero.  
  
 Si noti che i tipi di dati `Byte`, `UShort`, `UInteger`, e `ULong` non sono firmati, pertanto non c'è alcun bit di segno per la propagazione. Se `pattern` di eventuali tipi senza segno, le posizioni liberate sono sempre impostate su zero.  
  
 Per impedire lo spostamento di bit più che il risultato può contenere, Visual Basic nasconde il valore di `amount` con una maschera di dimensioni corrispondenti al tipo di dati di `pattern`. L'operazione di AND binaria di questi valori viene utilizzato per l'entità dello spostamento. Di seguito sono riportate le maschere di dimensioni:  
  
|Tipo di dati`pattern`|Maschera di dimensioni (decimale)|Maschera di dimensioni (esadecimale)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Se `amount` è zero, il valore di `result` è identico al valore di `pattern`. Se `amount` è negativo, verrà considerato come un valore senza segno e nascosto con la maschera di dimensioni appropriate.  
  
 Aritmetici non generano mai eccezioni di overflow.  
  
## <a name="overloading"></a>Overload  
 Il `>>` operatore può essere *overload*, il che significa che una classe o struttura ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore in una classe o una struttura, assicurarsi di comprendere il comportamento ridefinito. Per ulteriori informazioni, vedere [routine di operatore](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `>>` operatore per eseguire spostamenti a destra aritmetici in valori integrali. Il risultato dispone sempre gli stessi dati di tipo dell'espressione viene spostato.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 I risultati dell'esempio precedente sono come segue:  
  
-   `result1`è 2560 (0000 1010 0000 0000).  
  
-   `result2`è di 160 (0000 0000 1010 0000).  
  
-   `result3`è 2 (0000 0000 0000 0010).  
  
-   `result4`è 640 (0000 0010 1000 0000).  
  
-   `result5`è 0 (spostate 15 cifre a destra).  
  
 L'entità dello spostamento per `result4` viene calcolata come 18 e 15, pari a 2.  
  
 Nell'esempio seguente viene aritmetici su un valore negativo.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 I risultati dell'esempio precedente sono come segue:  
  
-   `negresult1`è -512 (1111 1110 0000 0000).  
  
-   `negresult2`è -1 (il bit di segno è stato propagato).  
  
## <a name="see-also"></a>Vedere anche  
 [Operatori di spostamento bit](../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operatore >>=](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)  
 [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
