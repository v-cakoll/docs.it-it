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
ms.openlocfilehash: 0c10fc3998469e19d5be744ea8fb4faed25f1a2a
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201222"
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
 Obbligatorio. Qualsiasi espressione numerica.  
  
 `expression2`  
 Obbligatorio solo se il `–` operatore sta calcolando un valore negativo. Qualsiasi espressione numerica.  
  
## <a name="result"></a>Risultato  
 Il risultato è la differenza tra `expression1` e `expression2`, o il valore negato di `expression1`.  
  
 Il tipo di dati del risultato è un tipo numerico appropriato per i tipi di dati di `expression1` e `expression2`. Vedere le tabelle "Calcoli di interi" nella [Data Types of operatore Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="supported-types"></a>Tipi supportati  
 tutti i tipi numerici. Inclusi i tipi senza segno e a virgola mobile e `Decimal`.  
  
## <a name="remarks"></a>Note  
 Nel primo utilizzo illustrato nella sintassi illustrata in precedenza, il `–` operatore è il *binario* operatore di sottrazione aritmetica per la differenza tra due espressioni numeriche.  
  
 Nel secondo utilizzo illustrato nella sintassi illustrata in precedenza, il `–` operatore è il *unario* operatore di negazione per il valore negativo di un'espressione. In questo senso, è costituito invertire il segno di negazione `expression1` in modo che il risultato è un valore positivo se `expression1` è negativo.  
  
 Se delle espressioni viene valutata [Nothing](../../../visual-basic/language-reference/nothing.md), il `–` operatore lo considera come zero.  
  
> [!NOTE]
>  Il `–` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di aver compreso il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `–` operatore per calcolare e restituire la differenza tra due numeri, quindi per negare a un numero.  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 Dopo l'esecuzione di queste istruzioni `binaryResult` contiene il valore 124,45 e `unaryResult` 334,90.  
  
## <a name="see-also"></a>Vedere anche
- [-= Operatore (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
