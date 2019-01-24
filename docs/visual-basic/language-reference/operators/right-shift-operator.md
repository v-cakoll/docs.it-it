---
title: '&gt;&gt; Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.>>
helpviewer_keywords:
- operator>>
- '>> operator [Visual Basic]'
- bit shift operators [Visual Basic]
- operator >>
- right shift operators [Visual Basic]
ms.assetid: 054dc6a6-47d9-47ef-82da-cfa2b59fbf8f
ms.openlocfilehash: e1d2b6569e2bcb3c1516dbc8c78adca0855481e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668496"
---
# <a name="gtgt-operator-visual-basic"></a>&gt;&gt; Operatore (Visual Basic)
Esegue uno scorrimento a destra aritmetico in uno schema di bit.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = pattern >> amount  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Valore numerico integrale. Il risultato dello spostamento dello schema di bit. Il tipo di dati è uguale a quello di `pattern`.  
  
 `pattern`  
 Obbligatorio. Espressione numerica integrale. Lo schema di bit da spostare. Il tipo di dati deve essere un tipo integrale (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Obbligatorio. Espressione numerica. Il numero di bit da spostare lo schema di bit. Il tipo di dati deve essere `Integer` o ampliato a `Integer`.  
  
## <a name="remarks"></a>Note  
 Aritmetici non sono circolari, ovvero i bit spostati oltre un'estremità del risultato non sono reintrodotto a altra estremità. In uno scorrimento aritmetico a destra, i bit spostati oltre la posizione del bit più a destra vengono ignorati e il bit più a sinistra (accesso) viene propagato nelle posizioni dei bit liberate a sinistra. Questo significa che se `pattern` ha un valore negativo, le posizioni vuote sono impostate su uno; in caso contrario, essi vengono impostati su zero.  
  
 Si noti che i tipi di dati `Byte`, `UShort`, `UInteger`, e `ULong` non sono firmati, pertanto non presenta alcun bit di segno per la propagazione. Se `pattern` è di qualsiasi tipi senza segno, le posizioni vuote sono sempre impostate su zero.  
  
 Per impedire lo spostamento da più bit quello che può contenere il risultato, Visual Basic nasconde il valore di `amount` con una maschera di dimensione corrispondente al tipo di dati di `pattern`. L'operatore AND binaria di questi valori viene utilizzato per l'entità dello spostamento. Le maschere di dimensioni sono i seguenti:  
  
|Tipo di dati `pattern`|Maschera di dimensioni (decimale)|Maschera di dimensioni (esadecimale)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|&H00000007|  
|`Short`, `UShort`|15|&H0000000F|  
|`Integer`, `UInteger`|31|&H0000001F|  
|`Long`, `ULong`|63|&H0000003F|  
  
 Se `amount` è zero, il valore di `result` è identico a quello di `pattern`. Se `amount` è negativo, viene considerato come un valore senza segno e nascosto con la maschera delle dimensioni appropriate.  
  
 Aritmetici non generano mai le eccezioni di overflow.  
  
## <a name="overloading"></a>Overload  
 Il `>>` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `>>` operatore eseguire spostamenti a destra aritmetici in valori integrali. Il risultato ha sempre gli stessi dati di tipo come quello dell'espressione viene spostato.  
  
 [!code-vb[VbVbalrOperators#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_1.vb)]  
  
 I risultati dell'esempio precedente sono come segue:  
  
-   `result1` is 2560 (0000 1010 0000 0000).  
  
-   `result2` is 160 (0000 0000 1010 0000).  
  
-   `result3` is 2 (0000 0000 0000 0010).  
  
-   `result4` is 640 (0000 0010 1000 0000).  
  
-   `result5` è uguale a 0 (spostate 15 cifre a destra).  
  
 L'entità dello spostamento per `result4` è pari a 18 e 15, quali uguale a 2.  
  
 Nell'esempio seguente mostra aritmetici su un valore negativo.  
  
 [!code-vb[VbVbalrOperators#55](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/right-shift-operator_2.vb)]  
  
 I risultati dell'esempio precedente sono come segue:  
  
-   `negresult1` is -512 (1111 1110 0000 0000).  
  
-   `negresult2` è -1 (il bit di segno viene propagato).  
  
## <a name="see-also"></a>Vedere anche
- [Operatori di spostamento bit](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatore >>=](../../../visual-basic/language-reference/operators/right-shift-assignment-operator.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
