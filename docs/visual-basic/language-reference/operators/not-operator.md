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
ms.openlocfilehash: 56cdeb80a217dbce15921eddd6a43d8d1b049376
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401459"
---
# <a name="not-operator-visual-basic"></a>Operatore Not (Visual Basic)
Esegue una negazione logica su un' `Boolean` espressione o una negazione bit per bit su un'espressione numerica.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a>Parti  
 `result`  
 Obbligatorio. Qualsiasi espressione `Boolean` o numerica.  
  
 `expression`  
 Obbligatorio. Qualsiasi espressione `Boolean` o numerica.  
  
## <a name="remarks"></a>Commenti  
 Per `Boolean` le espressioni, nella tabella seguente viene illustrato il modo in cui `result` viene determinato.  
  
|Se `expression` è |Il valore di `result` è|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Per le espressioni numeriche, l' `Not` operatore inverte i valori di bit di qualsiasi espressione numerica e imposta il bit corrispondente in in `result` base alla tabella seguente.  
  
|Se il bit in `expression` è|Il bit in `result` è|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
> Poiché gli operatori logici e bit per bit hanno una precedenza inferiore rispetto ad altri operatori aritmetici e relazionali, qualsiasi operazione bit per bit deve essere racchiusa tra parentesi per garantire un'esecuzione accurata.  
  
## <a name="data-types"></a>Tipi di dati  
 Per una negazione booleana, il tipo di dati del risultato è `Boolean` . Per una negazione bit per bit, il tipo di dati del risultato è identico a quello di `expression` . Tuttavia, se Expression è `Decimal` , il risultato è `Long` .  
  
## <a name="overloading"></a>Overload  
 L' `Not` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando il relativo operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `Not` operatore per eseguire la negazione logica su un' `Boolean` espressione. Il risultato è un `Boolean` valore che rappresenta l'inverso del valore dell'espressione.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 Nell'esempio precedente vengono restituiti i risultati di `False` e `True` , rispettivamente.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato l' `Not` operatore per eseguire la negazione logica dei singoli bit di un'espressione numerica. Il bit nel modello di risultato viene impostato sul contrario del bit corrispondente nel modello di operando, incluso il bit di segno.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 Nell'esempio precedente vengono restituiti rispettivamente i risultati di – 11, – 9 e-7.  
  
## <a name="see-also"></a>Vedere anche

- [Operatori logici e bit per bit (Visual Basic)](logical-bitwise-operators.md)
- [Precedenza tra gli operatori in Visual Basic](operator-precedence.md)
- [Elenco degli operatori per funzionalità](operators-listed-by-functionality.md)
- [Operatori logici e bit per bit in Visual Basic](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
