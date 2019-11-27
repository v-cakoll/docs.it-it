---
title: Operatore ^
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: b9860b7b6e076fc9c0288818aa9e4f2c0fc4c356
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331101"
---
# <a name="-operator-visual-basic"></a>Operatore ^ (Visual Basic)

Eleva un numero alla potenza di un altro numero.

## <a name="syntax"></a>Sintassi

```vb
number ^ exponent
```

## <a name="parts"></a>Parti

`number`\
Obbligatoria. Qualsiasi espressione numerica.

`exponent`\
Obbligatoria. Qualsiasi espressione numerica.

## <a name="result"></a>Risultato

Il risultato è `number` elevato alla potenza di `exponent`, sempre come valore di `Double`.

## <a name="supported-types"></a>Tipi supportati

`Double` Gli operandi di qualsiasi tipo diverso vengono convertiti in `Double`.

## <a name="remarks"></a>Note

Visual Basic esegue sempre l'elevamento a potenza nel [tipo di dati Double](../../../visual-basic/language-reference/data-types/double-data-type.md).

Il valore di `exponent` può essere frazionario, negativo o entrambi.

Quando in un'unica espressione viene eseguita più di un elevamento a potenza, l'operatore `^` viene valutato in base a quanto rilevato da sinistra verso destra.

> [!NOTE]
> L'operatore `^` può essere sottoposto a *Overload*, il che significa che una classe o una struttura può ridefinire il comportamento quando un operando ha il tipo della classe o della struttura. Se il codice usa questo operatore su una classe o una struttura di questo tipo, assicurarsi di comprendere il comportamento ridefinito. Per altre informazioni, vedere [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Esempio

Nell'esempio seguente viene usato l'operatore `^` per aumentare un numero alla potenza di un esponente. Il risultato è il primo operando elevato alla potenza del secondo.

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

L'esempio precedente produce i risultati seguenti:

`exp1` è impostato su 4 (2 quadrato).

`exp2` è impostato su 19683 (3 cubid, quindi il valore Cubed).

`exp3` è impostato su-125 (-5 Cubed).

`exp4` è impostato su 625 (-5 alla quarta potenza).

`exp5` è impostato su 2 (radice cubo di 8).

`exp6` è impostato su 0,5 (1,0 diviso per la radice del cubo di 8).

Si noti l'importanza delle parentesi nelle espressioni dell'esempio precedente. A causa della *precedenza degli operatori*, Visual Basic esegue normalmente l'operatore di `^` prima di qualsiasi altro, anche l'operatore di `–` unario. Se `exp4` e `exp6` sono stati calcolati senza parentesi, avrebbero prodotto i risultati seguenti:

`exp4 = -5 ^ 4` verrebbero calcolate come-(5 alla quarta potenza), il che comporterebbe-625.

`exp6 = 8 ^ -1.0 / 3.0` verrebbe calcolato come (da 8 a-1 potenza o 0,125) diviso per 3,0, il che comporterebbe 0.041666666666666666666666666666667.

## <a name="see-also"></a>Vedere anche

- [Operatore ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)
- [Operatori aritmetici](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Precedenza tra gli operatori in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Elenco degli operatori per funzionalità](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatori aritmetici in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
