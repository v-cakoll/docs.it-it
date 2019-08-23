---
title: '- Operatore (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: eb34b34986613f36b624c43c04f98390ffba4fe0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965858"
---
# <a name="--operator-visual-basic"></a>Operatore - (Visual Basic)
Restituisce la differenza tra due espressioni numeriche o il valore negativo di un'espressione numerica.  
  
## <a name="syntax"></a>Sintassi  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a>Parti  
 `expression1`  
 Richiesto. Qualsiasi espressione numerica.  
  
 `expression2`  
 Obbligatorio a meno che `–` l'operatore non calcoli un valore negativo. Qualsiasi espressione numerica.  
  
## <a name="result"></a>Risultato  
 Il risultato è la differenza tra `expression1` e `expression2`o il valore negato di `expression1`.  
  
 Il tipo di dati del risultato è un tipo numerico appropriato per i tipi `expression1` di `expression2`dati di e. Vedere le tabelle "aritmetiche di interi" nei [tipi di dati dei risultati dell'operatore](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Tipi supportati  
 tutti i tipi numerici. Sono inclusi i tipi a virgola mobile e non firmati `Decimal`e.  
  
## <a name="remarks"></a>Note  
 Nel primo utilizzo illustrato nella sintassi illustrata in precedenza, l' `–` operatore è l'operatore di sottrazione aritmetica *binario* per la differenza tra due espressioni numeriche.  
  
 Nel secondo utilizzo illustrato nella sintassi illustrata in precedenza, l' `–` operatore è l'operatore di negazione *unario* per il valore negativo di un'espressione. In questo senso, la negazione consiste nell'inversione del segno di `expression1` in modo che il risultato sia positivo se `expression1` è negativo.  
  
 Se una delle due espressioni restituisce [Nothing](../../../visual-basic/language-reference/nothing.md), l' `–` operatore lo considera come zero.  
  
> [!NOTE]
> L' `–` operatore può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, verificare di aver compreso il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato `–` l'operatore per calcolare e restituire la differenza tra due numeri e quindi per negare un numero.  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 Dopo l'esecuzione di queste istruzioni, `binaryResult` contiene 124,45 e `unaryResult` contiene – 334,90.  
  
## <a name="see-also"></a>Vedere anche

- [Operatore-= (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
