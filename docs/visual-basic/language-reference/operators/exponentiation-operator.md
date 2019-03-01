---
title: Operatore ^ (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: ce9cd527aff1203f30543b03f1520d429d038da3
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56978951"
---
# <a name="-operator-visual-basic"></a>Operatore ^ (Visual Basic)
Eleva un numero alla potenza di un altro numero.  
  
## <a name="syntax"></a>Sintassi  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a>Parti  
 `number`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
 `exponent`  
 Obbligatorio. Qualsiasi espressione numerica.  
  
## <a name="result"></a>Risultato  
 Il risultato viene `number` elevato alla potenza del `exponent`, sempre come una `Double` valore.  
  
## <a name="supported-types"></a>Tipi supportati  
 `Double`. Gli operandi di tipo diversi vengono convertiti in `Double`.  
  
## <a name="remarks"></a>Note  
 Visual Basic esegue sempre l'elevamento a potenza nel [tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md).  
  
 Il valore di `exponent` può essere frazionari, negativo o entrambi.  
  
 Quando più di un elevamento a potenza viene eseguito in un'unica espressione, il `^` operatore viene valutato quando viene rilevata da sinistra a destra.  
  
> [!NOTE]
>  Il `^` operatore può essere *sottoposto a overload*, il che significa che una classe o struttura può ridefinire il comportamento quando un operando ha il tipo di quella classe o struttura. Se il codice Usa l'operatore su una classe o struttura, assicurarsi di che comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Esempio  
 L'esempio seguente usa il `^` operatore per la generazione di un numero alla potenza di un esponente. Il risultato è il primo operando elevato alla potenza del secondo.  
  
 [!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]  
  
 L'esempio precedente produce i risultati seguenti:  
  
 `exp1` è impostato su 4 (2 al quadrato).  
  
 `exp2` è impostato su 19683 (3 al cubo, quindi tale valore al cubo).  
  
 `exp3` è impostato su -125 (al cubo -5).  
  
 `exp4` è impostato su 625 (-5 elevato alla potenza quarto).  
  
 `exp5` è impostato su 2 (radice cubica di 8).  
  
 `exp6` è impostato su 0,5 (1.0 diviso per la radice cubica di 8).  
  
 Si noti l'importanza delle parentesi nelle espressioni nell'esempio precedente. Because of *precedenza tra gli operatori*, Visual Basic esegue normalmente il `^` operatore prima degli altri, anche l'operatore unario `–` operatore. Se `exp4` e `exp6` fosse stato eseguito senza parentesi, che avrebbe prodotto i risultati seguenti:  
  
 `exp4 = -5 ^ 4` viene calcolato come: (5 elevato alla potenza quarto), che comporterebbe-625.  
  
 `exp6 = 8 ^ -1.0 / 3.0` viene calcolato come (8 per la potenza di-1 o 0.125) diviso per 3.0, risultato uguale a 0,041666666666666666666666666666667.  
  
## <a name="see-also"></a>Vedere anche
- [Operatore ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
