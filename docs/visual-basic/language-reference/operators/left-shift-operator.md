---
title: Operatore < < (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<<
helpviewer_keywords:
- bit shift operators [Visual Basic]
- << operator [Visual Basic]
- operator <<, Visual Basic left shift operator
ms.assetid: fdb93d25-81ba-417f-b808-41207bfb8440
ms.openlocfilehash: d6b186ad519bcd7cf82cce12523f2d75e09317cc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966891"
---
# <a name="-operator-visual-basic"></a>\<\<Operatore (Visual Basic)
Esegue uno scorrimento a sinistra aritmetico in uno schema di bit.  
  
## <a name="syntax"></a>Sintassi  
  
```  
result = pattern << amount  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Richiesto. Valore numerico integrale. Risultato dello spostamento dello schema di bit. Il tipo di dati è uguale a quello di `pattern`.  
  
 `pattern`  
 Richiesto. Espressione numerica integrale. Modello di bit da spostare. Il tipo di dati deve essere un tipo integrale`SByte`( `Byte` `Short`,, `UShort`, `Integer`, `UInteger`, `Long`, o `ULong`).  
  
 `amount`  
 Richiesto. Espressione numerica. Numero di bit per spostare lo schema di bit. Il tipo di dati deve `Integer` essere o ampliato a. `Integer`  
  
## <a name="remarks"></a>Note  
 I turni aritmetici non sono circolari, il che significa che i bit spostati da un'estremità del risultato non vengono reintrodotti nell'altra estremità. In uno scorrimento a sinistra aritmetico, i bit spostati oltre l'intervallo del tipo di dati del risultato vengono rimossi e le posizioni dei bit sgomberate a destra vengono impostate su zero.  
  
 Per evitare uno spostamento di più bit rispetto al risultato, Visual Basic maschera il valore di `amount` con una maschera di dimensioni che corrisponde al tipo di dati di. `pattern` Il file binario e di questi valori viene utilizzato per l'importo dello spostamento. Le maschere delle dimensioni sono le seguenti:  
  
|Tipo di dati di`pattern`|Maschera dimensioni (decimale)|Maschera dimensioni (esadecimale)|  
|----------------------------|---------------------------|-------------------------------|  
|`SByte`, `Byte`|7|& H00000007|  
|`Short`, `UShort`|15|& H0000000F|  
|`Integer`, `UInteger`|31|& H0000001F|  
|`Long`, `ULong`|63|& H0000003F|  
  
 Se `amount` è zero, il valore di `result` è identico al valore di `pattern`. Se `amount` è negativo, viene considerato come un valore senza segno e mascherato con la maschera di dimensioni appropriata.  
  
 I turni aritmetici non generano mai eccezioni di overflow.  
  
> [!NOTE]
> L' `<<` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato `<<` l'operatore per eseguire turni aritmetici a sinistra sui valori integrali. Il risultato ha sempre lo stesso tipo di dati dell'espressione spostata.  
  
 [!code-vb[VbVbalrOperators#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#12)]  
  
 I risultati dell'esempio precedente sono i seguenti:  
  
- `result1`è 192 (0000 0000 1100 0000).  
  
- `result2`è 3072 (0000 1100 0000 0000).  
  
- `result3`is-32768 (1000 0000 0000 0000).  
  
- `result4` is 384 (0000 0001 1000 0000).  
  
- `result5`è 0 (spostato di 15 posizioni a sinistra).  
  
 Il valore Shift per `result4` viene calcolato come 17 e 15, che è uguale a 1.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori di spostamento bit](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Operatori di assegnazione](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operatore <<=](../../../visual-basic/language-reference/operators/left-shift-assignment-operator.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
