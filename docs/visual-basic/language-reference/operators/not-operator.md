---
title: Operatore Not
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 08b091ccf6c50438b5ad9d6c445510112abe7418
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348302"
---
# <a name="not-operator-visual-basic"></a>Operatore Not (Visual Basic)
Esegue una negazione logica su un'espressione `Boolean` o una negazione bit per bit di un'espressione numerica.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatoria. Qualsiasi `Boolean` o espressione numerica.  
  
 `expression`  
 Obbligatoria. Qualsiasi `Boolean` o espressione numerica.  
  
## <a name="remarks"></a>Note  
 Per `Boolean` espressioni, nella tabella seguente viene illustrata la modalità di determinazione della `result`.  
  
|Se `expression` è|Il valore di `result` è|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Per le espressioni numeriche, l'operatore `Not` inverte i valori di bit di qualsiasi espressione numerica e imposta il bit corrispondente in `result` in base alla tabella seguente.  
  
|Se bit in `expression` è|Il bit in `result` è|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
> Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire un'esecuzione accurata.  
  
## <a name="data-types"></a>Tipi di dati  
 Per una negazione booleana, il tipo di dati del risultato è `Boolean`. Per una negazione bit per bit, il tipo di dati del risultato è identico a quello di `expression`. Tuttavia, se Expression è `Decimal`, il risultato viene `Long`.  
  
## <a name="overloading"></a>Overload  
 L'operatore `Not` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `Not` per eseguire la negazione logica su un'espressione `Boolean`. Il risultato è un valore `Boolean` che rappresenta l'inverso del valore dell'espressione.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 Nell'esempio precedente vengono prodotti rispettivamente i risultati di `False` e `True`.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l'operatore `Not` per eseguire la negazione logica dei singoli bit di un'espressione numerica. Il bit nel modello di risultato viene impostato sul contrario del bit corrispondente nel modello di operando, incluso il bit di segno.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 Nell'esempio precedente vengono restituiti rispettivamente i risultati di – 11, – 9 e-7.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici/bit per bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori logici e bit per bit in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
